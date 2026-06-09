# RasInitialize

- ea: `0x18000b230`
- end: `0x180011438`
- name: `RasInitialize`
- size: `25096`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1800119b0`
- `0x180013f40`

## callees

- `0x1800016f0`
- `0x180001c40`
- `0x180001ff0`
- `0x180002200`
- `0x18000b230`
- `0x180011590`
- `0x180014490`
- `0x1800144e0`
- `0x180014510`
- `0x180014570`
- `0x18001531c`
- `0x1800153e0`
- `0x180021ae4`
- `0x180021b14`
- `0x1800244b8`
- `0x180027386`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d3c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d3c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d3e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d336`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d336`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ca78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000f823`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ca78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000f823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f845`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b8ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b8ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d816`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b352`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001021a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001068b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001021a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001068b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b892`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000badd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bbb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bbe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c5ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c638`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c67b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d25f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbe4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dced`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dde2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e31b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f359`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f38f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010194`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010286`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001030f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010342`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010382`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001043b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001046e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001059d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010623`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b892`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000badd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bbb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bbe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c5ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c638`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c67b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c6d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d25f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbe4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dc83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dced`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dde2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e31b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f359`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f38f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010194`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010286`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001030f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010342`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010382`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001043b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001046e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001059d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010623`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b386`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b44d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b87a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bba2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bbcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c38d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c43b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c5d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c620`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c663`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c6c4`

## string_xrefs

- `0x18000ca6b`: `ntdll.dll`
- `0x18000f7f7`: `ntdll.dll`
- `0x18000d90f`: `SSTP service initialization failed, error = %d`
- `0x18000d8b4`: `RASMAN service initialization failed, error = %d`
- `0x180011240`: `Rasman service was started by RasInitialize`
- `0x180011292`: `TapiSrv service initialization failed, error = %d`

## pseudocode

```c
DWORD RasInitialize()
{
  DWORD result; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  __int64 v3; // rdx
  int *v4; // rbx
  void *v5; // r14
  wchar_t *v6; // r13
  HANDLE ProcessHeap; // rax
  _OWORD *v8; // rax
  _OWORD *v9; // r12
  HANDLE v10; // rax
  wchar_t *v11; // rax
  const wchar_t *v12; // rcx
  int v13; // r15d
  int v14; // eax
  HANDLE v15; // rax
  _DWORD *v16; // rax
  int v17; // r9d
  unsigned __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned __int64 v20; // rdx
  unsigned int i; // r9d
  unsigned int v22; // eax
  size_t v23; // rdx
  unsigned int j; // r9d
  unsigned int v25; // eax
  const wchar_t *v26; // rcx
  unsigned __int64 v27; // rax
  __int64 v28; // r11
  _DWORD *v29; // rdx
  unsigned int v30; // r9d
  unsigned int k; // r8d
  unsigned int v32; // eax
  _DWORD *v33; // r8
  unsigned int m; // r10d
  unsigned int v35; // eax
  HANDLE v36; // rax
  HANDLE v37; // rax
  _DWORD *v38; // r8
  unsigned int v39; // r9d
  unsigned int n; // r10d
  unsigned int v41; // eax
  void *v42; // rax
  unsigned int v43; // r15d
  HANDLE v44; // rax
  _DWORD *v45; // r15
  HANDLE v46; // rax
  void *v47; // r8
  _DWORD *v48; // rax
  HANDLE v49; // rax
  unsigned int *v50; // rax
  HANDLE v51; // rax
  HANDLE v52; // rax
  HANDLE v53; // rax
  HANDLE v54; // rax
  HANDLE v55; // rax
  HANDLE v56; // rax
  LPVOID v57; // rax
  HANDLE v58; // rax
  HANDLE v59; // rax
  HANDLE v60; // rax
  HANDLE v61; // rax
  int *v62; // r15
  _DWORD *v63; // rax
  int ii; // r8d
  _DWORD *v65; // rdx
  int v66; // r8d
  char *v67; // r9
  __int64 v68; // rdx
  unsigned __int64 v69; // rax
  __m128 v70; // xmm1
  __m128 v71; // xmm2
  __m128 v72; // xmm0
  __m128 v73; // xmm0
  __m128 v74; // xmm1
  __m128 v75; // xmm1
  __m128 v76; // xmm1
  __m128 v77; // xmm1
  int v78; // edx
  char *v79; // r13
  unsigned __int8 *v80; // rsi
  SIZE_T v81; // rbx
  int v82; // r9d
  int v83; // r8d
  int v84; // r14d
  int v85; // r12d
  int v86; // eax
  int v87; // r11d
  int v88; // r10d
  int v89; // r11d
  int v90; // r10d
  int v91; // ecx
  int v92; // r8d
  int v93; // r9d
  int v94; // edx
  int v95; // r8d
  unsigned int v96; // ecx
  int v97; // edx
  int v98; // eax
  int v99; // ecx
  int v100; // edx
  int v101; // r8d
  int v102; // ecx
  unsigned int v103; // edx
  unsigned int v104; // r8d
  int v105; // ecx
  int v106; // edx
  int v107; // r8d
  int v108; // ecx
  int v109; // edx
  int v110; // r9d
  int v111; // ecx
  int v112; // r8d
  unsigned int v113; // edx
  int v114; // r9d
  int v115; // ecx
  unsigned int v116; // r8d
  int v117; // r8d
  HANDLE v118; // rax
  _DWORD *v119; // rax
  HANDLE v120; // rax
  void *v121; // rcx
  SIZE_T *v122; // rdx
  void *v123; // rax
  SIZE_T v124; // r15
  HANDLE v125; // rax
  _OWORD *v126; // rax
  HANDLE v127; // rax
  _QWORD *v128; // rax
  int v129; // r15d
  unsigned int *v130; // rax
  SIZE_T *v131; // r9
  HANDLE v132; // rax
  SIZE_T v133; // rax
  HANDLE v134; // rax
  HANDLE v135; // rax
  HANDLE v136; // rax
  HANDLE v137; // rax
  _QWORD *v138; // rax
  _DWORD *v139; // rcx
  unsigned int v140; // edx
  unsigned int v141; // r8d
  unsigned int v142; // edx
  unsigned int v143; // eax
  unsigned int v144; // r15d
  HANDLE v145; // rax
  _DWORD *v146; // rax
  HANDLE v147; // rax
  _DWORD *v148; // rcx
  SIZE_T v149; // rdx
  _DWORD *v150; // rcx
  unsigned int *v151; // rdx
  _DWORD *v152; // rax
  int v153; // r9d
  __int64 v154; // r11
  unsigned int *v155; // r8
  unsigned int *v156; // rdx
  unsigned int *v157; // r8
  _DWORD *v158; // r10
  __int64 v159; // rax
  LPVOID v160; // r9
  unsigned int v161; // r11d
  unsigned int v162; // ecx
  unsigned int v163; // eax
  unsigned int v164; // r15d
  HANDLE v165; // rax
  void *v166; // rax
  signed int LastError; // eax
  unsigned int v168; // r8d
  unsigned int *v169; // rcx
  size_t v170; // r9
  size_t v171; // r11
  unsigned int *v172; // r10
  unsigned int v173; // r9d
  SIZE_T v174; // r15
  unsigned int *v175; // r11
  unsigned int v176; // r10d
  unsigned __int64 v177; // r9
  unsigned int v178; // r11d
  unsigned int v179; // r9d
  unsigned int v180; // r10d
  int v181; // ecx
  SIZE_T v182; // r15
  FARPROC ProcAddress; // rax
  int v184; // eax
  HANDLE v185; // rax
  _QWORD *v186; // rax
  SIZE_T v187; // rcx
  HANDLE v188; // rax
  void *v189; // rcx
  SIZE_T v190; // rax
  size_t v191; // r8
  const void *v192; // rdx
  int v193; // r15d
  HANDLE v194; // rax
  void *v195; // rcx
  SIZE_T v196; // r8
  void *v197; // rdx
  unsigned __int64 v198; // rax
  HANDLE v199; // rax
  void *v200; // rcx
  LPVOID v201; // r8
  void *v202; // rdx
  SIZE_T *v203; // rax
  __int64 v204; // rcx
  SIZE_T v205; // r15
  void *v206; // rax
  unsigned int *v207; // rcx
  unsigned __int8 *v208; // rdx
  unsigned __int8 *v209; // r9
  _BYTE *v210; // r11
  unsigned int v211; // r10d
  unsigned int v212; // r9d
  unsigned int v213; // r8d
  int v214; // edi
  LPVOID v215; // rbx
  int v216; // r14d
  int v217; // r10d
  int v218; // r15d
  int v219; // r11d
  unsigned int v220; // edx
  int v221; // r8d
  unsigned int v222; // ecx
  int v223; // edx
  int v224; // r8d
  unsigned int v225; // ecx
  int v226; // edx
  int v227; // r9d
  int v228; // r10d
  unsigned int v229; // r8d
  int v230; // ecx
  int v231; // edx
  unsigned int v232; // r8d
  unsigned int v233; // ecx
  int v234; // edx
  int v235; // r8d
  int v236; // ecx
  int v237; // edx
  int v238; // r8d
  int v239; // r9d
  int v240; // ecx
  unsigned int v241; // edx
  int v242; // r9d
  _BYTE *v243; // rcx
  int v244; // r8d
  int v245; // eax
  unsigned __int8 v246; // r8
  HANDLE v247; // rax
  unsigned __int64 v248; // rax
  __m128 v249; // xmm1
  __m128 v250; // xmm2
  __m128 v251; // xmm0
  __m128 v252; // xmm0
  __m128 v253; // xmm1
  __m128 v254; // xmm1
  __m128 v255; // xmm1
  __m128 v256; // xmm1
  DWORD CurrentProcessId; // eax
  unsigned int v258; // ebx
  unsigned int v259; // eax
  int v260; // r15d
  _DWORD *v261; // r9
  void *v262; // r8
  int v263; // r11d
  int v264; // r15d
  _DWORD *v265; // r8
  unsigned int *v266; // r8
  unsigned __int64 v267; // r10
  void *v268; // r10
  unsigned int *v269; // rcx
  void *v270; // rdx
  HANDLE v271; // rax
  _DWORD *v272; // rax
  unsigned int jj; // r8d
  _DWORD *v274; // rdx
  int *v275; // r9
  int v276; // r15d
  unsigned int *v277; // rax
  unsigned int kk; // r8d
  size_t v279; // r9
  unsigned int *v280; // rdx
  SIZE_T v281; // r10
  unsigned int v282; // r8d
  unsigned int *v283; // rax
  __int64 v284; // r10
  unsigned int *v285; // rdx
  unsigned int *v286; // r8
  unsigned int v287; // r11d
  unsigned int *v288; // rax
  unsigned int mm; // r10d
  __int64 v290; // r8
  unsigned int *v291; // rdx
  int v292; // edi
  SC_HANDLE v293; // rdi
  DWORD v294; // eax
  DWORD v295; // eax
  PVOID *v296; // rcx
  __int64 v297; // rdx
  unsigned int *v298; // rcx
  SIZE_T v299; // rcx
  unsigned __int8 *v300; // rbx
  _QWORD *v301; // r12
  HANDLE v302; // rax
  unsigned __int8 *v303; // rax
  unsigned __int8 *v304; // r13
  HANDLE v305; // rax
  void *v306; // rsi
  int v307; // ebx
  void *v308; // rdi
  int v309; // ebx
  int v310; // eax
  void *v311; // rbx
  HANDLE v312; // rax
  void *v313; // rdi
  HANDLE v314; // rax
  void *v315; // rdi
  HANDLE v316; // rax
  void *v317; // rdi
  HANDLE v318; // rax
  HANDLE v319; // rax
  HANDLE v320; // rax
  void *v321; // rbx
  HANDLE v322; // rax
  _QWORD *v323; // rdi
  void *v324; // rbx
  HANDLE v325; // rax
  void *v326; // rbx
  HANDLE v327; // rax
  void *v328; // rbx
  HANDLE v329; // rax
  HANDLE v330; // rax
  void *v331; // rbx
  HANDLE v332; // rax
  unsigned int v333; // r9d
  void *v334; // rdi
  HANDLE v335; // rax
  HANDLE v336; // rax
  HANDLE v337; // rax
  HANDLE v338; // rax
  int v339; // ebx
  int v340; // r9d
  int v341; // r10d
  int v342; // r11d
  SIZE_T *v343; // rax
  __int64 v344; // rax
  unsigned __int64 v345; // rbx
  void *v346; // rax
  unsigned int v347; // r11d
  _BYTE *v348; // rcx
  unsigned __int8 *v349; // rdx
  _BYTE *v350; // r9
  unsigned int v351; // r10d
  unsigned int v352; // r8d
  SIZE_T v353; // rdi
  int v354; // r12d
  SIZE_T v355; // r14
  int v356; // r13d
  int v357; // r10d
  int v358; // r9d
  int v359; // ebx
  int v360; // r11d
  int v361; // edx
  int v362; // r8d
  unsigned int v363; // ecx
  int v364; // edx
  int v365; // r8d
  unsigned int v366; // ecx
  int v367; // edx
  int v368; // r9d
  int v369; // r10d
  unsigned int v370; // r8d
  int v371; // ecx
  int v372; // edx
  unsigned int v373; // r8d
  unsigned int v374; // ecx
  int v375; // edx
  unsigned int v376; // r8d
  int v377; // ecx
  unsigned int v378; // edx
  int v379; // r8d
  int v380; // r9d
  int v381; // ecx
  unsigned int v382; // edx
  int v383; // eax
  int v384; // ecx
  unsigned int v385; // ecx
  _BYTE *v386; // r12
  _QWORD *v387; // r13
  unsigned __int64 v388; // rax
  __m128 v389; // xmm1
  __m128 v390; // xmm2
  __m128 v391; // xmm0
  __m128 v392; // xmm0
  __m128 v393; // xmm1
  __m128 v394; // xmm1
  __m128 v395; // xmm1
  __m128 v396; // xmm1
  HANDLE v397; // rax
  void *v398; // rcx
  HANDLE v399; // rax
  unsigned int v400; // r9d
  int v401; // eax
  int v402; // r9d
  SIZE_T v403; // r8
  int v404; // edx
  unsigned __int64 v405; // rax
  unsigned __int64 v406; // rcx
  __m128 v407; // xmm1
  __m128 v408; // xmm2
  __m128 v409; // xmm0
  __m128 v410; // xmm0
  __m128 v411; // xmm1
  __m128 v412; // xmm1
  __m128 v413; // xmm1
  __m128 v414; // xmm1
  int v415; // r11d
  unsigned int v416; // edx
  LPVOID v417; // rsi
  int v418; // r8d
  unsigned __int8 *v419; // r14
  SIZE_T v420; // r15
  int v421; // ebx
  int v422; // r13d
  int v423; // r12d
  int v424; // eax
  int v425; // r11d
  int v426; // r10d
  int v427; // r11d
  int v428; // r10d
  int v429; // edx
  int v430; // r9d
  int v431; // edx
  int v432; // r9d
  int v433; // r8d
  int v434; // edx
  unsigned int v435; // ecx
  int v436; // r8d
  int v437; // eax
  int v438; // ecx
  int v439; // r8d
  int v440; // ecx
  unsigned int v441; // edx
  unsigned int v442; // r8d
  int v443; // ecx
  int v444; // edx
  int v445; // r8d
  int v446; // ecx
  int v447; // edx
  int v448; // r8d
  int v449; // ecx
  int v450; // edx
  unsigned int v451; // eax
  int v452; // r8d
  int v453; // ecx
  HANDLE v454; // rax
  LPVOID v455; // rdi
  HANDLE v456; // rax
  void *v457; // rax
  size_t v458; // r8
  const void *v459; // rdx
  HANDLE v460; // rax
  _OWORD *v461; // rax
  HANDLE v462; // rax
  _QWORD *v463; // rax
  unsigned int v464; // ebx
  HANDLE v465; // rax
  LPVOID v466; // rax
  _DWORD *v467; // r9
  _DWORD *v468; // rax
  unsigned int *v469; // r9
  unsigned int v470; // r10d
  unsigned int v471; // r11d
  __int64 v472; // rdx
  __int64 v473; // r9
  int v474; // r11d
  _DWORD *v475; // r9
  _OWORD *v476; // rax
  unsigned int *v477; // r9
  unsigned int v478; // r10d
  unsigned int v479; // r11d
  __int64 v480; // rdx
  __int64 v481; // r9
  int v482; // r11d
  _DWORD *v483; // r9
  _QWORD *v484; // rax
  unsigned int *v485; // r9
  unsigned int v486; // r10d
  unsigned int v487; // r11d
  __int64 v488; // rdx
  __int64 v489; // r9
  int v490; // r11d
  _DWORD *v491; // r9
  size_t *v492; // rax
  size_t v493; // rcx
  __int64 v494; // rcx
  unsigned int v495; // r9d
  unsigned int v496; // edx
  unsigned int v497; // ebx
  HANDLE v498; // rax
  char *v499; // rax
  char *v500; // rbx
  void *v501; // rax
  HANDLE v502; // rax
  HANDLE v503; // rax
  HANDLE v504; // rax
  HANDLE v505; // rax
  HANDLE v506; // rax
  __int64 v507; // rdx
  unsigned int v508; // ecx
  unsigned int v509; // ebx
  HANDLE v510; // rax
  _DWORD *v511; // rax
  SIZE_T v512; // rcx
  SIZE_T v513; // rcx
  HANDLE v514; // rax
  __int64 v515; // rcx
  unsigned int *v516; // rcx
  int nn; // r10d
  unsigned int v518; // ebx
  SIZE_T v519; // rcx
  unsigned int i1; // r10d
  int v521; // r9d
  unsigned int v522; // ecx
  unsigned int v523; // r10d
  unsigned int v524; // ebx
  HANDLE v525; // rax
  _DWORD *v526; // rax
  _DWORD *v527; // rbx
  FARPROC v528; // rax
  int v529; // eax
  unsigned int v530; // r9d
  SIZE_T *v531; // rcx
  int v532; // r9d
  SIZE_T v533; // r11
  unsigned int v534; // r10d
  unsigned int v535; // r11d
  int v536; // r9d
  int v537; // r9d
  SIZE_T v538; // r10
  unsigned int v539; // r10d
  int v540; // r9d
  int v541; // r9d
  unsigned int v542; // r10d
  bool v543; // sf
  unsigned int v544; // r11d
  int v545; // r10d
  unsigned int v546; // r11d
  int v547; // r10d
  HANDLE v548; // rax
  HANDLE v549; // rax
  void *v550; // rcx
  _QWORD *v551; // rax
  SIZE_T v552; // r8
  const void *v553; // rdx
  HANDLE v554; // rax
  void *v555; // rcx
  SIZE_T v556; // r8
  const void *v557; // rdx
  HANDLE v558; // rax
  void *v559; // rcx
  LPVOID v560; // r8
  const void *v561; // rdx
  HANDLE v562; // rax
  HANDLE v563; // rax
  HANDLE v564; // rax
  HANDLE v565; // rax
  int v566; // ecx
  unsigned int v567; // r9d
  unsigned int v568; // r11d
  _DWORD *v569; // r10
  __int64 v570; // r11
  const void *v571; // rdi
  void *v572; // rbx
  int v573; // esi
  SIZE_T v574; // r9
  int v575; // r10d
  LPVOID v576; // r10
  unsigned int *v577; // r9
  SIZE_T v578; // r10
  __int64 v579; // rdx
  __int64 v580; // r9
  HANDLE v581; // rax
  int v582; // eax
  int *v583; // rcx
  SIZE_T v584; // rcx
  int v585; // r9d
  unsigned int v586; // r10d
  int v587; // r9d
  int *v588; // rax
  HANDLE v589; // rax
  HANDLE v590; // rax
  HANDLE v591; // rax
  HANDLE v592; // rax
  SIZE_T v593; // rcx
  HANDLE v594; // rax
  HANDLE v595; // rax
  HANDLE v596; // rax
  HANDLE v597; // rax
  HANDLE v598; // rax
  HANDLE v599; // rax
  HANDLE v600; // rax
  HANDLE v601; // rax
  SIZE_T v602; // rcx
  HANDLE v603; // rax
  HANDLE v604; // rax
  HANDLE v605; // rax
  HANDLE v606; // rax
  int v607; // eax
  SIZE_T *v608; // rcx
  int v609; // edi
  int v610; // esi
  unsigned int v611; // ebx
  int v612; // ecx
  int v613; // eax
  int v614; // edx
  int v615; // ecx
  char v616; // r14
  HANDLE v617; // rax
  HANDLE v618; // rax
  unsigned int v619; // ecx
  unsigned __int8 *v620; // rsi
  int v621; // r15d
  int v622; // r13d
  int v623; // r10d
  char v624; // bl
  int v625; // r14d
  int v626; // ecx
  unsigned int v627; // r10d
  _BYTE *v628; // rdi
  int v629; // ecx
  unsigned int v630; // edx
  char v631; // r9
  unsigned int v632; // ecx
  int v633; // r8d
  int v634; // r11d
  int v635; // eax
  char v636; // r14
  int v637; // eax
  int v638; // ecx
  unsigned int v639; // r8d
  int v640; // r11d
  char v641; // di
  DWORD v642; // eax
  void *v643; // [rsp+30h] [rbp-D0h]
  LPVOID v644; // [rsp+30h] [rbp-D0h]
  LPVOID v645; // [rsp+30h] [rbp-D0h]
  _DWORD *v646; // [rsp+38h] [rbp-C8h]
  unsigned int v647; // [rsp+38h] [rbp-C8h]
  unsigned int v648; // [rsp+38h] [rbp-C8h]
  SIZE_T dwBytes; // [rsp+40h] [rbp-C0h]
  _DWORD *dwBytesa; // [rsp+40h] [rbp-C0h]
  unsigned int *v651; // [rsp+48h] [rbp-B8h]
  size_t cchMax[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v653; // [rsp+60h] [rbp-A0h]
  LPVOID v654; // [rsp+68h] [rbp-98h]
  LPVOID v655; // [rsp+70h] [rbp-90h]
  LPVOID v656; // [rsp+78h] [rbp-88h] BYREF
  void *v657; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v658; // [rsp+88h] [rbp-78h]
  unsigned int v659; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h]
  unsigned int v661; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v662; // [rsp+A8h] [rbp-58h]
  size_t v663[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v664; // [rsp+C0h] [rbp-40h]
  int v665; // [rsp+C8h] [rbp-38h]
  SIZE_T v666; // [rsp+D0h] [rbp-30h]
  LPVOID v667; // [rsp+D8h] [rbp-28h]
  _DWORD *v668; // [rsp+E0h] [rbp-20h] BYREF
  SIZE_T v669; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v670; // [rsp+F0h] [rbp-10h]
  size_t Size; // [rsp+F8h] [rbp-8h]
  SIZE_T v672; // [rsp+100h] [rbp+0h]
  LPVOID v673; // [rsp+108h] [rbp+8h]
  unsigned int v674; // [rsp+110h] [rbp+10h] BYREF
  _OWORD *v675; // [rsp+118h] [rbp+18h]
  void *v676; // [rsp+120h] [rbp+20h]
  SIZE_T v677; // [rsp+128h] [rbp+28h]
  int v678; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v679; // [rsp+138h] [rbp+38h]
  void *v680; // [rsp+140h] [rbp+40h]
  int v681; // [rsp+148h] [rbp+48h]
  size_t v682; // [rsp+150h] [rbp+50h] BYREF
  int v683; // [rsp+158h] [rbp+58h]
  unsigned int v684; // [rsp+15Ch] [rbp+5Ch] BYREF
  unsigned int v685; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v686; // [rsp+164h] [rbp+64h]
  size_t pcchLength; // [rsp+168h] [rbp+68h] BYREF
  LPVOID v688; // [rsp+170h] [rbp+70h]
  int *v689; // [rsp+178h] [rbp+78h]
  HMODULE phModule; // [rsp+180h] [rbp+80h] BYREF
  HMODULE hModule; // [rsp+188h] [rbp+88h] BYREF
  SC_HANDLE hSCObject; // [rsp+190h] [rbp+90h]
  RPC_BINDING_HANDLE Binding; // [rsp+198h] [rbp+98h] BYREF
  __int128 v694; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v695; // [rsp+1B0h] [rbp+B0h]
  __int128 v696; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v697; // [rsp+1D0h] [rbp+D0h]
  SIZE_T v698; // [rsp+260h] [rbp+160h] BYREF
  SIZE_T v699; // [rsp+268h] [rbp+168h] BYREF
  LPVOID lpMem; // [rsp+270h] [rbp+170h] BYREF
  SIZE_T v701; // [rsp+278h] [rbp+178h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v678 = 0;
  Binding = 0;
  LODWORD(v698) = 0;
  GetProcessLowBoxStatus(&v698);
  if ( !(_DWORD)v698 )
    DebugInitEx();
  if ( g_dwTraceId != -1 )
  {
    CurrentProcessId = GetCurrentProcessId();
    TracePrintfExA(g_dwTraceId, 0xCu, "RasInitialize called by %d", CurrentProcessId);
  }
  result = RasInitializeNoWait();
  v1 = result;
  if ( result )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return result;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_323;
    v3 = 80;
    goto LABEL_773;
  }
  hSCObject = OpenSCManagerA(0, 0, 1u);
  if ( hSCObject )
  {
    v4 = 0;
    v681 = 0;
    v689 = 0;
    v680 = LocalAlloc(0x40u, 4u);
    v5 = v680;
    if ( !v680 )
    {
      v14 = 0;
      v13 = -2147024882;
      goto LABEL_25;
    }
    v686 = 0;
    *(_OWORD *)cchMax = 0;
    v683 = 0;
    v6 = 0;
    v656 = 0;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
    LODWORD(v699) = -805306345;
    v675 = v8;
    v9 = v8;
    if ( !v8 )
    {
      v9 = 0;
      v13 = -1073741801;
      goto LABEL_21;
    }
    *v8 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
    v8[1] = xmmword_1800311A0;
    v8[2] = xmmword_1800311B0;
    v8[3] = xmmword_1800311C0;
    v8[4] = xmmword_1800311D0;
    v8[5] = xmmword_1800311E0;
    v8[6] = xmmword_1800311F0;
    v8[7] = xmmword_180031200;
    v8[8] = xmmword_180031210;
    v8[9] = xmmword_180031220;
    v10 = GetProcessHeap();
    v11 = (wchar_t *)HeapAlloc(v10, 8u, 8u);
    v12 = v11;
    if ( !v11 )
    {
      v13 = -1073741801;
      goto LABEL_21;
    }
    v6 = v11;
    *(_QWORD *)v11 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
    v679 = v11;
    v670 = __rdtsc();
    pcchLength = 0;
    if ( StringLengthWorkerW(v12, (unsigned __int64)HIDWORD(v670) << 32, &pcchLength) < 0 )
    {
      pcchLength = 0;
      v13 = -1073741762;
      goto LABEL_21;
    }
    if ( (unsigned int)(2 * ++pcchLength) >= 0xFFFFFFFC )
      goto LABEL_20;
    if ( (unsigned int)(2 * pcchLength + 200) < 0xC4
      || 2 * (int)pcchLength + 208 < (unsigned int)(2 * pcchLength + 200)
      || 2 * (int)pcchLength + 216 < (unsigned int)(2 * pcchLength + 208) )
    {
      goto LABEL_29;
    }
    HIDWORD(cchMax[0]) = 2 * pcchLength + 216;
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 8u, HIDWORD(cchMax[0]));
    if ( !v16 )
    {
      v13 = -1073741801;
      goto LABEL_21;
    }
    v17 = 0;
    LODWORD(lpMem) = 0;
    cchMax[1] = (size_t)v16;
    if ( v16 + 1 >= v16 )
    {
      if ( (unsigned __int64)(v16 + 2) > cchMax[1] + HIDWORD(cchMax[0]) )
      {
        v13 = -1073741789;
        goto LABEL_35;
      }
      *v16 = 4;
      v16[1] = 0;
      v18 = cchMax[1];
      if ( cchMax[1] )
      {
        while ( !v17 )
        {
          v19 = *(_DWORD *)v18 + 4;
          if ( *(_DWORD *)v18 >= 0xFFFFFFFC || v18 + v19 < v18 )
            goto LABEL_34;
          v18 += v19;
          ++v17;
        }
        if ( v18 + 4 < v18 )
          goto LABEL_34;
        if ( v18 + 164 > cchMax[1] + HIDWORD(cchMax[0]) )
        {
          v13 = -1073741789;
          goto LABEL_35;
        }
        *(_DWORD *)v18 = 160;
        *(_OWORD *)(v18 + 4) = *v9;
        *(_OWORD *)(v18 + 20) = v9[1];
        *(_OWORD *)(v18 + 36) = v9[2];
        *(_OWORD *)(v18 + 52) = v9[3];
        *(_OWORD *)(v18 + 68) = v9[4];
        *(_OWORD *)(v18 + 84) = v9[5];
        *(_OWORD *)(v18 + 100) = v9[6];
        *(_OWORD *)(v18 + 116) = v9[7];
        *(_OWORD *)(v18 + 132) = v9[8];
        *(_OWORD *)(v18 + 148) = v9[9];
      }
      else
      {
        LODWORD(v701) = 0;
        LODWORD(v698) = RtlUIntAdd(4, 160, &v701);
        v13 = v698;
        if ( (v698 & 0x80000000) != 0LL )
          goto LABEL_78;
        LODWORD(v698) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v701, (char *)cchMax + 4);
        v13 = v698;
        if ( (v698 & 0x80000000) != 0LL )
          goto LABEL_78;
      }
      v20 = cchMax[1];
      if ( cchMax[1] )
      {
        for ( i = 0; i < 2; ++i )
        {
          v22 = *(_DWORD *)v20 + 4;
          if ( *(_DWORD *)v20 >= 0xFFFFFFFC || v20 + v22 < v20 )
            goto LABEL_34;
          v20 += v22;
        }
        if ( v20 + 4 < v20 )
          goto LABEL_34;
        if ( v20 + 12 > cchMax[1] + HIDWORD(cchMax[0]) )
        {
          v13 = -1073741789;
          goto LABEL_35;
        }
        *(_DWORD *)v20 = 8;
        *(_QWORD *)(v20 + 4) = *(_QWORD *)v6;
      }
      else
      {
        LODWORD(v701) = 0;
        LODWORD(v698) = RtlUIntAdd(4, 8, &v701);
        v13 = v698;
        if ( (v698 & 0x80000000) != 0LL )
          goto LABEL_78;
        LODWORD(v698) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v701, (char *)cchMax + 4);
        v13 = v698;
        if ( (v698 & 0x80000000) != 0LL )
          goto LABEL_78;
      }
      v23 = cchMax[1];
      if ( cchMax[1] )
      {
        for ( j = 0; j < 3; ++j )
        {
          v25 = *(_DWORD *)v23 + 4;
          if ( *(_DWORD *)v23 >= 0xFFFFFFFC || v23 + v25 < v23 )
            goto LABEL_34;
          v23 += v25;
        }
        if ( v23 + 4 < v23 )
          goto LABEL_34;
        v26 = (const wchar_t *)(cchMax[1] + HIDWORD(cchMax[0]));
        if ( v23 + 12 > (unsigned __int64)v26 )
        {
          v13 = -1073741789;
          goto LABEL_35;
        }
        v27 = v670;
        *(_DWORD *)v23 = 8;
        *(_QWORD *)(v23 + 4) = v27;
      }
      else
      {
        LODWORD(v701) = 0;
        LODWORD(v698) = RtlUIntAdd(4, 8, &v701);
        v13 = v698;
        if ( (v698 & 0x80000000) != 0LL )
          goto LABEL_78;
        LODWORD(v698) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v701, (char *)cchMax + 4);
        v13 = v698;
        if ( (v698 & 0x80000000) != 0LL )
          goto LABEL_78;
      }
      LODWORD(cchMax[0]) = 4;
      v682 = 0;
      if ( StringLengthWorkerW(v26, v23, &v682) < 0 )
      {
        v682 = 0;
        v13 = -1073741762;
        goto LABEL_35;
      }
      if ( v682 + 1 >= v682 )
      {
        v28 = (unsigned int)(2 * ++v682);
        if ( (_DWORD)v28 )
        {
          v29 = (_DWORD *)cchMax[1];
          if ( cchMax[1] )
          {
            v30 = 4;
            for ( k = 0; k < 4; ++k )
            {
              v32 = *v29 + 4;
              if ( *v29 >= 0xFFFFFFFC || (_DWORD *)((char *)v29 + v32) < v29 )
                goto LABEL_71;
              v29 = (_DWORD *)((char *)v29 + v32);
            }
            if ( v29 + 1 < v29 )
            {
LABEL_71:
              v13 = -1073741675;
              LODWORD(v698) = -1073741675;
              goto LABEL_72;
            }
            if ( (unsigned __int64)v29 + v28 + 4 <= cchMax[1] + HIDWORD(cchMax[0]) )
            {
              *v29 = v28;
              v13 = 0;
              LODWORD(v698) = 0;
              memcpy_0(v29 + 1, L"RasBase-RasMobileCore", (unsigned int)v28);
              v30 = 5;
              LODWORD(cchMax[0]) = 5;
LABEL_72:
              if ( v13 < 0 )
                goto LABEL_79;
              v33 = (_DWORD *)cchMax[1];
              if ( cchMax[1] )
              {
                for ( m = 0; m < v30; ++m )
                {
                  v35 = *v33 + 4;
                  if ( *v33 >= 0xFFFFFFFC || (_DWORD *)((char *)v33 + v35) < v33 )
                    goto LABEL_77;
                  v33 = (_DWORD *)((char *)v33 + v35);
                }
                if ( v33 + 1 < v33 )
                {
LABEL_77:
                  v13 = -1073741675;
                  LODWORD(v698) = -1073741675;
                  goto LABEL_78;
                }
                if ( (unsigned __int64)(v33 + 2) > cchMax[1] + HIDWORD(cchMax[0]) )
                {
                  v13 = -1073741789;
                  goto LABEL_35;
                }
                *v33 = 4;
                v33[1] = 0;
              }
              else
              {
                LODWORD(v701) = 0;
                LODWORD(v698) = RtlUIntAdd(4, 4, &v701);
                v13 = v698;
                if ( (v698 & 0x80000000) != 0LL )
                  goto LABEL_78;
                LODWORD(v698) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v701, (char *)cchMax + 4);
                v13 = v698;
                if ( (v698 & 0x80000000) != 0LL )
                  goto LABEL_78;
              }
              v38 = (_DWORD *)cchMax[1];
              v39 = ++LODWORD(cchMax[0]);
              if ( cchMax[1] )
              {
                for ( n = 0; n < v39; ++n )
                {
                  v41 = *v38 + 4;
                  if ( *v38 >= 0xFFFFFFFC || (_DWORD *)((char *)v38 + v41) < v38 )
                    goto LABEL_77;
                  v38 = (_DWORD *)((char *)v38 + v41);
                }
                if ( v38 + 1 >= v38 )
                {
                  if ( (unsigned __int64)(v38 + 2) > cchMax[1] + HIDWORD(cchMax[0]) )
                  {
                    v13 = -1073741789;
                    goto LABEL_35;
                  }
                  *v38 = 4;
                  v38[1] = 4;
LABEL_103:
                  ++LODWORD(cchMax[0]);
                  v698 = __rdtsc();
                  if ( HIDWORD(cchMax[0]) < 0xFFFFFFF8 )
                  {
                    v42 = (void *)((HIDWORD(cchMax[0]) + 15) & 0xFFFFFFF8);
                    v657 = v42;
                    if ( (unsigned int)v42 >= HIDWORD(cchMax[0]) + 8 )
                    {
                      v43 = (HIDWORD(cchMax[0]) + 15) & 0xFFFFFFF8;
                      lpMem = (LPVOID)(unsigned int)v42;
                      v44 = GetProcessHeap();
                      v646 = HeapAlloc(v44, 8u, v43);
                      v45 = v646;
                      if ( !v646 )
                      {
                        v13 = -805306345;
                        LODWORD(v698) = -805306345;
                        goto LABEL_79;
                      }
                      *v646 = cchMax[0];
                      v665 = 0;
                      if ( v646 + 1 < v646 || (v646[1] = HIDWORD(cchMax[0]), v646 + 2 < v646 + 1) )
                      {
                        v13 = -805306219;
                        LODWORD(v698) = -805306219;
                        v46 = GetProcessHeap();
                        v47 = v646;
                        goto LABEL_134;
                      }
                      v651 = 0;
                      v643 = 0;
                      *(_QWORD *)((char *)v646 + (_QWORD)lpMem - 8) = v698;
                      v673 = 0;
                      v653 = 0;
                      v664 = 0;
                      memcpy_0(v646 + 2, (const void *)cchMax[1], HIDWORD(cchMax[0]));
                      if ( !(_DWORD)v657
                        || (dwBytes = (unsigned int)v657 + 8LL, Src = MemoryAlloc(dwBytes), (v67 = (char *)Src) == 0) )
                      {
                        v13 = -805306367;
                        LODWORD(v698) = -805306367;
                        goto LABEL_111;
                      }
                      v68 = (unsigned int)v657;
                      LOBYTE(v66) = 0;
                      v655 = 0;
                      LODWORD(v698) = v66;
                      v662 = (unsigned __int8 *)v646;
                      if ( (_DWORD)v657 )
                      {
                        v69 = 0;
                        if ( (unsigned int)v657 < 0x20uLL )
                          goto LABEL_966;
                        v662 = (unsigned __int8 *)v646;
                        v655 = 0;
                        v70 = 0;
                        v71 = 0;
                        do
                        {
                          v70 = _mm_xor_ps(v70, (__m128)_mm_loadu_si128((const __m128i *)((char *)v646 + v69)));
                          v72 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v646 + v69 + 16));
                          v69 += 32LL;
                          v73 = _mm_xor_ps(v72, v71);
                          v71 = v73;
                        }
                        while ( v69 < ((unsigned int)v657 & 0xFFFFFFE0) );
                        v74 = _mm_xor_ps(v70, v73);
                        v75 = _mm_xor_ps(v74, (__m128)_mm_srli_si128((__m128i)v74, 8));
                        v76 = _mm_xor_ps(v75, (__m128)_mm_srli_si128((__m128i)v75, 4));
                        v77 = _mm_xor_ps(v76, (__m128)_mm_srli_si128((__m128i)v76, 2));
                        v66 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v77, (__m128)_mm_srli_si128((__m128i)v77, 1)));
                        LODWORD(v698) = v66;
                        if ( v69 < (unsigned int)v657 )
                        {
LABEL_966:
                          do
                            LOBYTE(v66) = *((_BYTE *)v646 + v69++) ^ v66;
                          while ( v69 < (unsigned int)v657 );
                          LODWORD(v698) = v66;
                        }
                      }
                      v658 = (unsigned __int8 *)0xC81ECB17B1B54A58LL;
                      Size = (unsigned __int64)(unsigned int)v657 >> 3;
                      if ( Size )
                      {
                        v78 = HIDWORD(v658);
                        v79 = (char *)Src;
                        v80 = v662;
                        v81 = Size;
                        v82 = 0;
                        v659 = HIWORD(HIDWORD(v658));
                        v83 = -1;
                        LODWORD(v654) = 19032;
                        v661 = WORD1(v658);
                        v666 = 0;
                        v84 = WORD2(v658);
                        v85 = HIWORD(HIDWORD(v658));
                        LODWORD(lpMem) = 0;
                        LODWORD(v701) = 0;
                        v646 = v662;
                        do
                        {
                          v86 = *v80;
                          v87 = v80[1];
                          v88 = v80[4];
                          v80 += 8;
                          v89 = *(v80 - 5) | ((*(v80 - 6) | (((v86 << 8) | v87) << 8)) << 8);
                          v90 = *(v80 - 1) | ((*(v80 - 2) | ((*(v80 - 3) | (v88 << 8)) << 8)) << 8);
                          v91 = v83 ^ v90;
                          v92 = v82 ^ v89 ^ v78 ^ ((v83 ^ v90) - 19032);
                          v93 = v91 ^ (__ROR4__(v92, 7) + WORD1(v658) * __ROR4__(v78 ^ v92, 15));
                          v94 = v92 ^ (v84 * __ROR4__(v93 - 1313519016, 9) - __ROR4__(v93, 10));
                          v95 = v93 ^ (__ROR4__(v94, 27) + v85 * __ROR4__(v84 ^ v94, 28));
                          v96 = v94 ^ (HIDWORD(v658) - (v95 ^ 0xB1B54A58));
                          v97 = v95 ^ (WORD1(v658) * (v96 - 19032) - (v96 >> 6));
                          v98 = v96 ^ (19032 * (v84 ^ __ROR4__(v97, 15)));
                          v99 = v97 ^ (v84 * (v85 + __ROR4__(~v98, 3)));
                          v100 = v98 ^ (v99 - HIDWORD(v658) - 19032);
                          v101 = v99 ^ (v661 * (v100 ^ v659)) ^ __ROR4__(v100, 10);
                          v102 = v100 ^ __ROR4__(v101, 3) ^ (v84 * __ROR4__(v101 ^ 0x4A58, 26));
                          v103 = v101 ^ (19032 * (__ROR4__(v102, 15) - v85));
                          v104 = v102
                               ^ (19032 * (v103 ^ v659))
                               ^ ((v103 ^ (v103 >> 14)) >> 1)
                               ^ (19032 * ((8 * (v103 - v84)) | ((v103 - v84) >> 29)));
                          v105 = v103 ^ (WORD1(v658) * (v104 - v84) - (v104 >> 13));
                          v106 = v104 ^ __ROR4__(v105, 11) ^ (v84 * __ROR4__(-1313519016 - v105, 9));
                          v107 = v105 ^ (v106 + 1313519016 - v85);
                          v108 = v106 ^ (19032 * (v107 ^ WORD1(v658)) - __ROR4__(v107, 7));
                          v109 = v107 ^ (WORD1(v658) * __ROR4__(v108 ^ v659, 28) - __ROR4__(v108, 16));
                          v110 = v108 ^ (__ROR4__(v109, 4) + v84 * __ROR4__(-1313519016 - v109, 10));
                          v79 += 8;
                          v111 = v109 ^ __ROR4__(v110, 9) ^ (v85 * __ROR4__(v110 + 1313519016, 4));
                          v112 = v110 ^ (19032 * __ROR4__(v111 ^ HIDWORD(v658), 24) - __ROR4__(v111, 30));
                          v113 = v111 ^ (WORD1(v658) * __ROR4__(HIDWORD(v658) - v112, 11) - __ROR4__(v112, 12));
                          v114 = (int)lpMem;
                          LODWORD(lpMem) = v89;
                          v115 = v112 ^ (v113 >> 8) ^ (v84 * (v113 ^ WORD1(v658)));
                          v116 = v113 ^ 0xB1B54A58;
                          v82 = v115 ^ v114;
                          v78 = HIDWORD(v658);
                          v117 = v701 ^ HIDWORD(v658) ^ v116;
                          *(v79 - 5) = v82;
                          v83 = v115 ^ v117;
                          *(v79 - 1) = v83;
                          *(v79 - 6) = __ROR4__(v82, 8);
                          *(v79 - 2) = __ROR4__(v83, 8);
                          *(v79 - 7) = __ROR4__(v82, 16);
                          *(v79 - 3) = __ROR4__(v83, 16);
                          *(v79 - 8) = __ROR4__(v82, 24);
                          *(v79 - 4) = __ROR4__(v83, 24);
                          LODWORD(v701) = v90;
                          ++v666;
                        }
                        while ( v666 < v81 );
                        v4 = v689;
                        v5 = v680;
                        v9 = v675;
                        v6 = v679;
                        v45 = v646;
                        v68 = (unsigned int)v657;
                        v67 = (char *)Src;
                      }
                      else
                      {
                        v655 = 0;
                      }
                      *(_QWORD *)&v67[v68] = (unsigned __int8)v698;
                      v118 = GetProcessHeap();
                      v119 = HeapAlloc(v118, 8u, 0x30u);
                      v698 = (SIZE_T)v119;
                      if ( v119 )
                      {
                        *v119 = dwBytes;
                        v120 = GetProcessHeap();
                        v121 = HeapAlloc(v120, 8u, (unsigned int)dwBytes);
                        v122 = (SIZE_T *)(v698 + 8);
                        lpMem = (LPVOID)(v698 + 8);
                        v123 = v655;
                        if ( v121 )
                        {
                          *v122 = (SIZE_T)v121;
                          v655 = v123;
                          v646 = v45;
                          memcpy_0(v121, Src, (unsigned int)dwBytes);
                          v124 = v698;
                          *(_DWORD *)(v698 + 16) = 160;
                          v125 = GetProcessHeap();
                          v126 = HeapAlloc(v125, 8u, 0xA0u);
                          if ( v126 )
                          {
                            *(_QWORD *)(v124 + 24) = v126;
                            *v126 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                            v126[1] = xmmword_1800310F0;
                            v126[2] = xmmword_180031100;
                            v126[3] = xmmword_180031110;
                            v126[4] = xmmword_180031120;
                            v126[5] = xmmword_180031130;
                            v126[6] = xmmword_180031140;
                            v126[7] = xmmword_180031150;
                            v126[8] = xmmword_180031160;
                            v126[9] = xmmword_180031170;
                            *(_DWORD *)(v124 + 32) = 8;
                            v127 = GetProcessHeap();
                            v128 = HeapAlloc(v127, 8u, 8u);
                            if ( v128 )
                            {
                              *(_QWORD *)(v124 + 40) = v128;
                              *v128 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                              v651 = (unsigned int *)v124;
                              v129 = 0;
                              v655 = 0;
                              goto LABEL_202;
                            }
                          }
                          v122 = (SIZE_T *)lpMem;
                          v123 = v655;
                        }
                        v129 = -1073741801;
                        v655 = v123;
                        v701 = *v122;
                        if ( v701 )
                        {
                          v132 = GetProcessHeap();
                          HeapFree(v132, 0, (LPVOID)v701);
                          *(_QWORD *)lpMem = 0;
                        }
                        v133 = v698;
                        lpMem = *(LPVOID *)(v698 + 24);
                        if ( lpMem )
                        {
                          v134 = GetProcessHeap();
                          HeapFree(v134, 0, lpMem);
                          v133 = v698;
                          *(_QWORD *)(v698 + 24) = 0;
                        }
                        lpMem = *(LPVOID *)(v133 + 40);
                        if ( lpMem )
                        {
                          v135 = GetProcessHeap();
                          HeapFree(v135, 0, lpMem);
                          *(_QWORD *)(v698 + 40) = 0;
                        }
                        v136 = GetProcessHeap();
                        HeapFree(v136, 0, (LPVOID)v698);
                      }
                      else
                      {
                        v129 = -1073741801;
                      }
LABEL_202:
                      v137 = GetProcessHeap();
                      HeapFree(v137, 0, Src);
                      v138 = v655;
                      if ( v655 )
                      {
                        v698 = *((_QWORD *)v655 + 1);
                        if ( v698 )
                        {
                          v589 = GetProcessHeap();
                          HeapFree(v589, 0, (LPVOID)v698);
                          v138 = v655;
                          *((_QWORD *)v655 + 1) = 0;
                        }
                        v698 = v138[3];
                        if ( v698 )
                        {
                          v590 = GetProcessHeap();
                          HeapFree(v590, 0, (LPVOID)v698);
                          v138 = v655;
                          *((_QWORD *)v655 + 3) = 0;
                        }
                        v698 = v138[5];
                        if ( v698 )
                        {
                          v591 = GetProcessHeap();
                          HeapFree(v591, 0, (LPVOID)v698);
                          *((_QWORD *)v655 + 5) = 0;
                        }
                        v592 = GetProcessHeap();
                        HeapFree(v592, 0, v655);
                        v139 = v651;
                      }
                      else
                      {
                        v139 = v651;
                      }
                      v13 = v129 | 0x10000000;
                      LODWORD(v698) = v13;
                      if ( v13 < 0 )
                        goto LABEL_215;
                      if ( *v139 >= 0xFFFFFFFC
                        || (v140 = *v139 + 8, v140 < *v139 + 4)
                        || (v141 = v140 + v139[4], v141 < v140)
                        || (v142 = v141 + 4, v141 + 4 < v141)
                        || (v143 = v142 + v139[8], LODWORD(v701) = v143, v143 < v142) )
                      {
LABEL_214:
                        v13 = -805306219;
                        LODWORD(v698) = -805306219;
LABEL_215:
                        v48 = v646;
                        goto LABEL_216;
                      }
                      v144 = v143;
                      v145 = GetProcessHeap();
                      v146 = HeapAlloc(v145, 8u, v144);
                      lpMem = v146;
                      if ( !v146 )
                      {
                        v48 = v646;
                        v13 = -805306345;
                        LODWORD(v698) = -805306345;
                        goto LABEL_110;
                      }
                      *v146 = *v651;
                      v698 = (SIZE_T)(v146 + 1);
                      if ( v146 + 1 < v146 )
                        goto LABEL_212;
                      memcpy_0(v146 + 1, *((const void **)v651 + 1), *v651);
                      v148 = (_DWORD *)(v698 + *v651);
                      if ( (unsigned __int64)v148 < v698 )
                        goto LABEL_212;
                      *v148 = v651[4];
                      v698 = (SIZE_T)(v148 + 1);
                      if ( v148 + 1 < v148
                        || (memcpy_0(v148 + 1, *((const void **)v651 + 3), v651[4]),
                            v149 = v698,
                            v150 = (_DWORD *)(v698 + v651[4]),
                            v698 = (SIZE_T)v150,
                            (unsigned __int64)v150 < v149)
                        || (*v150 = v651[8], v150 + 1 < v150)
                        || (memcpy_0(v150 + 1, *((const void **)v651 + 5), v651[8]), v698 + 4 + v651[8] < v698 + 4) )
                      {
LABEL_212:
                        v13 = -805306219;
                        LODWORD(v698) = -805306219;
                        v147 = GetProcessHeap();
                        HeapFree(v147, 0, lpMem);
                        v48 = v646;
                        v643 = 0;
                        goto LABEL_110;
                      }
                      v151 = (unsigned int *)cchMax[1];
                      v152 = v646;
                      if ( cchMax[1] )
                      {
                        if ( LODWORD(cchMax[0]) <= 1 )
                        {
                          v13 = -1073741811;
                          v643 = lpMem;
                        }
                        else
                        {
                          v153 = 0;
                          v643 = lpMem;
                          while ( 1 )
                          {
                            v154 = *v151;
                            v155 = v151 + 1;
                            if ( v153 )
                              break;
                            if ( v155 < v151 )
                              goto LABEL_108;
                            v151 = (unsigned int *)((char *)v155 + v154);
                            if ( (unsigned int *)((char *)v155 + v154) < v155 )
                              goto LABEL_108;
                            v153 = 1;
                          }
                          if ( v155 < v151 )
                            goto LABEL_108;
                          v643 = lpMem;
                          if ( LODWORD(cchMax[0]) <= 2 )
                          {
                            v13 = -1073741811;
                            goto LABEL_109;
                          }
                          v156 = (unsigned int *)cchMax[1];
                          LODWORD(v698) = 0;
                          while ( 1 )
                          {
                            v157 = v156 + 1;
                            v158 = v152;
                            Src = v152;
                            v159 = *v156;
                            v160 = lpMem;
                            v654 = lpMem;
                            if ( (unsigned int)v698 >= 2 )
                              break;
                            if ( v157 < v156 )
                              goto LABEL_108;
                            v156 = (unsigned int *)((char *)v157 + v159);
                            if ( (unsigned int *)((char *)v157 + v159) < v157 )
                              goto LABEL_108;
                            LODWORD(v698) = v698 + 1;
                            v152 = v646;
                          }
                          if ( v157 < v156
                            || (v161 = v154 + 80, v161 < 0x50)
                            || (v162 = v161 + 4, v161 + 4 < v161)
                            || (v163 = v162 + v159, LODWORD(lpMem) = v163, v163 < v162) )
                          {
LABEL_108:
                            v13 = -1073741675;
                            goto LABEL_109;
                          }
                          if ( v163 <= 0x400000 )
                          {
                            v164 = v163;
                            v165 = GetProcessHeap();
                            v166 = HeapAlloc(v165, 8u, v164);
                            Size = (size_t)v166;
                            if ( !v166 )
                            {
                              v13 = -805306345;
                              LODWORD(v698) = -805306345;
                              v643 = v654;
                              v48 = Src;
                              goto LABEL_216;
                            }
                            v673 = v166;
                            phModule = 0;
                            v696 = 0;
                            v697 = 0;
                            if ( !v654 )
                            {
                              v48 = Src;
                              v13 = -2147024809;
                              v643 = 0;
                              LODWORD(v698) = -2147024809;
                              goto LABEL_216;
                            }
                            *(_QWORD *)&v696 = v654;
                            LODWORD(v697) = v701;
                            *((_QWORD *)&v696 + 1) = v166;
                            *(_QWORD *)((char *)&v697 + 4) = (unsigned int)lpMem;
                            if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule) )
                            {
                              ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation");
                              if ( ProcAddress )
                              {
                                v184 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, _QWORD))ProcAddress)(
                                         134,
                                         &v696,
                                         32,
                                         0);
                                v13 = v184 | 0x10000000;
                                LODWORD(v698) = v184 | 0x10000000;
                                if ( v184 >= 0 )
                                {
                                  v168 = DWORD1(v697);
                                  goto LABEL_248;
                                }
                                goto LABEL_246;
                              }
                              LastError = GetLastError();
                              LODWORD(v698) = LastError;
                              v13 = LastError;
                              if ( LastError <= 0 )
                              {
LABEL_245:
                                if ( v13 >= 0 )
                                {
                                  v13 = -2147467259;
                                  goto LABEL_315;
                                }
LABEL_246:
                                v168 = (unsigned int)lpMem;
                                if ( v13 != -805306333 )
                                {
                                  if ( v13 < 0 )
                                    goto LABEL_812;
LABEL_248:
                                  v169 = v651;
                                  if ( v168 < 4 )
                                  {
                                    v13 = -805306306;
                                    v643 = v654;
                                    goto LABEL_267;
                                  }
                                  v646 = Src;
                                  v643 = v654;
                                  v170 = *(unsigned int *)Size;
                                  v171 = Size + 4;
                                  LODWORD(v698) = *(_DWORD *)Size;
                                  v666 = Size + 4;
                                  if ( Size + 4 < Size )
                                    goto LABEL_213;
                                  if ( v168 - 4 < (unsigned int)v170 )
                                  {
                                    v13 = -805306306;
                                    v643 = v654;
                                    goto LABEL_313;
                                  }
                                  v172 = (unsigned int *)(v170 + v171);
                                  Size = v170;
                                  if ( v170 + v171 < v171 )
                                    goto LABEL_213;
                                  v173 = v170 + 4;
                                  if ( v173 < 4 )
                                    goto LABEL_213;
                                  if ( v168 - v173 < 4 )
                                  {
                                    v13 = -805306306;
                                    v643 = v654;
                                    goto LABEL_313;
                                  }
                                  v174 = *v172;
                                  v175 = v172 + 1;
                                  LODWORD(lpMem) = *v172;
                                  v657 = v172 + 1;
                                  if ( v172 + 1 < v172 )
                                    goto LABEL_213;
                                  v176 = v173 + 4;
                                  if ( v173 + 4 < v173 )
                                    goto LABEL_213;
                                  if ( v168 - v176 < (unsigned int)v174 )
                                  {
                                    v13 = -805306306;
                                    v643 = v654;
                                    goto LABEL_313;
                                  }
                                  v177 = (unsigned __int64)v175 + v174;
                                  v672 = v174;
                                  if ( (unsigned int *)((char *)v175 + v174) < v175 )
                                    goto LABEL_213;
                                  v178 = v176 + v174;
                                  if ( v176 + (unsigned int)v174 < v176 )
                                    goto LABEL_213;
                                  if ( v168 - v178 < 4 )
                                  {
                                    v13 = -805306306;
                                    v643 = v654;
                                    goto LABEL_313;
                                  }
                                  v676 = (void *)(v177 + 4);
                                  if ( v177 + 4 < v177 || (v179 = v178 + 4, v178 + 4 < v178) )
                                  {
LABEL_213:
                                    v643 = v654;
                                    goto LABEL_214;
                                  }
                                  v180 = *(_DWORD *)((char *)v657 + v174);
                                  LODWORD(v701) = v180;
                                  if ( v168 - v179 >= v180 )
                                  {
                                    if ( v179 + v180 >= v179 )
                                    {
                                      if ( v168 != v179 + v180 )
                                      {
                                        v13 = -805306306;
                                        v643 = v654;
                                        goto LABEL_267;
                                      }
                                      v181 = v180 + v174;
                                      v182 = (unsigned int)v698;
                                      if ( (unsigned int)(v698 + v181) + 12LL != v168 )
                                      {
                                        v13 = -805306306;
                                        v643 = v654;
LABEL_267:
                                        LODWORD(v698) = v13;
LABEL_268:
                                        v48 = Src;
                                        v646 = Src;
                                        goto LABEL_110;
                                      }
                                      v185 = GetProcessHeap();
                                      v186 = HeapAlloc(v185, 8u, 0x30u);
                                      v698 = (SIZE_T)v186;
                                      v187 = (SIZE_T)v186;
                                      if ( !v186 )
                                      {
                                        v13 = -805306345;
                                        LODWORD(v698) = -805306345;
                                        goto LABEL_812;
                                      }
                                      if ( v666 )
                                      {
                                        *(_DWORD *)v186 = v182;
                                        v188 = GetProcessHeap();
                                        v189 = HeapAlloc(v188, 8u, v182);
                                        v190 = v698;
                                        if ( !v189 )
                                        {
                                          v608 = (SIZE_T *)(v698 + 8);
                                          v662 = (unsigned __int8 *)(v698 + 8);
LABEL_745:
                                          v193 = -1073741801;
                                          v593 = *v608;
                                          lpMem = 0;
                                          v701 = v593;
                                          if ( v593 )
                                          {
                                            v594 = GetProcessHeap();
                                            HeapFree(v594, 0, (LPVOID)v701);
                                            *(_QWORD *)v662 = 0;
                                            v190 = v698;
                                          }
                                          v701 = *(_QWORD *)(v190 + 24);
                                          if ( v701 )
                                          {
                                            v595 = GetProcessHeap();
                                            HeapFree(v595, 0, (LPVOID)v701);
                                            v190 = v698;
                                            *(_QWORD *)(v698 + 24) = 0;
                                          }
                                          v701 = *(_QWORD *)(v190 + 40);
                                          if ( v701 )
                                          {
                                            v596 = GetProcessHeap();
                                            HeapFree(v596, 0, (LPVOID)v701);
                                            *(_QWORD *)(v698 + 40) = 0;
                                          }
                                          v597 = GetProcessHeap();
                                          HeapFree(v597, 0, (LPVOID)v698);
                                          v203 = (SIZE_T *)lpMem;
                                          goto LABEL_283;
                                        }
                                        v191 = Size;
                                        v192 = (const void *)v666;
                                        v193 = 0;
                                        v662 = (unsigned __int8 *)(v698 + 8);
                                        *(_QWORD *)(v698 + 8) = v189;
                                        memcpy_0(v189, v192, v191);
                                        v187 = v698;
                                      }
                                      else
                                      {
                                        v193 = 0;
                                        *(_DWORD *)v186 = 0;
                                        v662 = (unsigned __int8 *)(v186 + 1);
                                        v186[1] = 0;
                                      }
                                      if ( v657 )
                                      {
                                        *(_DWORD *)(v187 + 16) = (_DWORD)lpMem;
                                        v194 = GetProcessHeap();
                                        v195 = HeapAlloc(v194, 8u, v672);
                                        v190 = v698;
                                        if ( !v195 )
                                        {
LABEL_815:
                                          v608 = (SIZE_T *)v662;
                                          goto LABEL_745;
                                        }
                                        v196 = v672;
                                        v197 = v657;
                                        *(_QWORD *)(v698 + 24) = v195;
                                        memcpy_0(v195, v197, v196);
                                        v187 = v698;
                                      }
                                      else
                                      {
                                        *(_DWORD *)(v187 + 16) = 0;
                                        *(_QWORD *)(v187 + 24) = 0;
                                      }
                                      if ( !v676 )
                                      {
                                        *(_DWORD *)(v187 + 32) = 0;
                                        *(_QWORD *)(v187 + 40) = 0;
                                        goto LABEL_282;
                                      }
                                      v198 = (unsigned int)v701;
                                      *(_DWORD *)(v187 + 32) = v701;
                                      lpMem = (LPVOID)v198;
                                      v199 = GetProcessHeap();
                                      v200 = HeapAlloc(v199, 8u, (SIZE_T)lpMem);
                                      if ( v200 )
                                      {
                                        v201 = lpMem;
                                        v202 = v676;
                                        *(_QWORD *)(v698 + 40) = v200;
                                        memcpy_0(v200, v202, (size_t)v201);
                                        v187 = v698;
LABEL_282:
                                        v203 = (SIZE_T *)v187;
                                        lpMem = (LPVOID)v187;
LABEL_283:
                                        if ( v193 >= 0 )
                                        {
                                          v653 = v203;
                                        }
                                        else
                                        {
                                          if ( v203 )
                                          {
                                            v698 = v203[1];
                                            if ( v698 )
                                            {
                                              v598 = GetProcessHeap();
                                              HeapFree(v598, 0, (LPVOID)v698);
                                              v203 = (SIZE_T *)lpMem;
                                              *((_QWORD *)lpMem + 1) = 0;
                                            }
                                            v698 = v203[3];
                                            if ( v698 )
                                            {
                                              v599 = GetProcessHeap();
                                              HeapFree(v599, 0, (LPVOID)v698);
                                              v203 = (SIZE_T *)lpMem;
                                              *((_QWORD *)lpMem + 3) = 0;
                                            }
                                            v698 = v203[5];
                                            if ( v698 )
                                            {
                                              v600 = GetProcessHeap();
                                              HeapFree(v600, 0, (LPVOID)v698);
                                              *((_QWORD *)lpMem + 5) = 0;
                                            }
                                            v601 = GetProcessHeap();
                                            HeapFree(v601, 0, lpMem);
                                          }
                                          v203 = (SIZE_T *)v653;
                                        }
                                        v13 = v193 | 0x10000000;
                                        LODWORD(v698) = v13;
                                        if ( v13 >= 0 )
                                        {
                                          if ( v203 )
                                          {
                                            v662 = (unsigned __int8 *)v203[1];
                                            if ( v662 )
                                            {
                                              v204 = *(unsigned int *)v203;
                                              if ( (_DWORD)v204 )
                                              {
                                                v205 = v204 - 8;
                                                v669 = v204 - 8;
                                                v206 = MemoryAlloc(v204 - 8);
                                                v657 = v206;
                                                v207 = (unsigned int *)v206;
                                                if ( !v206 )
                                                {
                                                  v643 = v654;
                                                  v646 = Src;
                                                  goto LABEL_301;
                                                }
                                                v208 = v662;
                                                LOBYTE(v659) = 0;
                                                v209 = v662;
                                                Size = 0x7F1137FAB69605ELL;
                                                v210 = v206;
                                                v658 = v662;
                                                v655 = v206;
                                                v211 = v205 & 7;
                                                if ( (v205 & 7) == 0 )
                                                {
                                                  v212 = 0;
                                                  LODWORD(lpMem) = v205 & 7;
                                                  v213 = 0;
                                                  LODWORD(v701) = -1;
                                                  goto LABEL_293;
                                                }
                                                v609 = 0;
                                                v610 = 0;
                                                v611 = 0;
                                                do
                                                {
                                                  v612 = *v209++;
                                                  LODWORD(v698) = v612;
                                                  LODWORD(lpMem) = 8 * v611;
                                                  if ( v611 >= 4 )
                                                  {
                                                    LODWORD(v698) = (_DWORD)v698 << (56 - (_BYTE)lpMem);
                                                    v610 |= v698;
                                                  }
                                                  else
                                                  {
                                                    LODWORD(v698) = (_DWORD)v698 << (24 - (_BYTE)lpMem);
                                                    v609 |= v698;
                                                  }
                                                  ++v611;
                                                }
                                                while ( (int)v611 < (int)v211 );
                                                v4 = v689;
                                                v613 = v609 ^ 0x92F65A5;
                                                LODWORD(v701) = v610;
                                                v614 = v610 ^ 0x699A899C;
                                                LODWORD(lpMem) = v609;
                                                v658 = v209;
                                                v213 = v609 ^ 0x92F65A5;
                                                v615 = (int)v689;
                                                do
                                                {
                                                  v698 = (SIZE_T)(v210 + 1);
                                                  if ( v615 >= 4 )
                                                  {
                                                    v614 = __ROR4__(v614, 24);
                                                    v616 = v614;
                                                  }
                                                  else
                                                  {
                                                    v613 = __ROR4__(v613, 24);
                                                    v616 = v613;
                                                  }
                                                  *v210 = v616;
                                                  ++v615;
                                                  v210 = (_BYTE *)v698;
                                                }
                                                while ( v615 < (int)v211 );
                                                v655 = (LPVOID)v698;
                                                v5 = v680;
                                                if ( v211 <= 4 )
                                                {
                                                  v212 = 0;
                                                  if ( v211 < 4 )
                                                  {
                                                    v208 = v662;
                                                    v213 = v213 >> (8 * (4 - v211)) << (8 * (4 - v211));
                                                    goto LABEL_834;
                                                  }
                                                }
                                                else
                                                {
                                                  v212 = (v610 ^ 0x699A899Cu) >> (8 * (8 - v211)) << (8 * (8 - v211));
                                                }
                                                v208 = v662;
LABEL_834:
                                                v207 = (unsigned int *)v657;
LABEL_293:
                                                v688 = (LPVOID)(v205 >> 3);
                                                if ( v205 >> 3 )
                                                {
                                                  v214 = HIDWORD(Size);
                                                  v215 = v688;
                                                  LODWORD(v698) = 24670;
                                                  v216 = HIWORD(HIDWORD(Size));
                                                  v217 = WORD2(Size);
                                                  v661 = HIDWORD(Size) ^ 0xAB69605E;
                                                  v666 = 0;
                                                  LODWORD(v654) = WORD2(Size);
                                                  do
                                                  {
                                                    v218 = v658[3] | ((v658[2] | ((v658[1] | (*v658 << 8)) << 8)) << 8);
                                                    v219 = v658[7]
                                                         | ((v658[6] | ((v658[5] | (v658[4] << 8)) << 8)) << 8);
                                                    v658 += 8;
                                                    v220 = v214 ^ v212 ^ v219 ^ v213 ^ v218 ^ 0xAB69605E;
                                                    v221 = v213
                                                         ^ v218
                                                         ^ (__ROR4__(v220, 22) + v217 * __ROR4__(v220 + 1419157410, 27));
                                                    v222 = v220
                                                         ^ (43881 * __ROR4__(v214 + v221, 9) - __ROR4__(v221, 30));
                                                    v223 = v221 ^ (v698 * (v222 - v217) - (v222 >> 13));
                                                    v224 = v222
                                                         ^ (v216 * __ROR4__(v223 ^ 0xAB69, 26) - __ROR4__(v223, 30));
                                                    v225 = v223 ^ (v214 - (v224 ^ 0xAB69605E));
                                                    v226 = v224 ^ (43881 * (v225 ^ v217)) ^ __ROR4__(v225, 6);
                                                    v227 = v225
                                                         ^ (__ROR4__(v226, 30) + v698 * __ROR4__(v214 + v226, 15));
                                                    v228 = v226
                                                         ^ (v216 * __ROR4__(v227 + 1419157410, 14) - __ROR4__(v227, 24));
                                                    v229 = v227
                                                         ^ __ROR4__(v228, 10)
                                                         ^ ((_DWORD)v654 * __ROR4__(v228 ^ 0xAB69605E, 12));
                                                    v230 = v228 ^ (v229 >> 10) ^ (43881 * (v216 ^ v229));
                                                    v217 = (int)v654;
                                                    v231 = v229 ^ (v216 * (v698 + __ROR4__(~v230, 5)));
                                                    v232 = v230 ^ (v231 - v216) ^ 0xAB69605E;
                                                    v233 = v231
                                                         ^ ((v232 >> 2) + (_DWORD)v654 * __ROR4__(v216 ^ v232, 30));
                                                    v234 = v232
                                                         ^ (__ROR4__(v233, 25) + 43881 * __ROR4__(v233 - v214, 6));
                                                    v235 = v233
                                                         ^ (v698 * (v234 ^ (unsigned int)v654) + __ROR4__(v234, 9));
                                                    v236 = v234
                                                         ^ (__ROR4__(v235, 25) + v216 * __ROR4__(v235 ^ 0xAB69, 27));
                                                    v237 = v235 ^ v236 ^ v661;
                                                    v238 = v236 ^ ((_DWORD)v654 * (__ROR4__(v237, 3) - 43881));
                                                    v239 = v237 ^ (v698 * __ROR4__(v238 - v214, 1) - __ROR4__(v238, 6));
                                                    v240 = v238
                                                         ^ (__ROR4__(v239, 18) + v216 * __ROR4__(v239 - 1419157410, 29));
                                                    v241 = v239
                                                         ^ ((_DWORD)v654 * __ROR4__(v240 - 1419157410, 17)
                                                          - __ROR4__(v240, 14));
                                                    v242 = v240 ^ (v241 >> 3) ^ (43881 * (v241 ^ v698));
                                                    v243 = v655;
                                                    v244 = v242 ^ v214;
                                                    v245 = v242;
                                                    v212 = v701 ^ v242;
                                                    LODWORD(v701) = v219;
                                                    v213 = (unsigned int)lpMem
                                                         ^ v241
                                                         ^ __ROR4__(v245, 30)
                                                         ^ (v698 * __ROR4__(v244, 28));
                                                    *((_BYTE *)v655 + 3) = v213;
                                                    v243[7] = v212;
                                                    v243[2] = __ROR4__(v213, 8);
                                                    v243[6] = __ROR4__(v212, 8);
                                                    v243[1] = __ROR4__(v213, 16);
                                                    v243[5] = __ROR4__(v212, 16);
                                                    *v243 = __ROR4__(v213, 24);
                                                    v243[4] = __ROR4__(v212, 24);
                                                    LODWORD(lpMem) = v218;
                                                    v655 = v243 + 8;
                                                    ++v666;
                                                  }
                                                  while ( v666 < (unsigned __int64)v215 );
                                                  v4 = v689;
                                                  v5 = v680;
                                                  v9 = v675;
                                                  v6 = v679;
                                                  v205 = v669;
                                                  v207 = (unsigned int *)v657;
                                                  v208 = v662;
                                                }
                                                if ( !v205 )
                                                {
                                                  v246 = v659;
                                                  goto LABEL_299;
                                                }
                                                v248 = 0;
                                                if ( v205 >= 0x20 )
                                                {
                                                  v249 = 0;
                                                  v250 = 0;
                                                  do
                                                  {
                                                    v249 = _mm_xor_ps(
                                                             v249,
                                                             (__m128)_mm_loadu_si128((const __m128i *)((char *)v207 + v248)));
                                                    v251 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v207 + v248 + 16));
                                                    v248 += 32LL;
                                                    v252 = _mm_xor_ps(v251, v250);
                                                    v250 = v252;
                                                  }
                                                  while ( v248 < (v205 & 0xFFFFFFFFFFFFFFE0uLL) );
                                                  v253 = _mm_xor_ps(v249, v252);
                                                  v254 = _mm_xor_ps(v253, (__m128)_mm_srli_si128((__m128i)v253, 8));
                                                  v255 = _mm_xor_ps(v254, (__m128)_mm_srli_si128((__m128i)v254, 4));
                                                  v256 = _mm_xor_ps(v255, (__m128)_mm_srli_si128((__m128i)v255, 2));
                                                  v246 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                      v256,
                                                                                      (__m128)_mm_srli_si128(
                                                                                                (__m128i)v256,
                                                                                                1)));
                                                  if ( v248 >= v205 )
                                                  {
LABEL_299:
                                                    if ( v246 != *(_QWORD *)&v208[v205] )
                                                    {
                                                      v247 = GetProcessHeap();
                                                      HeapFree(v247, 0, v657);
LABEL_301:
                                                      v48 = v646;
                                                      v13 = -805306367;
                                                      LODWORD(v698) = -805306367;
                                                      goto LABEL_110;
                                                    }
                                                    v664 = v207;
                                                    v266 = v207;
                                                    if ( (unsigned int)v205 >= 4 )
                                                    {
                                                      v298 = v207 + 1;
                                                      if ( v298 < v266 )
                                                        goto LABEL_331;
                                                      if ( (unsigned int)(v205 - 4) < 4 )
                                                      {
                                                        v260 = -1073741762;
                                                        goto LABEL_332;
                                                      }
                                                      v261 = v298 + 1;
                                                      v666 = (SIZE_T)(v298 + 1);
                                                      if ( v298 + 1 < v298 )
                                                      {
                                                        v48 = v646;
LABEL_340:
                                                        v13 = -805306219;
                                                        LODWORD(v698) = -805306219;
                                                        goto LABEL_110;
                                                      }
                                                      v299 = *v298;
                                                      LODWORD(lpMem) = v299;
                                                      if ( (int)v205 - 8 < (unsigned int)v299 )
                                                      {
                                                        v260 = -1073741762;
                                                        goto LABEL_332;
                                                      }
                                                      if ( (unsigned int)v299 >= 0xFFFFFFF8 )
                                                        goto LABEL_331;
                                                      v267 = (unsigned __int64)v261 + v299;
                                                      v672 = v299;
                                                      if ( (char *)v266 + (unsigned int)v205 >= (char *)v261 + v299
                                                        && (unsigned __int64)v266
                                                         + (unsigned int)v205
                                                         - v299
                                                         - (_QWORD)v261 < 8 )
                                                      {
                                                        LODWORD(v698) = 0;
                                                        v263 = 0;
                                                        if ( !v261 )
                                                        {
                                                          v264 = 0;
LABEL_347:
                                                          v268 = 0;
                                                          LODWORD(v701) = *v266;
                                                          v676 = 0;
                                                          if ( !(_DWORD)lpMem )
                                                          {
LABEL_348:
                                                            v48 = v646;
                                                            v269 = v651;
                                                            v270 = v643;
                                                            v262 = v653;
                                                            if ( v261 )
                                                            {
                                                              memcpy_0(v268, v261, v672);
                                                              v48 = v646;
                                                              v269 = v651;
                                                              v270 = v643;
                                                              v262 = v653;
                                                              v263 = v698;
                                                              v268 = v676;
                                                            }
                                                            v656 = v268;
                                                            v665 = v263;
                                                            if ( (_DWORD)v701 == v263 )
                                                            {
LABEL_841:
                                                              v13 = v264 | 0x10000000;
                                                              v653 = v262;
                                                              LODWORD(v698) = v13;
                                                              v643 = v270;
                                                              v651 = v269;
                                                              v646 = v48;
                                                            }
                                                            else
                                                            {
                                                              v13 = -805306306;
                                                              LODWORD(v698) = -805306306;
                                                            }
LABEL_110:
                                                            if ( !v48 )
                                                            {
LABEL_112:
                                                              v50 = v651;
                                                              if ( v651 )
                                                              {
                                                                lpMem = (LPVOID)*((_QWORD *)v651 + 1);
                                                                if ( lpMem )
                                                                {
                                                                  v51 = GetProcessHeap();
                                                                  HeapFree(v51, 0, lpMem);
                                                                  v50 = v651;
                                                                  *((_QWORD *)v651 + 1) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v50 + 3);
                                                                if ( lpMem )
                                                                {
                                                                  v52 = GetProcessHeap();
                                                                  HeapFree(v52, 0, lpMem);
                                                                  v50 = v651;
                                                                  *((_QWORD *)v651 + 3) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v50 + 5);
                                                                if ( lpMem )
                                                                {
                                                                  v53 = GetProcessHeap();
                                                                  HeapFree(v53, 0, lpMem);
                                                                  *((_QWORD *)v651 + 5) = 0;
                                                                }
                                                                v54 = GetProcessHeap();
                                                                HeapFree(v54, 0, v651);
                                                              }
                                                              if ( v643 )
                                                              {
                                                                v55 = GetProcessHeap();
                                                                HeapFree(v55, 0, v643);
                                                              }
                                                              if ( v673 )
                                                              {
                                                                v56 = GetProcessHeap();
                                                                HeapFree(v56, 0, v673);
                                                              }
                                                              v57 = v653;
                                                              if ( v653 )
                                                              {
                                                                lpMem = (LPVOID)*((_QWORD *)v653 + 1);
                                                                if ( lpMem )
                                                                {
                                                                  v58 = GetProcessHeap();
                                                                  HeapFree(v58, 0, lpMem);
                                                                  v57 = v653;
                                                                  *((_QWORD *)v653 + 1) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v57 + 3);
                                                                if ( lpMem )
                                                                {
                                                                  v59 = GetProcessHeap();
                                                                  HeapFree(v59, 0, lpMem);
                                                                  v57 = v653;
                                                                  *((_QWORD *)v653 + 3) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v57 + 5);
                                                                if ( lpMem )
                                                                {
                                                                  v60 = GetProcessHeap();
                                                                  HeapFree(v60, 0, lpMem);
                                                                  *((_QWORD *)v653 + 5) = 0;
                                                                }
                                                                v61 = GetProcessHeap();
                                                                HeapFree(v61, 0, v653);
                                                              }
                                                              if ( !v664 )
                                                              {
LABEL_135:
                                                                if ( v13 < 0 )
                                                                  goto LABEL_79;
                                                                if ( !v665 )
                                                                {
                                                                  v13 = -1073425151;
                                                                  goto LABEL_21;
                                                                }
                                                                if ( !v656 )
                                                                {
                                                                  v13 = -1073741811;
                                                                  LODWORD(v698) = -1073741811;
                                                                  goto LABEL_79;
                                                                }
                                                                if ( (char *)v656 + 4 < v656 )
                                                                  goto LABEL_20;
                                                                v62 = 0;
                                                                if ( *(_DWORD *)v656 )
                                                                  v62 = (int *)((char *)v656 + 4);
                                                                if ( *(_DWORD *)v656 != 4 )
                                                                {
                                                                  v13 = -1073741789;
                                                                  goto LABEL_21;
                                                                }
                                                                v13 = *v62;
                                                                LODWORD(v698) = v13;
                                                                if ( v13 == -805306333 )
                                                                {
                                                                  LODWORD(lpMem) = -2147024774;
                                                                }
                                                                else
                                                                {
                                                                  LODWORD(lpMem) = v13;
                                                                  if ( v13 != -2147024774 && v13 < 0 )
                                                                    goto LABEL_79;
                                                                }
                                                                if ( v665 != 6 )
                                                                {
                                                                  v13 = -1073425151;
                                                                  goto LABEL_21;
                                                                }
                                                                v63 = v656;
                                                                for ( ii = 0; ; ii = 1 )
                                                                {
                                                                  v65 = v63 + 1;
                                                                  if ( ii )
                                                                    break;
                                                                  if ( v65 < v63 )
                                                                    goto LABEL_20;
                                                                  v63 = (_DWORD *)((char *)v65 + (unsigned int)*v63);
                                                                  if ( v63 < v65 )
                                                                    goto LABEL_20;
                                                                }
                                                                if ( v65 < v63 )
                                                                  goto LABEL_20;
                                                                v131 = 0;
                                                                if ( *v63 )
                                                                  v131 = (SIZE_T *)(v63 + 1);
                                                                if ( *v63 != 8 )
                                                                {
                                                                  v13 = -1073741789;
                                                                  goto LABEL_21;
                                                                }
                                                                v272 = v656;
                                                                v698 = *v131;
                                                                for ( jj = 0; ; ++jj )
                                                                {
                                                                  v274 = v272 + 1;
                                                                  if ( jj >= 2 )
                                                                    break;
                                                                  if ( v274 < v272 )
                                                                    goto LABEL_20;
                                                                  v272 = (_DWORD *)((char *)v274 + (unsigned int)*v272);
                                                                  if ( v272 < v274 )
                                                                    goto LABEL_20;
                                                                }
                                                                if ( v274 < v272 )
                                                                  goto LABEL_20;
                                                                v275 = 0;
                                                                if ( *v272 )
                                                                  v275 = v272 + 1;
                                                                if ( *v272 != 4 )
                                                                {
                                                                  v13 = -1073741789;
                                                                  goto LABEL_21;
                                                                }
                                                                v276 = *v275;
                                                                v277 = (unsigned int *)v656;
                                                                for ( kk = 0; ; ++kk )
                                                                {
                                                                  v279 = *v277;
                                                                  v280 = v277 + 1;
                                                                  if ( kk >= 3 )
                                                                    break;
                                                                  if ( v280 < v277 )
                                                                    goto LABEL_34;
                                                                  v277 = (unsigned int *)((char *)v280 + v279);
                                                                  if ( (unsigned int *)((char *)v280 + v279) < v280 )
                                                                    goto LABEL_34;
                                                                }
                                                                if ( v280 >= v277 )
                                                                {
                                                                  v281 = 0;
                                                                  v282 = 0;
                                                                  v283 = (unsigned int *)v656;
                                                                  if ( (_DWORD)v279 )
                                                                    v281 = (SIZE_T)v280;
                                                                  v701 = v281;
                                                                  while ( 1 )
                                                                  {
                                                                    v284 = *v283;
                                                                    v285 = v283 + 1;
                                                                    if ( v282 >= 4 )
                                                                      break;
                                                                    if ( v285 < v283 )
                                                                      goto LABEL_20;
                                                                    v283 = (unsigned int *)((char *)v285 + v284);
                                                                    if ( (unsigned int *)((char *)v285 + v284) < v285 )
                                                                      goto LABEL_20;
                                                                    ++v282;
                                                                  }
                                                                  if ( v285 >= v283 )
                                                                  {
                                                                    v286 = 0;
                                                                    if ( (_DWORD)v284 )
                                                                      v286 = v283 + 1;
                                                                    if ( (_DWORD)v284 != 4 )
                                                                    {
                                                                      v13 = -1073741789;
                                                                      goto LABEL_21;
                                                                    }
                                                                    v287 = *v286;
                                                                    v288 = (unsigned int *)v656;
                                                                    for ( mm = 0; ; ++mm )
                                                                    {
                                                                      v290 = *v288;
                                                                      v291 = v288 + 1;
                                                                      if ( mm >= 5 )
                                                                        break;
                                                                      if ( v291 < v288 )
                                                                        goto LABEL_20;
                                                                      v288 = (unsigned int *)((char *)v291 + v290);
                                                                      if ( (unsigned int *)((char *)v291 + v290) < v291 )
                                                                        goto LABEL_20;
                                                                    }
                                                                    if ( v291 >= v288 )
                                                                    {
                                                                      v130 = 0;
                                                                      if ( (_DWORD)v290 )
                                                                        v130 = v291;
                                                                      if ( (_DWORD)v290 != 4 )
                                                                      {
                                                                        v13 = -1073741789;
                                                                        goto LABEL_21;
                                                                      }
                                                                      if ( v670 != v698 )
                                                                      {
                                                                        v13 = -1073425151;
                                                                        goto LABEL_21;
                                                                      }
                                                                      v686 = *v130;
                                                                      v683 = v276;
                                                                      if ( v287 > 4 )
                                                                      {
                                                                        v13 = -2147024774;
                                                                        goto LABEL_21;
                                                                      }
                                                                      if ( (unsigned int)v279 > 4 )
                                                                      {
                                                                        v13 = -2147024774;
                                                                        goto LABEL_21;
                                                                      }
                                                                      memcpy_0(v5, (const void *)v701, v279);
                                                                      v13 = 0;
                                                                      LODWORD(v698) = 0;
LABEL_180:
                                                                      if ( (_DWORD)lpMem )
                                                                      {
                                                                        v13 = (int)lpMem;
                                                                        LODWORD(v698) = (_DWORD)lpMem;
                                                                      }
LABEL_79:
                                                                      HIDWORD(cchMax[0]) = 0;
                                                                      lpMem = (LPVOID)cchMax[1];
                                                                      if ( cchMax[1] )
                                                                      {
                                                                        v36 = GetProcessHeap();
                                                                        HeapFree(v36, 0, lpMem);
                                                                        cchMax[1] = 0;
                                                                      }
                                                                      if ( v656 )
                                                                      {
                                                                        v37 = GetProcessHeap();
                                                                        HeapFree(v37, 0, v656);
                                                                      }
                                                                      if ( v9 )
                                                                      {
                                                                        v617 = GetProcessHeap();
                                                                        HeapFree(v617, 0, v9);
                                                                      }
                                                                      if ( v6 )
                                                                      {
                                                                        v618 = GetProcessHeap();
                                                                        HeapFree(v618, 0, v6);
                                                                      }
                                                                      if ( v13 < 0 )
                                                                      {
                                                                        LocalFree(v5);
                                                                        goto LABEL_89;
                                                                      }
                                                                      if ( !v686 )
                                                                        goto LABEL_24;
                                                                      v300 = 0;
                                                                      v301 = 0;
                                                                      dwBytesa = 0;
                                                                      *(_OWORD *)v663 = 0;
                                                                      v302 = GetProcessHeap();
                                                                      v303 = (unsigned __int8 *)HeapAlloc(
                                                                                                  v302,
                                                                                                  8u,
                                                                                                  0xA0u);
                                                                      v662 = v303;
                                                                      v304 = v303;
                                                                      if ( !v303 )
                                                                        goto LABEL_424;
                                                                      *(_OWORD *)v303 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
                                                                      *((_OWORD *)v303 + 1) = xmmword_1800311A0;
                                                                      *((_OWORD *)v303 + 2) = xmmword_1800311B0;
                                                                      *((_OWORD *)v303 + 3) = xmmword_1800311C0;
                                                                      *((_OWORD *)v303 + 4) = xmmword_1800311D0;
                                                                      *((_OWORD *)v303 + 5) = xmmword_1800311E0;
                                                                      *((_OWORD *)v303 + 6) = xmmword_1800311F0;
                                                                      *((_OWORD *)v303 + 7) = xmmword_180031200;
                                                                      *((_OWORD *)v303 + 8) = xmmword_180031210;
                                                                      *((_OWORD *)v303 + 9) = xmmword_180031220;
                                                                      v305 = GetProcessHeap();
                                                                      v658 = (unsigned __int8 *)HeapAlloc(v305, 8u, 8u);
                                                                      if ( !v658 )
                                                                        goto LABEL_423;
                                                                      v301 = v658;
                                                                      *(_QWORD *)v658 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
                                                                      LODWORD(lpMem) = 0;
                                                                      Size = __rdtsc();
                                                                      LODWORD(v701) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 4, &v701) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  0,
                                                                                  (unsigned int)v701,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      LODWORD(v701) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 160, &v701) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  (unsigned int)lpMem,
                                                                                  (unsigned int)v701,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      LODWORD(v701) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 8, &v701) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  (unsigned int)lpMem,
                                                                                  (unsigned int)v701,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      LODWORD(v701) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 8, &v701) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  (unsigned int)lpMem,
                                                                                  (unsigned int)v701,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      HIDWORD(v663[0]) = (_DWORD)lpMem;
                                                                      v464 = (unsigned int)lpMem;
                                                                      v465 = GetProcessHeap();
                                                                      v466 = HeapAlloc(v465, 8u, v464);
                                                                      if ( !v466 )
                                                                        goto LABEL_423;
                                                                      v311 = 0;
                                                                      v663[1] = (size_t)v466;
                                                                      LODWORD(v663[0]) = 0;
                                                                      LODWORD(v668) = 0;
                                                                      v667 = 0;
                                                                      v701 = (SIZE_T)v466;
                                                                      if ( (int)RtlULongLongAdd(v466, 4, &v668) < 0
                                                                        || (unsigned __int64)(v467 + 2) > v663[1] + HIDWORD(v663[0]) )
                                                                      {
                                                                        goto LABEL_423;
                                                                      }
                                                                      v468 = v668;
                                                                      *v467 = 4;
                                                                      *v468 = 4;
                                                                      v469 = (unsigned int *)v663[1];
                                                                      v470 = LODWORD(v663[0]) + 1;
                                                                      LODWORD(v668) = 0;
                                                                      ++LODWORD(v663[0]);
                                                                      v667 = 0;
                                                                      if ( v663[1] )
                                                                      {
                                                                        v701 = v663[1];
                                                                        v471 = 0;
                                                                        while ( v471 < v470 )
                                                                        {
                                                                          v472 = *v469;
                                                                          LODWORD(lpMem) = 0;
                                                                          if ( (int)RtlUIntAdd(4, v472, &lpMem) < 0 )
                                                                            goto LABEL_423;
                                                                          v300 = v304;
                                                                          if ( (int)RtlULongLongAdd(
                                                                                      v473,
                                                                                      (unsigned int)lpMem,
                                                                                      &v701) < 0 )
                                                                            goto LABEL_424;
                                                                          v469 = (unsigned int *)v701;
                                                                          v471 = v474 + 1;
                                                                          v301 = v658;
                                                                          v311 = 0;
                                                                        }
                                                                        if ( (int)RtlULongLongAdd(v469, 4, &v668) < 0
                                                                          || (unsigned __int64)(v475 + 41) > v663[1] + HIDWORD(v663[0]) )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                        v476 = v668;
                                                                        *v475 = 160;
                                                                        *v476 = *(_OWORD *)v304;
                                                                        v476[1] = *((_OWORD *)v304 + 1);
                                                                        v476[2] = *((_OWORD *)v304 + 2);
                                                                        v476[3] = *((_OWORD *)v304 + 3);
                                                                        v476[4] = *((_OWORD *)v304 + 4);
                                                                        v476[5] = *((_OWORD *)v304 + 5);
                                                                        v476[6] = *((_OWORD *)v304 + 6);
                                                                        v476[7] = *((_OWORD *)v304 + 7);
                                                                        v476[8] = *((_OWORD *)v304 + 8);
                                                                        v476[9] = *((_OWORD *)v304 + 9);
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(4, 160, &lpMem) < 0
                                                                          || (int)RtlUIntAdd(
                                                                                    HIDWORD(v663[0]),
                                                                                    (unsigned int)lpMem,
                                                                                    (char *)v663 + 4) < 0 )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                      }
                                                                      v477 = (unsigned int *)v663[1];
                                                                      v478 = LODWORD(v663[0]) + 1;
                                                                      LODWORD(v668) = 0;
                                                                      ++LODWORD(v663[0]);
                                                                      v667 = 0;
                                                                      if ( v663[1] )
                                                                      {
                                                                        v701 = v663[1];
                                                                        v479 = 0;
                                                                        while ( v479 < v478 )
                                                                        {
                                                                          v480 = *v477;
                                                                          LODWORD(lpMem) = 0;
                                                                          if ( (int)RtlUIntAdd(4, v480, &lpMem) < 0 )
                                                                            goto LABEL_423;
                                                                          v300 = v304;
                                                                          if ( (int)RtlULongLongAdd(
                                                                                      v481,
                                                                                      (unsigned int)lpMem,
                                                                                      &v701) < 0 )
                                                                            goto LABEL_424;
                                                                          v477 = (unsigned int *)v701;
                                                                          v479 = v482 + 1;
                                                                          v301 = v658;
                                                                          v311 = 0;
                                                                        }
                                                                        if ( (int)RtlULongLongAdd(v477, 4, &v668) < 0
                                                                          || (unsigned __int64)(v483 + 3) > v663[1] + HIDWORD(v663[0]) )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                        v484 = v668;
                                                                        *v483 = 8;
                                                                        *v484 = *v301;
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(4, 8, &lpMem) < 0
                                                                          || (int)RtlUIntAdd(
                                                                                    HIDWORD(v663[0]),
                                                                                    (unsigned int)lpMem,
                                                                                    (char *)v663 + 4) < 0 )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                      }
                                                                      v485 = (unsigned int *)v663[1];
                                                                      v486 = LODWORD(v663[0]) + 1;
                                                                      LODWORD(v668) = 0;
                                                                      ++LODWORD(v663[0]);
                                                                      v667 = 0;
                                                                      if ( v663[1] )
                                                                      {
                                                                        v701 = v663[1];
                                                                        v487 = 0;
                                                                        while ( v487 < v486 )
                                                                        {
                                                                          v488 = *v485;
                                                                          LODWORD(lpMem) = 0;
                                                                          if ( (int)RtlUIntAdd(4, v488, &lpMem) < 0 )
                                                                            goto LABEL_423;
                                                                          v300 = v304;
                                                                          if ( (int)RtlULongLongAdd(
                                                                                      v489,
                                                                                      (unsigned int)lpMem,
                                                                                      &v701) < 0 )
                                                                            goto LABEL_424;
                                                                          v485 = (unsigned int *)v701;
                                                                          v487 = v490 + 1;
                                                                          v301 = v658;
                                                                          v311 = 0;
                                                                        }
                                                                        if ( (int)RtlULongLongAdd(v485, 4, &v668) < 0
                                                                          || (unsigned __int64)(v491 + 3) > v663[1] + HIDWORD(v663[0]) )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                        v492 = (size_t *)v668;
                                                                        v493 = Size;
                                                                        *v491 = 8;
                                                                        *v492 = v493;
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(4, 8, &lpMem) < 0
                                                                          || (int)RtlUIntAdd(
                                                                                    HIDWORD(v663[0]),
                                                                                    (unsigned int)lpMem,
                                                                                    (char *)v663 + 4) < 0 )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                      }
                                                                      ++LODWORD(v663[0]);
                                                                      LODWORD(lpMem) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 4, &lpMem) >= 0 )
                                                                      {
                                                                        LODWORD(v701) = (_DWORD)lpMem;
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(v494, 8, &lpMem) >= 0
                                                                          && (int)RtlUIntAdd(
                                                                                    v495,
                                                                                    (unsigned int)lpMem,
                                                                                    &v701) >= 0 )
                                                                        {
                                                                          v386 = 0;
                                                                          v653 = 0;
                                                                          Size = __rdtsc();
                                                                          v659 = 0;
                                                                          v674 = 8;
                                                                          v401 = RtlUIntAdd(8, HIDWORD(v663[0]), &v674);
                                                                          if ( v401 < 0 )
                                                                          {
LABEL_497:
                                                                            v665 = 0;
                                                                            v310 = v401 | 0x10000000;
                                                                            v664 = 0;
                                                                            v387 = 0;
                                                                            v644 = 0;
                                                                            v688 = 0;
                                                                            v655 = 0;
                                                                            Size = 0;
                                                                            if ( v310 < 0 )
                                                                              goto LABEL_431;
                                                                            if ( v386 )
                                                                            {
                                                                              if ( !v400
                                                                                || (v672 = v400 + 8LL,
                                                                                    v666 = (SIZE_T)MemoryAlloc(v672),
                                                                                    (v403 = v666) == 0) )
                                                                              {
                                                                                LODWORD(v699) = -805306367;
                                                                                goto LABEL_433;
                                                                              }
                                                                              LOBYTE(v402) = 0;
                                                                              v404 = v701;
                                                                              v405 = v659;
                                                                              LODWORD(lpMem) = v701;
                                                                              v661 = v402;
                                                                              if ( v659 )
                                                                              {
                                                                                v406 = 0;
                                                                                if ( v659 < 0x20uLL )
                                                                                  goto LABEL_967;
                                                                                LODWORD(lpMem) = v701;
                                                                                v407 = 0;
                                                                                v408 = 0;
                                                                                do
                                                                                {
                                                                                  v407 = _mm_xor_ps(
                                                                                           v407,
                                                                                           (__m128)_mm_loadu_si128((const __m128i *)&v386[v406]));
                                                                                  v409 = (__m128)_mm_loadu_si128((const __m128i *)&v386[v406 + 16]);
                                                                                  v406 += 32LL;
                                                                                  v410 = _mm_xor_ps(v409, v408);
                                                                                  v408 = v410;
                                                                                }
                                                                                while ( v406 < (v659 & 0xFFFFFFE0) );
                                                                                v411 = _mm_xor_ps(v407, v410);
                                                                                v412 = _mm_xor_ps(
                                                                                         v411,
                                                                                         (__m128)_mm_srli_si128(
                                                                                                   (__m128i)v411,
                                                                                                   8));
                                                                                v413 = _mm_xor_ps(
                                                                                         v412,
                                                                                         (__m128)_mm_srli_si128(
                                                                                                   (__m128i)v412,
                                                                                                   4));
                                                                                v414 = _mm_xor_ps(
                                                                                         v413,
                                                                                         (__m128)_mm_srli_si128(
                                                                                                   (__m128i)v413,
                                                                                                   2));
                                                                                v402 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v414, (__m128)_mm_srli_si128((__m128i)v414, 1)));
                                                                                v661 = v402;
                                                                                if ( v406 < v659 )
                                                                                {
LABEL_967:
                                                                                  do
                                                                                    LOBYTE(v402) = v386[v406++] ^ v402;
                                                                                  while ( v406 < v659 );
                                                                                  v661 = v402;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                LODWORD(lpMem) = v701;
                                                                              }
                                                                              v657 = (void *)0xC81ECB17B1B54A58LL;
                                                                              v676 = v386;
                                                                              v677 = v666;
                                                                              v415 = v659 & 7;
                                                                              if ( (v659 & 7) == 0 )
                                                                              {
                                                                                v416 = 0;
                                                                                LODWORD(v673) = -1;
                                                                                LODWORD(v679) = 0;
                                                                                LODWORD(v675) = 0;
                                                                                goto LABEL_510;
                                                                              }
                                                                              v619 = 0;
                                                                              LODWORD(v701) = 0;
                                                                              v620 = v386;
                                                                              v621 = 0;
                                                                              v622 = 0;
                                                                              do
                                                                              {
                                                                                v623 = *v620;
                                                                                v624 = 8 * v619;
                                                                                ++v620;
                                                                                if ( v619 >= 4 )
                                                                                  v622 |= v623 << (56 - v624);
                                                                                else
                                                                                  v621 |= v623 << (24 - v624);
                                                                                v619 = v701 + 1;
                                                                                LODWORD(v701) = v619;
                                                                              }
                                                                              while ( (int)v619 < v415 );
                                                                              LODWORD(v675) = v622;
                                                                              LODWORD(v670) = 0;
                                                                              v625 = 0;
                                                                              v626 = v622;
                                                                              LODWORD(v673) = v621 ^ 0xB17A307A;
                                                                              v387 = v664;
                                                                              LODWORD(v701) = v621 ^ 0xB17A307A;
                                                                              v311 = v664;
                                                                              v627 = v626 ^ 0x42F6B18D;
                                                                              LODWORD(v679) = v621;
                                                                              v13 = v698;
                                                                              v628 = (_BYTE *)v666;
                                                                              v629 = (int)v673;
                                                                              v676 = v620;
                                                                              LODWORD(lpMem) = v404;
                                                                              v630 = v627;
                                                                              v653 = v386;
                                                                              do
                                                                              {
                                                                                v669 = (SIZE_T)(v628 + 1);
                                                                                if ( v625 >= 4 )
                                                                                {
                                                                                  v630 = __ROR4__(v630, 24);
                                                                                  v631 = v630;
                                                                                }
                                                                                else
                                                                                {
                                                                                  v629 = __ROR4__(v629, 24);
                                                                                  v631 = v629;
                                                                                }
                                                                                *v628 = v631;
                                                                                ++v625;
                                                                                v628 = (_BYTE *)v669;
                                                                              }
                                                                              while ( v625 < v415 );
                                                                              v5 = v680;
                                                                              v677 = v669;
                                                                              LOBYTE(v402) = v661;
                                                                              if ( (unsigned int)v415 <= 4 )
                                                                              {
                                                                                LODWORD(v673) = 0;
                                                                                if ( (unsigned int)v415 < 4 )
                                                                                {
                                                                                  v416 = (unsigned int)v701 >> (8 * (4 - v415)) << (8 * (4 - v415));
LABEL_510:
                                                                                  v667 = (LPVOID)(v405 >> 3);
                                                                                  if ( v405 >> 3 )
                                                                                  {
                                                                                    v417 = v667;
                                                                                    v418 = (int)v673;
                                                                                    v419 = (unsigned __int8 *)v676;
                                                                                    v420 = v677;
                                                                                    v421 = (int)v679;
                                                                                    v422 = (int)v675;
                                                                                    LODWORD(v670) = WORD2(v657);
                                                                                    LODWORD(v654) = HIWORD(HIDWORD(v657));
                                                                                    LODWORD(v701) = 19032;
                                                                                    LODWORD(v656) = WORD1(v657);
                                                                                    LODWORD(Src) = HIWORD(HIDWORD(v657));
                                                                                    v423 = HIWORD(HIDWORD(v657));
                                                                                    v647 = HIDWORD(v657) ^ 0xB1B54A58;
                                                                                    v669 = 0;
                                                                                    do
                                                                                    {
                                                                                      v424 = v419[1];
                                                                                      v425 = *v419;
                                                                                      v426 = v419[4];
                                                                                      v419 += 8;
                                                                                      v427 = *(v419 - 5)
                                                                                           | ((*(v419 - 6)
                                                                                             | ((v424 | (v425 << 8)) << 8)) << 8);
                                                                                      v428 = *(v419 - 1)
                                                                                           | ((*(v419 - 2)
                                                                                             | ((*(v419 - 3)
                                                                                               | (v426 << 8)) << 8)) << 8);
                                                                                      v429 = v416
                                                                                           ^ v427
                                                                                           ^ ((v418 ^ v428) - v701);
                                                                                      v430 = __ROR4__(v429, 15);
                                                                                      v431 = HIDWORD(v657) ^ v429;
                                                                                      v432 = v418
                                                                                           ^ v428
                                                                                           ^ (__ROR4__(v431, 7)
                                                                                            + WORD1(v657) * v430);
                                                                                      v433 = v431
                                                                                           ^ (v670
                                                                                            * __ROR4__(
                                                                                                v432 - 1313519016,
                                                                                                9)
                                                                                            - __ROR4__(v432, 10));
                                                                                      v434 = v432
                                                                                           ^ (__ROR4__(v433, 27)
                                                                                            + v423
                                                                                            * __ROR4__(v670 ^ v433, 28));
                                                                                      v435 = v433
                                                                                           ^ (HIDWORD(v657)
                                                                                            - (v434 ^ 0xB1B54A58));
                                                                                      v436 = v434
                                                                                           ^ (WORD1(v657)
                                                                                            * (v435 - v701)
                                                                                            - (v435 >> 6));
                                                                                      v437 = v435
                                                                                           ^ (v701
                                                                                            * (v670 ^ __ROR4__(v436, 15)));
                                                                                      v438 = v436
                                                                                           ^ (v670
                                                                                            * (v423 + __ROR4__(~v437, 3)));
                                                                                      v439 = v438
                                                                                           ^ ((_DWORD)v656
                                                                                            * ((unsigned int)v654
                                                                                             ^ v437
                                                                                             ^ (v438
                                                                                              - v701
                                                                                              - HIDWORD(v657))))
                                                                                           ^ __ROR4__(
                                                                                               v437
                                                                                             ^ (v438
                                                                                              - v701
                                                                                              - HIDWORD(v657)),
                                                                                               10);
                                                                                      v440 = v437
                                                                                           ^ (v438 - v701 - HIDWORD(v657))
                                                                                           ^ __ROR4__(v439, 3)
                                                                                           ^ (v670
                                                                                            * __ROR4__(v701 ^ v439, 26));
                                                                                      v441 = v439
                                                                                           ^ (v701
                                                                                            * (__ROR4__(v440, 15) - v423));
                                                                                      v442 = v440
                                                                                           ^ (v701
                                                                                            * ((unsigned int)v654 ^ v441))
                                                                                           ^ ((v441 ^ (v441 >> 14)) >> 1)
                                                                                           ^ (v701
                                                                                            * ((8 * (v441 - v670))
                                                                                             | ((v441
                                                                                               - (unsigned int)v670) >> 29)));
                                                                                      v443 = v441
                                                                                           ^ (WORD1(v657)
                                                                                            * (v442 - v670)
                                                                                            - (v442 >> 13));
                                                                                      v444 = v442
                                                                                           ^ __ROR4__(v443, 11)
                                                                                           ^ (v670
                                                                                            * __ROR4__(
                                                                                                -1313519016 - v443,
                                                                                                9));
                                                                                      v445 = v443
                                                                                           ^ (v444 - v423 + 1313519016);
                                                                                      v446 = v444
                                                                                           ^ (v701
                                                                                            * (v445 ^ WORD1(v657))
                                                                                            - __ROR4__(v445, 7));
                                                                                      v447 = v445
                                                                                           ^ (WORD1(v657)
                                                                                            * __ROR4__(
                                                                                                v446
                                                                                              ^ (unsigned int)v654,
                                                                                                28)
                                                                                            - __ROR4__(v446, 16));
                                                                                      v448 = v446
                                                                                           ^ (__ROR4__(v447, 4)
                                                                                            + v670
                                                                                            * __ROR4__(
                                                                                                -1313519016 - v447,
                                                                                                10));
                                                                                      v420 += 8LL;
                                                                                      v449 = v447
                                                                                           ^ __ROR4__(v448, 9)
                                                                                           ^ (v423
                                                                                            * __ROR4__(
                                                                                                v448 + 1313519016,
                                                                                                4));
                                                                                      v450 = v448
                                                                                           ^ (v701
                                                                                            * __ROR4__(
                                                                                                v449 ^ HIDWORD(v657),
                                                                                                24)
                                                                                            - __ROR4__(v449, 30));
                                                                                      v451 = v449
                                                                                           ^ (WORD1(v657)
                                                                                            * __ROR4__(
                                                                                                HIDWORD(v657) - v450,
                                                                                                11)
                                                                                            - __ROR4__(v450, 12));
                                                                                      v452 = v422 ^ v647 ^ v451;
                                                                                      v422 = v428;
                                                                                      v453 = v450
                                                                                           ^ (v451 >> 8)
                                                                                           ^ (v670 * (WORD1(v657) ^ v451));
                                                                                      v416 = v453 ^ v421;
                                                                                      v418 = v453 ^ v452;
                                                                                      *(_BYTE *)(v420 - 5) = v453 ^ v421;
                                                                                      LOBYTE(v451) = __ROR4__(v453 ^ v421, 8);
                                                                                      v421 = v427;
                                                                                      *(_BYTE *)(v420 - 1) = v418;
                                                                                      *(_BYTE *)(v420 - 6) = v451;
                                                                                      *(_BYTE *)(v420 - 2) = __ROR4__(v418, 8);
                                                                                      *(_BYTE *)(v420 - 7) = __ROR4__(v416, 16);
                                                                                      *(_BYTE *)(v420 - 3) = __ROR4__(v418, 16);
                                                                                      *(_BYTE *)(v420 - 8) = __ROR4__(v416, 24);
                                                                                      *(_BYTE *)(v420 - 4) = __ROR4__(v418, 24);
                                                                                      ++v669;
                                                                                    }
                                                                                    while ( v669 < (unsigned __int64)v417 );
                                                                                    v387 = v664;
                                                                                    v5 = v680;
                                                                                    v311 = v664;
                                                                                    v13 = v698;
                                                                                    v386 = v653;
                                                                                    v403 = v666;
                                                                                    LOBYTE(v402) = v661;
                                                                                  }
                                                                                  *(_QWORD *)(v403 + v659) = (unsigned __int8)v402;
                                                                                  v454 = GetProcessHeap();
                                                                                  v455 = HeapAlloc(v454, 8u, 0x30u);
                                                                                  if ( v455 )
                                                                                  {
                                                                                    *(_DWORD *)v455 = v672;
                                                                                    v456 = GetProcessHeap();
                                                                                    v457 = HeapAlloc(
                                                                                             v456,
                                                                                             8u,
                                                                                             (unsigned int)v672);
                                                                                    if ( v457 )
                                                                                    {
                                                                                      v458 = (unsigned int)v672;
                                                                                      v459 = (const void *)v666;
                                                                                      *((_QWORD *)v455 + 1) = v457;
                                                                                      memcpy_0(v457, v459, v458);
                                                                                      *((_DWORD *)v455 + 4) = 160;
                                                                                      v460 = GetProcessHeap();
                                                                                      v461 = HeapAlloc(v460, 8u, 0xA0u);
                                                                                      if ( v461 )
                                                                                      {
                                                                                        *((_QWORD *)v455 + 3) = v461;
                                                                                        *v461 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                                                                                        v461[1] = xmmword_1800310F0;
                                                                                        v461[2] = xmmword_180031100;
                                                                                        v461[3] = xmmword_180031110;
                                                                                        v461[4] = xmmword_180031120;
                                                                                        v461[5] = xmmword_180031130;
                                                                                        v461[6] = xmmword_180031140;
                                                                                        v461[7] = xmmword_180031150;
                                                                                        v461[8] = xmmword_180031160;
                                                                                        v461[9] = xmmword_180031170;
                                                                                        *((_DWORD *)v455 + 8) = 8;
                                                                                        v462 = GetProcessHeap();
                                                                                        v463 = HeapAlloc(v462, 8u, 8u);
                                                                                        if ( v463 )
                                                                                        {
                                                                                          *((_QWORD *)v455 + 5) = v463;
                                                                                          *v463 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                                                                                          LODWORD(v701) = 0;
LABEL_519:
                                                                                          v387 = v455;
                                                                                          goto LABEL_601;
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                    v501 = (void *)*((_QWORD *)v455 + 1);
                                                                                    LODWORD(v701) = -1073741801;
                                                                                    v667 = v501;
                                                                                    if ( v501 )
                                                                                    {
                                                                                      v502 = GetProcessHeap();
                                                                                      HeapFree(v502, 0, v667);
                                                                                      *((_QWORD *)v455 + 1) = 0;
                                                                                    }
                                                                                    v667 = (LPVOID)*((_QWORD *)v455 + 3);
                                                                                    if ( v667 )
                                                                                    {
                                                                                      v503 = GetProcessHeap();
                                                                                      HeapFree(v503, 0, v667);
                                                                                      *((_QWORD *)v455 + 3) = 0;
                                                                                    }
                                                                                    v667 = (LPVOID)*((_QWORD *)v455 + 5);
                                                                                    if ( v667 )
                                                                                    {
                                                                                      v504 = GetProcessHeap();
                                                                                      HeapFree(v504, 0, v667);
                                                                                      *((_QWORD *)v455 + 5) = 0;
                                                                                    }
                                                                                    v505 = GetProcessHeap();
                                                                                    HeapFree(v505, 0, v455);
                                                                                    v455 = 0;
                                                                                    if ( (v701 & 0x80000000) == 0LL )
                                                                                      goto LABEL_519;
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    LODWORD(v701) = -1073741801;
                                                                                  }
LABEL_601:
                                                                                  v506 = GetProcessHeap();
                                                                                  HeapFree(v506, 0, (LPVOID)v666);
                                                                                  v310 = v701 | 0x10000000;
                                                                                  if ( (v701 & 0x80000000) != 0LL )
                                                                                    goto LABEL_431;
                                                                                  v507 = *(unsigned int *)v387;
                                                                                  LODWORD(v654) = 0;
                                                                                  LODWORD(v701) = 4;
                                                                                  v307 = RtlUIntAdd(4, v507, &v701);
                                                                                  if ( v307 >= 0 )
                                                                                  {
                                                                                    v307 = RtlUIntAdd(
                                                                                             (unsigned int)v701,
                                                                                             v508,
                                                                                             &v701);
                                                                                    if ( v307 >= 0 )
                                                                                    {
                                                                                      v307 = RtlUIntAdd(
                                                                                               (unsigned int)v701,
                                                                                               *((unsigned int *)v387 + 4),
                                                                                               &v701);
                                                                                      if ( v307 >= 0 )
                                                                                      {
                                                                                        v307 = RtlUIntAdd(
                                                                                                 (unsigned int)v701,
                                                                                                 4,
                                                                                                 &v701);
                                                                                        if ( v307 >= 0 )
                                                                                        {
                                                                                          v307 = RtlUIntAdd(
                                                                                                   (unsigned int)v701,
                                                                                                   *((unsigned int *)v387 + 8),
                                                                                                   &v701);
                                                                                          if ( v307 >= 0 )
                                                                                          {
                                                                                            v509 = v701;
                                                                                            v510 = GetProcessHeap();
                                                                                            v511 = HeapAlloc(
                                                                                                     v510,
                                                                                                     8u,
                                                                                                     v509);
                                                                                            v308 = v511;
                                                                                            if ( !v511 )
                                                                                            {
                                                                                              v311 = 0;
                                                                                              goto LABEL_432;
                                                                                            }
                                                                                            v699 = (SIZE_T)v511;
                                                                                            *v511 = *(_DWORD *)v387;
                                                                                            v307 = RtlULongLongAdd(
                                                                                                     v511,
                                                                                                     4,
                                                                                                     &v699);
                                                                                            if ( v307 >= 0 )
                                                                                            {
                                                                                              memcpy_0(
                                                                                                (void *)v699,
                                                                                                (const void *)v387[1],
                                                                                                *(unsigned int *)v387);
                                                                                              v307 = RtlULongLongAdd(v699, *(unsigned int *)v387, &v699);
                                                                                              if ( v307 >= 0 )
                                                                                              {
                                                                                                v512 = v699;
                                                                                                *(_DWORD *)v699 = *((_DWORD *)v387 + 4);
                                                                                                v307 = RtlULongLongAdd(v512, 4, &v699);
                                                                                                if ( v307 >= 0 )
                                                                                                {
                                                                                                  memcpy_0(
                                                                                                    (void *)v699,
                                                                                                    (const void *)v387[3],
                                                                                                    *((unsigned int *)v387 + 4));
                                                                                                  v307 = RtlULongLongAdd(v699, *((unsigned int *)v387 + 4), &v699);
                                                                                                  if ( v307 >= 0 )
                                                                                                  {
                                                                                                    v513 = v699;
                                                                                                    *(_DWORD *)v699 = *((_DWORD *)v387 + 8);
                                                                                                    v307 = RtlULongLongAdd(v513, 4, &v699);
                                                                                                    if ( v307 >= 0 )
                                                                                                    {
                                                                                                      memcpy_0((void *)v699, (const void *)v387[5], *((unsigned int *)v387 + 8));
                                                                                                      v307 = RtlULongLongAdd(v699, *((unsigned int *)v387 + 8), &v699);
                                                                                                      if ( v307 >= 0 )
                                                                                                      {
                                                                                                        LODWORD(v654) = v701;
                                                                                                        v644 = v308;
LABEL_428:
                                                                                                        v309 = v307 | 0x10000000;
                                                                                                        if ( v309 < 0 )
                                                                                                        {
                                                                                                          LODWORD(v699) = v309;
                                                                                                          v311 = v644;
                                                                                                          goto LABEL_432;
                                                                                                        }
                                                                                                        v685 = 8;
                                                                                                        v310 = RtlUIntAdd(8, (unsigned int)lpMem, &v685) | 0x10000000;
                                                                                                        if ( v310 >= 0 )
                                                                                                        {
                                                                                                          v515 = (v685 + 7) & 0xFFFFFFF8;
                                                                                                          if ( (unsigned int)v515 < v685 )
                                                                                                          {
                                                                                                            v310 = -1073741675;
                                                                                                            goto LABEL_430;
                                                                                                          }
                                                                                                          v684 = (v685 + 7) & 0xFFFFFFF8;
                                                                                                          v310 = RtlUIntAdd(v515, 8, &v684);
                                                                                                          if ( v310 >= 0 )
                                                                                                          {
                                                                                                            LODWORD(lpMem) = 0;
                                                                                                            v516 = (unsigned int *)v663[1];
                                                                                                            if ( v663[1] && LODWORD(v663[0]) > 1 )
                                                                                                            {
                                                                                                              v699 = v663[1];
                                                                                                              for ( nn = 0;
                                                                                                                    !nn;
                                                                                                                    nn = v545 + 1 )
                                                                                                              {
                                                                                                                v310 = RtlULongLongAdd(v516, 4, &v699);
                                                                                                                if ( v310 < 0 )
                                                                                                                  goto LABEL_430;
                                                                                                                v310 = RtlULongLongAdd(v699, v544, &v699);
                                                                                                                if ( v310 < 0 )
                                                                                                                  goto LABEL_430;
                                                                                                                v516 = (unsigned int *)v699;
                                                                                                              }
                                                                                                              v518 = *v516;
                                                                                                              v310 = RtlULongLongAdd(v516, 4, &v699);
                                                                                                              if ( v310 < 0 )
                                                                                                                goto LABEL_430;
                                                                                                              v519 = v663[1];
                                                                                                              if ( v663[1] )
                                                                                                              {
                                                                                                                if ( LODWORD(v663[0]) > 2 )
                                                                                                                {
                                                                                                                  v699 = v663[1];
                                                                                                                  for ( i1 = 0;
                                                                                                                        i1 < 2;
                                                                                                                        i1 = v547 + 1 )
                                                                                                                  {
                                                                                                                    v310 = RtlULongLongAdd(v519, 4, &v699);
                                                                                                                    if ( v310 < 0 )
                                                                                                                      goto LABEL_430;
                                                                                                                    v310 = RtlULongLongAdd(v699, v546, &v699);
                                                                                                                    if ( v310 < 0 )
                                                                                                                      goto LABEL_430;
                                                                                                                    v519 = v699;
                                                                                                                  }
                                                                                                                  v310 = RtlULongLongAdd(v519, 4, &v699);
                                                                                                                  if ( v310 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  LODWORD(lpMem) = v521;
                                                                                                                  LODWORD(v699) = 4;
                                                                                                                  v310 = RtlUIntAdd(4, v684, &v699);
                                                                                                                  if ( v310 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v310 = RtlUIntAdd((unsigned int)v699, v522, &v699);
                                                                                                                  if ( v310 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v310 = RtlUIntAdd((unsigned int)v699, v518, &v699);
                                                                                                                  if ( v310 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v310 = RtlUIntAdd((unsigned int)v699, 4, &v699);
                                                                                                                  if ( v310 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v310 = RtlUIntAdd((unsigned int)v699, v523, &v699);
                                                                                                                  if ( v310 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  LODWORD(lpMem) = v699;
                                                                                                                  if ( (unsigned int)v699 > 0x400000 )
                                                                                                                  {
                                                                                                                    v310 = -2147418113;
                                                                                                                    goto LABEL_430;
                                                                                                                  }
                                                                                                                  v524 = v699;
                                                                                                                  v525 = GetProcessHeap();
                                                                                                                  v526 = HeapAlloc(v525, 8u, v524);
                                                                                                                  v527 = v526;
                                                                                                                  if ( !v526 )
                                                                                                                  {
                                                                                                                    v311 = v644;
                                                                                                                    LODWORD(v699) = -805306345;
                                                                                                                    goto LABEL_432;
                                                                                                                  }
                                                                                                                  v688 = v526;
                                                                                                                  hModule = 0;
                                                                                                                  v694 = 0;
                                                                                                                  v695 = 0;
                                                                                                                  if ( !v308 )
                                                                                                                  {
                                                                                                                    LODWORD(v699) = -2147024809;
                                                                                                                    goto LABEL_765;
                                                                                                                  }
                                                                                                                  LODWORD(v695) = (_DWORD)v654;
                                                                                                                  *(_QWORD *)((char *)&v695 + 4) = (unsigned int)lpMem;
                                                                                                                  *(_QWORD *)&v694 = v308;
                                                                                                                  *((_QWORD *)&v694 + 1) = v526;
                                                                                                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule) )
                                                                                                                  {
                                                                                                                    v528 = GetProcAddress(hModule, "NtQuerySystemInformation");
                                                                                                                    if ( v528 )
                                                                                                                    {
                                                                                                                      v529 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, _QWORD))v528)(134, &v694, 32, 0) | 0x10000000;
                                                                                                                      if ( v529 >= 0 )
                                                                                                                      {
                                                                                                                        v530 = DWORD1(v695);
LABEL_639:
                                                                                                                        LODWORD(v699) = 0;
                                                                                                                        v656 = v527;
                                                                                                                        if ( v530 < 4 )
                                                                                                                        {
                                                                                                                          LODWORD(v699) = -805306306;
                                                                                                                          v311 = v308;
                                                                                                                        }
                                                                                                                        else
                                                                                                                        {
                                                                                                                          LODWORD(v701) = *v527;
                                                                                                                          v339 = RtlULongLongAdd(v527, 4, &v656);
                                                                                                                          if ( v339 < 0 )
                                                                                                                            goto LABEL_471;
                                                                                                                          v339 = RtlUIntAdd(0, 4, &v699);
                                                                                                                          if ( v339 < 0 )
                                                                                                                          {
                                                                                                                            v664 = v387;
                                                                                                                            v343 = v531;
                                                                                                                            v653 = v386;
                                                                                                                            v645 = v308;
                                                                                                                            goto LABEL_473;
                                                                                                                          }
                                                                                                                          if ( v532 - (int)v699 < (unsigned int)v533 )
                                                                                                                          {
                                                                                                                            LODWORD(v699) = -805306306;
                                                                                                                            v311 = v308;
                                                                                                                          }
                                                                                                                          else
                                                                                                                          {
                                                                                                                            v677 = (SIZE_T)v656;
                                                                                                                            v669 = v533;
                                                                                                                            v339 = RtlULongLongAdd(v656, (unsigned int)v533, &v656);
                                                                                                                            if ( v339 < 0 )
                                                                                                                              goto LABEL_471;
                                                                                                                            v339 = RtlUIntAdd(v534, v535, &v699);
                                                                                                                            if ( v339 < 0 )
                                                                                                                              goto LABEL_471;
                                                                                                                            if ( (unsigned int)(v536 - v699) < 4 )
                                                                                                                            {
                                                                                                                              LODWORD(v699) = -805306306;
                                                                                                                              v311 = v308;
                                                                                                                            }
                                                                                                                            else
                                                                                                                            {
                                                                                                                              LODWORD(lpMem) = *(_DWORD *)v656;
                                                                                                                              v339 = RtlULongLongAdd(v656, 4, &v656);
                                                                                                                              if ( v339 < 0 )
                                                                                                                                goto LABEL_471;
                                                                                                                              v339 = RtlUIntAdd((unsigned int)v699, 4, &v699);
                                                                                                                              if ( v339 < 0 )
                                                                                                                                goto LABEL_471;
                                                                                                                              if ( v537 - (int)v699 < (unsigned int)v538 )
                                                                                                                              {
                                                                                                                                LODWORD(v699) = -805306306;
                                                                                                                                v311 = v308;
                                                                                                                              }
                                                                                                                              else
                                                                                                                              {
                                                                                                                                v672 = (SIZE_T)v656;
                                                                                                                                v666 = v538;
                                                                                                                                v339 = RtlULongLongAdd(v656, (unsigned int)v538, &v656);
                                                                                                                                if ( v339 < 0 )
                                                                                                                                  goto LABEL_471;
                                                                                                                                v339 = RtlUIntAdd((unsigned int)v699, v539, &v699);
                                                                                                                                if ( v339 < 0 )
                                                                                                                                  goto LABEL_471;
                                                                                                                                if ( (unsigned int)(v540 - v699) < 4 )
                                                                                                                                {
                                                                                                                                  LODWORD(v699) = -805306306;
                                                                                                                                  v311 = v308;
                                                                                                                                }
                                                                                                                                else
                                                                                                                                {
                                                                                                                                  v648 = *(_DWORD *)v656;
                                                                                                                                  v339 = RtlULongLongAdd(v656, 4, &v656);
                                                                                                                                  if ( v339 < 0 )
                                                                                                                                    goto LABEL_471;
                                                                                                                                  v339 = RtlUIntAdd((unsigned int)v699, 4, &v699);
                                                                                                                                  if ( v339 < 0 )
                                                                                                                                    goto LABEL_471;
                                                                                                                                  if ( v541 - (int)v699 < v542 )
                                                                                                                                  {
                                                                                                                                    LODWORD(v699) = -805306306;
                                                                                                                                    v311 = v308;
                                                                                                                                  }
                                                                                                                                  else
                                                                                                                                  {
                                                                                                                                    v339 = RtlUIntAdd((unsigned int)v699, v542, &v699);
                                                                                                                                    if ( v339 < 0 )
                                                                                                                                    {
LABEL_471:
                                                                                                                                      v645 = v308;
                                                                                                                                      v653 = v386;
                                                                                                                                      v664 = v387;
LABEL_472:
                                                                                                                                      v343 = (SIZE_T *)v655;
                                                                                                                                      goto LABEL_473;
                                                                                                                                    }
                                                                                                                                    if ( v340 == (_DWORD)v699 )
                                                                                                                                    {
                                                                                                                                      if ( (unsigned int)(v342 + v341 + (_DWORD)lpMem) + 12LL == v340 )
                                                                                                                                      {
                                                                                                                                        v548 = GetProcessHeap();
                                                                                                                                        v343 = (SIZE_T *)HeapAlloc(v548, 8u, 0x30u);
                                                                                                                                        v699 = (SIZE_T)v343;
                                                                                                                                        if ( v343 )
                                                                                                                                        {
                                                                                                                                          v653 = v386;
                                                                                                                                          v664 = v387;
                                                                                                                                          v645 = v308;
                                                                                                                                          if ( v677 )
                                                                                                                                          {
                                                                                                                                            *(_DWORD *)v343 = v701;
                                                                                                                                            v549 = GetProcessHeap();
                                                                                                                                            v550 = HeapAlloc(v549, 8u, v669);
                                                                                                                                            v551 = (_QWORD *)v699;
                                                                                                                                            if ( !v550 )
                                                                                                                                            {
LABEL_766:
                                                                                                                                              v602 = v551[1];
                                                                                                                                              v339 = -1073741801;
                                                                                                                                              lpMem = 0;
                                                                                                                                              v701 = v602;
                                                                                                                                              if ( v602 )
                                                                                                                                              {
                                                                                                                                                v603 = GetProcessHeap();
                                                                                                                                                HeapFree(v603, 0, (LPVOID)v701);
                                                                                                                                                v551 = (_QWORD *)v699;
                                                                                                                                                *(_QWORD *)(v699 + 8) = 0;
                                                                                                                                              }
                                                                                                                                              v701 = v551[3];
                                                                                                                                              if ( v701 )
                                                                                                                                              {
                                                                                                                                                v604 = GetProcessHeap();
                                                                                                                                                HeapFree(v604, 0, (LPVOID)v701);
                                                                                                                                                v551 = (_QWORD *)v699;
                                                                                                                                                *(_QWORD *)(v699 + 24) = 0;
                                                                                                                                              }
                                                                                                                                              v701 = v551[5];
                                                                                                                                              if ( v701 )
                                                                                                                                              {
                                                                                                                                                v605 = GetProcessHeap();
                                                                                                                                                HeapFree(v605, 0, (LPVOID)v701);
                                                                                                                                                *(_QWORD *)(v699 + 40) = 0;
                                                                                                                                              }
                                                                                                                                              v606 = GetProcessHeap();
                                                                                                                                              HeapFree(v606, 0, (LPVOID)v699);
                                                                                                                                              v343 = (SIZE_T *)lpMem;
                                                                                                                                              goto LABEL_678;
                                                                                                                                            }
                                                                                                                                            v552 = v669;
                                                                                                                                            v339 = 0;
                                                                                                                                            v553 = (const void *)v677;
                                                                                                                                            *(_QWORD *)(v699 + 8) = v550;
                                                                                                                                            memcpy_0(v550, v553, v552);
                                                                                                                                            v343 = (SIZE_T *)v699;
                                                                                                                                          }
                                                                                                                                          else
                                                                                                                                          {
                                                                                                                                            *(_DWORD *)v343 = 0;
                                                                                                                                            v339 = 0;
                                                                                                                                            v343[1] = 0;
                                                                                                                                          }
                                                                                                                                          if ( v672 )
                                                                                                                                          {
                                                                                                                                            *((_DWORD *)v343 + 4) = (_DWORD)lpMem;
                                                                                                                                            v554 = GetProcessHeap();
                                                                                                                                            v555 = HeapAlloc(v554, 8u, v666);
                                                                                                                                            v551 = (_QWORD *)v699;
                                                                                                                                            if ( !v555 )
                                                                                                                                            {
LABEL_889:
                                                                                                                                              v653 = v386;
                                                                                                                                              v664 = v387;
                                                                                                                                              v645 = v308;
                                                                                                                                              v699 = (SIZE_T)v551;
                                                                                                                                              goto LABEL_766;
                                                                                                                                            }
                                                                                                                                            v556 = v666;
                                                                                                                                            v339 = 0;
                                                                                                                                            v557 = (const void *)v672;
                                                                                                                                            *(_QWORD *)(v699 + 24) = v555;
                                                                                                                                            memcpy_0(v555, v557, v556);
                                                                                                                                            v343 = (SIZE_T *)v699;
                                                                                                                                          }
                                                                                                                                          else
                                                                                                                                          {
                                                                                                                                            *((_DWORD *)v343 + 4) = 0;
                                                                                                                                            v343[3] = 0;
                                                                                                                                          }
                                                                                                                                          if ( !v656 )
                                                                                                                                          {
                                                                                                                                            *((_DWORD *)v343 + 8) = 0;
                                                                                                                                            v343[5] = 0;
                                                                                                                                            goto LABEL_677;
                                                                                                                                          }
                                                                                                                                          *((_DWORD *)v343 + 8) = v648;
                                                                                                                                          lpMem = (LPVOID)v648;
                                                                                                                                          v558 = GetProcessHeap();
                                                                                                                                          v559 = HeapAlloc(v558, 8u, v648);
                                                                                                                                          v551 = (_QWORD *)v699;
                                                                                                                                          if ( v559 )
                                                                                                                                          {
                                                                                                                                            v560 = lpMem;
                                                                                                                                            v339 = 0;
                                                                                                                                            v561 = v656;
                                                                                                                                            *(_QWORD *)(v699 + 40) = v559;
                                                                                                                                            memcpy_0(v559, v561, (size_t)v560);
                                                                                                                                            v343 = (SIZE_T *)v699;
LABEL_677:
                                                                                                                                            lpMem = v343;
                                                                                                                                            v645 = v308;
                                                                                                                                            v664 = v387;
                                                                                                                                            v653 = v386;
LABEL_678:
                                                                                                                                            if ( v339 < 0 )
                                                                                                                                            {
                                                                                                                                              if ( v343 )
                                                                                                                                              {
                                                                                                                                                v699 = v343[1];
                                                                                                                                                if ( v699 )
                                                                                                                                                {
                                                                                                                                                  v562 = GetProcessHeap();
                                                                                                                                                  HeapFree(v562, 0, (LPVOID)v699);
                                                                                                                                                  v343 = (SIZE_T *)lpMem;
                                                                                                                                                  *((_QWORD *)lpMem + 1) = 0;
                                                                                                                                                }
                                                                                                                                                v699 = v343[3];
                                                                                                                                                if ( v699 )
                                                                                                                                                {
                                                                                                                                                  v563 = GetProcessHeap();
                                                                                                                                                  HeapFree(v563, 0, (LPVOID)v699);
                                                                                                                                                  v343 = (SIZE_T *)lpMem;
                                                                                                                                                  *((_QWORD *)lpMem + 3) = 0;
                                                                                                                                                }
                                                                                                                                                v699 = v343[5];
                                                                                                                                                if ( v699 )
                                                                                                                                                {
                                                                                                                                                  v564 = GetProcessHeap();
                                                                                                                                                  HeapFree(v564, 0, (LPVOID)v699);
                                                                                                                                                  *((_QWORD *)lpMem + 5) = 0;
                                                                                                                                                }
                                                                                                                                                v565 = GetProcessHeap();
                                                                                                                                                HeapFree(v565, 0, lpMem);
                                                                                                                                              }
                                                                                                                                              goto LABEL_472;
                                                                                                                                            }
                                                                                                                                            v655 = v343;
LABEL_473:
                                                                                                                                            LODWORD(v699) = v339 | 0x10000000;
                                                                                                                                            if ( v339 < 0 )
                                                                                                                                            {
LABEL_521:
                                                                                                                                              v311 = v645;
                                                                                                                                              goto LABEL_432;
                                                                                                                                            }
                                                                                                                                            if ( !v343 )
                                                                                                                                            {
                                                                                                                                              LODWORD(v699) = -805306355;
                                                                                                                                              goto LABEL_493;
                                                                                                                                            }
                                                                                                                                            v666 = v343[1];
                                                                                                                                            if ( !v666 )
                                                                                                                                            {
                                                                                                                                              LODWORD(v699) = -805306355;
                                                                                                                                              goto LABEL_493;
                                                                                                                                            }
                                                                                                                                            v344 = *(unsigned int *)v343;
                                                                                                                                            if ( !(_DWORD)v344 )
                                                                                                                                            {
                                                                                                                                              LODWORD(v699) = -805306355;
                                                                                                                                              goto LABEL_493;
                                                                                                                                            }
                                                                                                                                            v345 = v344 - 8;
                                                                                                                                            v676 = (void *)(v344 - 8);
                                                                                                                                            v346 = MemoryAlloc(v344 - 8);
                                                                                                                                            v657 = v346;
                                                                                                                                            v348 = v346;
                                                                                                                                            if ( !v346 )
                                                                                                                                            {
LABEL_492:
                                                                                                                                              LODWORD(v699) = -805306367;
LABEL_493:
                                                                                                                                              v311 = v645;
                                                                                                                                              goto LABEL_432;
                                                                                                                                            }
                                                                                                                                            v349 = (unsigned __int8 *)v666;
                                                                                                                                            LOBYTE(v347) = 0;
                                                                                                                                            v661 = v347;
                                                                                                                                            v672 = 0x7F1137FAB69605ELL;
                                                                                                                                            v350 = v346;
                                                                                                                                            v669 = (SIZE_T)v346;
                                                                                                                                            v351 = v345 & 7;
                                                                                                                                            if ( (v345 & 7) != 0 )
                                                                                                                                            {
                                                                                                                                              v632 = 0;
                                                                                                                                              v633 = 0;
                                                                                                                                              v634 = 0;
                                                                                                                                              LODWORD(v699) = 0;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v635 = *v349;
                                                                                                                                                v636 = 8 * v632;
                                                                                                                                                ++v349;
                                                                                                                                                if ( v632 >= 4 )
                                                                                                                                                  v633 |= v635 << (56 - v636);
                                                                                                                                                else
                                                                                                                                                  v634 |= v635 << (24 - v636);
                                                                                                                                                v632 = v699 + 1;
                                                                                                                                                LODWORD(v699) = v632;
                                                                                                                                              }
                                                                                                                                              while ( (int)v632 < (int)v351 );
                                                                                                                                              v5 = v680;
                                                                                                                                              LODWORD(v701) = v633;
                                                                                                                                              v637 = v634 ^ 0x92F65A5;
                                                                                                                                              LODWORD(lpMem) = v634;
                                                                                                                                              v638 = v633 ^ 0x699A899C;
                                                                                                                                              LODWORD(v699) = v634 ^ 0x92F65A5;
                                                                                                                                              v639 = v633 ^ 0x699A899C;
                                                                                                                                              v640 = 0;
                                                                                                                                              v645 = v308;
                                                                                                                                              v664 = v387;
                                                                                                                                              v653 = v386;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v667 = v350 + 1;
                                                                                                                                                if ( v640 >= 4 )
                                                                                                                                                {
                                                                                                                                                  v638 = __ROR4__(v638, 24);
                                                                                                                                                  v641 = v638;
                                                                                                                                                }
                                                                                                                                                else
                                                                                                                                                {
                                                                                                                                                  v637 = __ROR4__(v637, 24);
                                                                                                                                                  v641 = v637;
                                                                                                                                                }
                                                                                                                                                *v350 = v641;
                                                                                                                                                ++v640;
                                                                                                                                                v350 = v667;
                                                                                                                                              }
                                                                                                                                              while ( v640 < (int)v351 );
                                                                                                                                              v669 = (SIZE_T)v667;
                                                                                                                                              if ( v351 <= 4 )
                                                                                                                                              {
                                                                                                                                                v352 = 0;
                                                                                                                                                if ( v351 < 4 )
                                                                                                                                                  LODWORD(v699) = (unsigned int)v699 >> (8 * (4 - v351)) << (8 * (4 - v351));
                                                                                                                                              }
                                                                                                                                              else
                                                                                                                                              {
                                                                                                                                                v352 = v639 >> (8 * (8 - v351)) << (8 * (8 - v351));
                                                                                                                                              }
                                                                                                                                              v348 = v657;
                                                                                                                                              LOBYTE(v347) = v661;
                                                                                                                                            }
                                                                                                                                            else
                                                                                                                                            {
                                                                                                                                              v352 = 0;
                                                                                                                                              LODWORD(lpMem) = v345 & 7;
                                                                                                                                              LODWORD(v699) = 0;
                                                                                                                                              LODWORD(v701) = -1;
                                                                                                                                            }
                                                                                                                                            v353 = v345 >> 3;
                                                                                                                                            if ( v345 >> 3 )
                                                                                                                                            {
                                                                                                                                              v354 = HIDWORD(v672);
                                                                                                                                              v355 = v669;
                                                                                                                                              LODWORD(v675) = HIDWORD(v672) ^ 0xAB69605E;
                                                                                                                                              v356 = HIWORD(HIDWORD(v672));
                                                                                                                                              v357 = WORD2(v672);
                                                                                                                                              v358 = 24670;
                                                                                                                                              LODWORD(v673) = 43881;
                                                                                                                                              v677 = 0;
                                                                                                                                              LODWORD(v654) = WORD2(v672);
                                                                                                                                              v659 = 24670;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v359 = v349[3] | ((v349[2] | (((*v349 << 8) | v349[1]) << 8)) << 8);
                                                                                                                                                v360 = v349[7] | ((v349[6] | ((v349[5] | (v349[4] << 8)) << 8)) << 8);
                                                                                                                                                v667 = v349 + 8;
                                                                                                                                                v361 = v352 ^ v360 ^ (unsigned int)v675 ^ v699 ^ v359;
                                                                                                                                                v362 = v699 ^ v359 ^ (__ROR4__(v361, 22) + v357 * __ROR4__(v361 + 1419157410, 27));
                                                                                                                                                v363 = v361 ^ (43881 * __ROR4__(v354 + v362, 9) - __ROR4__(v362, 30));
                                                                                                                                                v364 = v362 ^ (v358 * (v363 - v357) - (v363 >> 13));
                                                                                                                                                v365 = v363 ^ (v356 * __ROR4__(v364 ^ (unsigned int)v673, 26) - __ROR4__(v364, 30));
                                                                                                                                                v366 = v364 ^ (v354 - (v365 ^ 0xAB69605E));
                                                                                                                                                v367 = v365 ^ (43881 * (v366 ^ v357)) ^ __ROR4__(v366, 6);
                                                                                                                                                v368 = v366 ^ (__ROR4__(v367, 30) + v659 * __ROR4__(v354 + v367, 15));
                                                                                                                                                v369 = v367 ^ (v356 * __ROR4__(v368 + 1419157410, 14) - __ROR4__(v368, 24));
                                                                                                                                                v370 = v368 ^ __ROR4__(v369, 10) ^ ((_DWORD)v654 * __ROR4__(v369 ^ 0xAB69605E, 12));
                                                                                                                                                v371 = v369 ^ (v370 >> 10) ^ (43881 * (v356 ^ v370));
                                                                                                                                                v357 = (int)v654;
                                                                                                                                                v372 = v370 ^ (v356 * (v659 + __ROR4__(~v371, 5)));
                                                                                                                                                v373 = v371 ^ (v372 - v356) ^ 0xAB69605E;
                                                                                                                                                v374 = v372 ^ ((v373 >> 2) + (_DWORD)v654 * __ROR4__(v356 ^ v373, 30));
                                                                                                                                                v375 = v373 ^ (__ROR4__(v374, 25) + 43881 * __ROR4__(v374 - v354, 6));
                                                                                                                                                v376 = v374 ^ (v659 * (v375 ^ (unsigned int)v654) + __ROR4__(v375, 9));
                                                                                                                                                v377 = v375 ^ (__ROR4__(v376, 25) + v356 * __ROR4__(v376 ^ (unsigned int)v673, 27));
                                                                                                                                                v378 = v376 ^ v377 ^ (unsigned int)v675;
                                                                                                                                                v379 = v377 ^ ((_DWORD)v654 * (__ROR4__(v378, 3) - 43881));
                                                                                                                                                v380 = v378 ^ (v659 * __ROR4__(v379 - v354, 1) - __ROR4__(v379, 6));
                                                                                                                                                v355 += 8LL;
                                                                                                                                                v381 = v379 ^ (__ROR4__(v380, 18) + v356 * __ROR4__(v380 - 1419157410, 29));
                                                                                                                                                v382 = v380 ^ ((_DWORD)v654 * __ROR4__(v381 - 1419157410, 17) - __ROR4__(v381, 14));
                                                                                                                                                v358 = v659;
                                                                                                                                                v383 = v381 ^ (v382 >> 3) ^ (43881 * (v659 ^ v382));
                                                                                                                                                v352 = v701 ^ v383;
                                                                                                                                                LODWORD(v701) = v360;
                                                                                                                                                v384 = v382 ^ __ROR4__(v383, 30) ^ (v659 * __ROR4__(v354 ^ v383, 28));
                                                                                                                                                v349 = (unsigned __int8 *)v667;
                                                                                                                                                v385 = (unsigned int)lpMem ^ v384;
                                                                                                                                                *(_BYTE *)(v355 - 5) = v385;
                                                                                                                                                *(_BYTE *)(v355 - 1) = v352;
                                                                                                                                                *(_BYTE *)(v355 - 6) = __ROR4__(v385, 8);
                                                                                                                                                *(_BYTE *)(v355 - 2) = __ROR4__(v352, 8);
                                                                                                                                                *(_BYTE *)(v355 - 7) = __ROR4__(v385, 16);
                                                                                                                                                *(_BYTE *)(v355 - 3) = __ROR4__(v352, 16);
                                                                                                                                                *(_BYTE *)(v355 - 8) = __ROR4__(v385, 24);
                                                                                                                                                *(_BYTE *)(v355 - 4) = __ROR4__(v352, 24);
                                                                                                                                                LODWORD(v699) = v385;
                                                                                                                                                LODWORD(lpMem) = v359;
                                                                                                                                                ++v677;
                                                                                                                                              }
                                                                                                                                              while ( v677 < v353 );
                                                                                                                                              v5 = v680;
                                                                                                                                              v13 = v698;
                                                                                                                                              v386 = v653;
                                                                                                                                              v387 = v664;
                                                                                                                                              v345 = (unsigned __int64)v676;
                                                                                                                                              v348 = v657;
                                                                                                                                              LOBYTE(v347) = v661;
                                                                                                                                            }
                                                                                                                                            if ( v345 )
                                                                                                                                            {
                                                                                                                                              v388 = 0;
                                                                                                                                              if ( v345 < 0x20 )
                                                                                                                                                goto LABEL_968;
                                                                                                                                              v389 = 0;
                                                                                                                                              v390 = 0;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v389 = _mm_xor_ps(v389, (__m128)_mm_loadu_si128((const __m128i *)&v348[v388]));
                                                                                                                                                v391 = (__m128)_mm_loadu_si128((const __m128i *)&v348[v388 + 16]);
                                                                                                                                                v388 += 32LL;
                                                                                                                                                v392 = _mm_xor_ps(v391, v390);
                                                                                                                                                v390 = v392;
                                                                                                                                              }
                                                                                                                                              while ( v388 < (v345 & 0xFFFFFFFFFFFFFFE0uLL) );
                                                                                                                                              v393 = _mm_xor_ps(v389, v392);
                                                                                                                                              v394 = _mm_xor_ps(v393, (__m128)_mm_srli_si128((__m128i)v393, 8));
                                                                                                                                              v395 = _mm_xor_ps(v394, (__m128)_mm_srli_si128((__m128i)v394, 4));
                                                                                                                                              v396 = _mm_xor_ps(v395, (__m128)_mm_srli_si128((__m128i)v395, 2));
                                                                                                                                              LOBYTE(v347) = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v396, (__m128)_mm_srli_si128((__m128i)v396, 1)));
                                                                                                                                              if ( v388 < v345 )
                                                                                                                                              {
LABEL_968:
                                                                                                                                                do
                                                                                                                                                  LOBYTE(v347) = v348[v388++] ^ v347;
                                                                                                                                                while ( v388 < v345 );
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                            if ( (unsigned __int8)v347 != *(_QWORD *)(v345 + v666) )
                                                                                                                                            {
                                                                                                                                              v397 = GetProcessHeap();
                                                                                                                                              HeapFree(v397, 0, v657);
                                                                                                                                              goto LABEL_492;
                                                                                                                                            }
                                                                                                                                            Size = (size_t)v348;
                                                                                                                                            LODWORD(v698) = 0;
                                                                                                                                            v699 = (SIZE_T)v348;
                                                                                                                                            if ( (unsigned int)v345 >= 4 )
                                                                                                                                            {
                                                                                                                                              v566 = RtlULongLongAdd(v348, 4, &v699);
                                                                                                                                              if ( v566 < 0 )
                                                                                                                                                goto LABEL_520;
                                                                                                                                              v566 = RtlUIntAdd(0, 4, &v698);
                                                                                                                                              if ( v566 < 0 )
                                                                                                                                                goto LABEL_520;
                                                                                                                                              if ( (unsigned int)(v345 - v698) >= 4 )
                                                                                                                                              {
                                                                                                                                                v566 = RtlULongLongAdd(v699, 4, &v699);
                                                                                                                                                if ( v566 < 0 )
                                                                                                                                                  goto LABEL_520;
                                                                                                                                                v566 = RtlUIntAdd(v567, 4, &v698);
                                                                                                                                                if ( v566 < 0 )
                                                                                                                                                  goto LABEL_520;
                                                                                                                                                if ( (int)v345 - (int)v698 >= v568 )
                                                                                                                                                {
                                                                                                                                                  v566 = RtlUIntAdd((unsigned int)v698, v568, &v698);
                                                                                                                                                  if ( v566 < 0 )
                                                                                                                                                  {
LABEL_520:
                                                                                                                                                    LODWORD(v699) = v566 | 0x10000000;
                                                                                                                                                    goto LABEL_521;
                                                                                                                                                  }
                                                                                                                                                  v571 = (const void *)v699;
                                                                                                                                                  v677 = (unsigned int)v570;
                                                                                                                                                  if ( (unsigned __int64)v569 + (unsigned int)v345 >= v699 + v570 && (unsigned __int64)v569 + (unsigned int)v345 - (unsigned int)v570 - v699 < 8 )
                                                                                                                                                  {
                                                                                                                                                    v572 = 0;
                                                                                                                                                    LODWORD(v698) = *v569;
                                                                                                                                                    v573 = 0;
                                                                                                                                                    lpMem = 0;
                                                                                                                                                    v701 = 0;
                                                                                                                                                    v669 = 0;
                                                                                                                                                    if ( v699 )
                                                                                                                                                    {
                                                                                                                                                      LODWORD(v699) = RtlULongLongAdd(v699, (unsigned int)v570, &lpMem);
                                                                                                                                                      if ( (v699 & 0x80000000) == 0LL )
                                                                                                                                                      {
                                                                                                                                                        v576 = lpMem;
                                                                                                                                                        while ( 1 )
                                                                                                                                                        {
                                                                                                                                                          if ( v574 >= (unsigned __int64)v576 )
                                                                                                                                                          {
                                                                                                                                                            if ( (LPVOID)v574 == v576 )
                                                                                                                                                              goto LABEL_711;
LABEL_911:
                                                                                                                                                            v566 = -1073741811;
                                                                                                                                                            goto LABEL_520;
                                                                                                                                                          }
                                                                                                                                                          LODWORD(v699) = RtlULongLongAdd(v574, 4, &v701);
                                                                                                                                                          if ( (v699 & 0x80000000) != 0LL )
                                                                                                                                                            break;
                                                                                                                                                          if ( v701 > v578 )
                                                                                                                                                            goto LABEL_911;
                                                                                                                                                          v579 = *v577;
                                                                                                                                                          LODWORD(v699) = 0;
                                                                                                                                                          v566 = RtlUIntAdd(4, v579, &v699);
                                                                                                                                                          if ( v566 < 0 )
                                                                                                                                                            goto LABEL_520;
                                                                                                                                                          LODWORD(v699) = RtlULongLongAdd(v580, (unsigned int)v699, &v669);
                                                                                                                                                          if ( (v699 & 0x80000000) != 0LL )
                                                                                                                                                            break;
                                                                                                                                                          v574 = v669;
                                                                                                                                                          if ( v669 > (unsigned __int64)v576 )
                                                                                                                                                            goto LABEL_911;
                                                                                                                                                          ++v573;
                                                                                                                                                        }
                                                                                                                                                        v575 = v698;
                                                                                                                                                      }
                                                                                                                                                      v582 = v665;
                                                                                                                                                    }
                                                                                                                                                    else
                                                                                                                                                    {
                                                                                                                                                      LODWORD(v699) = 0;
LABEL_711:
                                                                                                                                                      if ( (_DWORD)v570 )
                                                                                                                                                      {
                                                                                                                                                        v581 = GetProcessHeap();
                                                                                                                                                        v572 = HeapAlloc(v581, 8u, v677);
                                                                                                                                                        if ( !v572 )
                                                                                                                                                        {
                                                                                                                                                          v566 = -1073741801;
                                                                                                                                                          goto LABEL_520;
                                                                                                                                                        }
                                                                                                                                                        LODWORD(v699) = 0;
                                                                                                                                                      }
                                                                                                                                                      if ( v571 )
                                                                                                                                                        memcpy_0(v572, v571, v677);
                                                                                                                                                      v575 = v698;
                                                                                                                                                      v582 = v573;
                                                                                                                                                      v665 = v573;
                                                                                                                                                      dwBytesa = v572;
                                                                                                                                                    }
                                                                                                                                                    v566 = v699;
                                                                                                                                                    if ( (v699 & 0x80000000) != 0LL || v575 == v582 )
                                                                                                                                                      goto LABEL_520;
                                                                                                                                                  }
                                                                                                                                                }
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                            v566 = -1073741762;
                                                                                                                                            goto LABEL_520;
                                                                                                                                          }
                                                                                                                                          goto LABEL_889;
                                                                                                                                        }
                                                                                                                                        LODWORD(v699) = -805306345;
                                                                                                                                        v311 = v308;
                                                                                                                                      }
                                                                                                                                      else
                                                                                                                                      {
                                                                                                                                        LODWORD(v699) = -805306306;
                                                                                                                                        v311 = v308;
                                                                                                                                      }
                                                                                                                                    }
                                                                                                                                    else
                                                                                                                                    {
                                                                                                                                      LODWORD(v699) = -805306306;
                                                                                                                                      v311 = v308;
                                                                                                                                    }
                                                                                                                                  }
                                                                                                                                }
                                                                                                                              }
                                                                                                                            }
                                                                                                                          }
                                                                                                                        }
LABEL_432:
                                                                                                                        if ( !v386 )
                                                                                                                        {
LABEL_434:
                                                                                                                          if ( v387 )
                                                                                                                          {
                                                                                                                            v313 = (void *)v387[1];
                                                                                                                            if ( v313 )
                                                                                                                            {
                                                                                                                              v314 = GetProcessHeap();
                                                                                                                              HeapFree(v314, 0, v313);
                                                                                                                              v387[1] = 0;
                                                                                                                            }
                                                                                                                            v315 = (void *)v387[3];
                                                                                                                            if ( v315 )
                                                                                                                            {
                                                                                                                              v316 = GetProcessHeap();
                                                                                                                              HeapFree(v316, 0, v315);
                                                                                                                              v387[3] = 0;
                                                                                                                            }
                                                                                                                            v317 = (void *)v387[5];
                                                                                                                            if ( v317 )
                                                                                                                            {
                                                                                                                              v318 = GetProcessHeap();
                                                                                                                              HeapFree(v318, 0, v317);
                                                                                                                              v387[5] = 0;
                                                                                                                            }
                                                                                                                            v319 = GetProcessHeap();
                                                                                                                            HeapFree(v319, 0, v387);
                                                                                                                          }
                                                                                                                          if ( v311 )
                                                                                                                          {
                                                                                                                            v320 = GetProcessHeap();
                                                                                                                            HeapFree(v320, 0, v311);
                                                                                                                          }
                                                                                                                          v321 = v688;
                                                                                                                          if ( v688 )
                                                                                                                          {
                                                                                                                            v322 = GetProcessHeap();
                                                                                                                            HeapFree(v322, 0, v321);
                                                                                                                          }
                                                                                                                          v323 = v655;
                                                                                                                          if ( v655 )
                                                                                                                          {
                                                                                                                            v324 = (void *)*((_QWORD *)v655 + 1);
                                                                                                                            if ( v324 )
                                                                                                                            {
                                                                                                                              v325 = GetProcessHeap();
                                                                                                                              HeapFree(v325, 0, v324);
                                                                                                                              v323[1] = 0;
                                                                                                                            }
                                                                                                                            v326 = (void *)v323[3];
                                                                                                                            if ( v326 )
                                                                                                                            {
                                                                                                                              v327 = GetProcessHeap();
                                                                                                                              HeapFree(v327, 0, v326);
                                                                                                                              v323[3] = 0;
                                                                                                                            }
                                                                                                                            v328 = (void *)v323[5];
                                                                                                                            if ( v328 )
                                                                                                                            {
                                                                                                                              v329 = GetProcessHeap();
                                                                                                                              HeapFree(v329, 0, v328);
                                                                                                                              v323[5] = 0;
                                                                                                                            }
                                                                                                                            v330 = GetProcessHeap();
                                                                                                                            HeapFree(v330, 0, v323);
                                                                                                                          }
                                                                                                                          v331 = (void *)Size;
                                                                                                                          if ( Size )
                                                                                                                          {
                                                                                                                            v332 = GetProcessHeap();
                                                                                                                            HeapFree(v332, 0, v331);
                                                                                                                          }
                                                                                                                          v306 = dwBytesa;
                                                                                                                          if ( (v699 & 0x80000000) == 0LL && v665 )
                                                                                                                          {
                                                                                                                            if ( !dwBytesa )
                                                                                                                            {
                                                                                                                              v301 = v658;
                                                                                                                              v300 = v662;
                                                                                                                              goto LABEL_461;
                                                                                                                            }
                                                                                                                            v698 = (SIZE_T)dwBytesa;
                                                                                                                            if ( (int)RtlULongLongAdd(dwBytesa, 4, &v698) >= 0 )
                                                                                                                            {
                                                                                                                              v583 = (int *)v698;
                                                                                                                              if ( !*dwBytesa )
                                                                                                                                v583 = 0;
                                                                                                                              if ( *dwBytesa == 4 && *v583 >= 0 && v333 > 1 )
                                                                                                                              {
                                                                                                                                v584 = (SIZE_T)dwBytesa;
                                                                                                                                v585 = 0;
                                                                                                                                v698 = (SIZE_T)dwBytesa;
                                                                                                                                while ( !v585 )
                                                                                                                                {
                                                                                                                                  if ( (int)RtlULongLongAdd(v584, 4, &v698) < 0 || (int)RtlULongLongAdd(v698, v586, &v698) < 0 )
                                                                                                                                    goto LABEL_460;
                                                                                                                                  v584 = v698;
                                                                                                                                  v585 = v587 + 1;
                                                                                                                                }
                                                                                                                                RtlULongLongAdd(v584, 4, &v698);
                                                                                                                                v301 = v658;
                                                                                                                                v300 = v662;
                                                                                                                                goto LABEL_461;
                                                                                                                              }
                                                                                                                            }
                                                                                                                          }
LABEL_460:
                                                                                                                          v301 = v658;
                                                                                                                          v300 = v662;
LABEL_461:
                                                                                                                          v334 = (void *)v663[1];
                                                                                                                          v663[0] = 0;
                                                                                                                          if ( v663[1] )
                                                                                                                          {
                                                                                                                            v335 = GetProcessHeap();
                                                                                                                            HeapFree(v335, 0, v334);
                                                                                                                            v663[1] = 0;
                                                                                                                          }
                                                                                                                          if ( v306 )
                                                                                                                          {
                                                                                                                            v336 = GetProcessHeap();
                                                                                                                            HeapFree(v336, 0, v306);
                                                                                                                          }
                                                                                                                          if ( v300 )
                                                                                                                          {
                                                                                                                            v337 = GetProcessHeap();
                                                                                                                            HeapFree(v337, 0, v300);
                                                                                                                          }
                                                                                                                          if ( v301 )
                                                                                                                          {
                                                                                                                            v338 = GetProcessHeap();
                                                                                                                            HeapFree(v338, 0, v301);
                                                                                                                          }
LABEL_24:
                                                                                                                          v14 = v683;
                                                                                                                          v4 = (int *)v5;
LABEL_25:
                                                                                                                          if ( v13 >= 0 )
                                                                                                                          {
                                                                                                                            if ( v14 == 4 )
                                                                                                                            {
                                                                                                                              v13 = 0;
                                                                                                                              if ( v4 )
                                                                                                                                v588 = v4;
                                                                                                                              else
                                                                                                                                v588 = 0;
                                                                                                                              v292 = *v588;
LABEL_392:
                                                                                                                              if ( v4 )
                                                                                                                                LocalFree(v4);
                                                                                                                              if ( v13 >= 0 && v292 )
                                                                                                                              {
                                                                                                                                v293 = hSCObject;
                                                                                                                              }
                                                                                                                              else
                                                                                                                              {
                                                                                                                                v293 = hSCObject;
                                                                                                                                v294 = InitializeService(hSCObject, "SSTPSVC", 0x78u, &v678);
                                                                                                                                v1 = v294;
                                                                                                                                if ( v294 )
                                                                                                                                {
                                                                                                                                  if ( g_dwTraceId != -1 )
                                                                                                                                    TracePrintfExA(g_dwTraceId, 0xCu, "SSTP service initialization failed, error = %d", v294);
                                                                                                                                  v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                                                                                    goto LABEL_321;
                                                                                                                                  v297 = 82;
                                                                                                                                  goto LABEL_928;
                                                                                                                                }
                                                                                                                              }
                                                                                                                              v295 = InitializeService(v293, "RASMAN", 0x78u, &v678);
                                                                                                                              v1 = v295;
                                                                                                                              if ( !v295 )
                                                                                                                              {
                                                                                                                                if ( v678 )
                                                                                                                                {
                                                                                                                                  if ( g_dwTraceId != -1 )
                                                                                                                                    TracePrintfExA(g_dwTraceId, 0xCu, "Rasman service was started by RasInitialize");
                                                                                                                                  if ( (unsigned int)IsModemPresent() )
                                                                                                                                  {
                                                                                                                                    v642 = InitializeService(v293, "TAPISRV", 5u, &v678);
                                                                                                                                    v1 = v642;
                                                                                                                                    if ( v642 )
                                                                                                                                    {
                                                                                                                                      if ( g_dwTraceId != -1 )
                                                                                                                                        TracePrintfExA(g_dwTraceId, 0xCu, "TapiSrv service initialization failed, error = %d", v642);
                                                                                                                                      v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                                                                                        goto LABEL_321;
                                                                                                                                      v297 = 84;
                                                                                                                                      goto LABEL_928;
                                                                                                                                    }
                                                                                                                                    if ( v678 )
                                                                                                                                    {
                                                                                                                                      if ( g_dwTraceId != -1 )
                                                                                                                                        TracePrintfExA(g_dwTraceId, 0xCu, "TapiSrv was started by RasInitialize");
                                                                                                                                    }
                                                                                                                                    else if ( g_dwTraceId != -1 )
                                                                                                                                    {
                                                                                                                                      TracePrintfExA(g_dwTraceId, 0xCu, "Waiting for TapiSrv to start is done");
                                                                                                                                    }
                                                                                                                                  }
                                                                                                                                }
                                                                                                                                if ( !(unsigned int)IsRasmanProcess() )
                                                                                                                                {
                                                                                                                                  Binding = (RPC_BINDING_HANDLE)g_hBinding;
                                                                                                                                  if ( g_hBinding )
                                                                                                                                    goto LABEL_321;
                                                                                                                                  EnterCriticalSection(&g_RasCriticalSection);
                                                                                                                                  v258 = RasRpcConnect(0, &Binding);
                                                                                                                                  LeaveCriticalSection(&g_RasCriticalSection);
                                                                                                                                  if ( v258 )
                                                                                                                                  {
                                                                                                                                    if ( g_dwTraceId != -1 )
                                                                                                                                      TracePrintfExA(g_dwTraceId, 0xCu, "RasInitialize: Failed to connect to local server. %d\n", v258);
                                                                                                                                    v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                                                                                                    {
                                                                                                                                      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v258);
                                                                                                                                      v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    }
                                                                                                                                    v1 = 711;
                                                                                                                                    if ( v296 == &WPP_GLOBAL_Control || (*((_BYTE *)v296 + 28) & 0x40) == 0 || *((_BYTE *)v296 + 25) < 2u )
                                                                                                                                      goto LABEL_321;
                                                                                                                                    v297 = 86;
                                                                                                                                    goto LABEL_928;
                                                                                                                                  }
                                                                                                                                  v259 = RasReferenceRasman(1);
                                                                                                                                  v1 = v259;
                                                                                                                                  if ( v259 )
                                                                                                                                  {
                                                                                                                                    if ( g_dwTraceId != -1 )
                                                                                                                                      TracePrintfExA(g_dwTraceId, 0xCu, "RasInitialize: failed to reference rasman. %d\n", v259);
                                                                                                                                    v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                                                                                                    {
                                                                                                                                      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
                                                                                                                                      v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    }
                                                                                                                                    v1 = 711;
                                                                                                                                    if ( v296 == &WPP_GLOBAL_Control || (*((_BYTE *)v296 + 28) & 0x40) == 0 || *((_BYTE *)v296 + 25) < 2u )
                                                                                                                                      goto LABEL_321;
                                                                                                                                    v297 = 88;
                                                                                                                                    goto LABEL_928;
                                                                                                                                  }
                                                                                                                                }
                                                                                                                                g_fRasInitialized = 1;
LABEL_321:
                                                                                                                                CloseServiceHandle(v293);
LABEL_322:
                                                                                                                                v2 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                goto LABEL_323;
                                                                                                                              }
                                                                                                                              if ( g_dwTraceId != -1 )
                                                                                                                                TracePrintfExA(g_dwTraceId, 0xCu, "RASMAN service initialization failed, error = %d", v295);
                                                                                                                              v296 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                                                                                goto LABEL_321;
                                                                                                                              v297 = 83;
LABEL_928:
                                                                                                                              WPP_SF_d(v296[2], v297, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
                                                                                                                              goto LABEL_321;
                                                                                                                            }
                                                                                                                            v13 = -1073418210;
LABEL_391:
                                                                                                                            v292 = v681;
                                                                                                                            goto LABEL_392;
                                                                                                                          }
LABEL_89:
                                                                                                                          switch ( v13 )
                                                                                                                          {
                                                                                                                            case -805306316:
                                                                                                                              v13 = -1073418222;
                                                                                                                              break;
                                                                                                                            case -805306139:
                                                                                                                            case -1073425151:
                                                                                                                              v13 = -1073418201;
                                                                                                                              break;
                                                                                                                            case -805306306:
                                                                                                                              v13 = -1073418200;
                                                                                                                              break;
                                                                                                                            case -2147024774:
                                                                                                                              v13 = -1073418210;
                                                                                                                              break;
                                                                                                                          }
                                                                                                                          goto LABEL_391;
                                                                                                                        }
LABEL_433:
                                                                                                                        v312 = GetProcessHeap();
                                                                                                                        HeapFree(v312, 0, v386);
                                                                                                                        goto LABEL_434;
                                                                                                                      }
                                                                                                                      goto LABEL_657;
                                                                                                                    }
                                                                                                                    v529 = GetLastError();
                                                                                                                    v543 = v529 < 0;
                                                                                                                    if ( v529 <= 0 )
                                                                                                                    {
LABEL_656:
                                                                                                                      if ( !v543 )
                                                                                                                      {
                                                                                                                        LODWORD(v699) = -2147467259;
LABEL_764:
                                                                                                                        v644 = v308;
LABEL_765:
                                                                                                                        v311 = v644;
                                                                                                                        goto LABEL_432;
                                                                                                                      }
LABEL_657:
                                                                                                                      v530 = (unsigned int)lpMem;
                                                                                                                      if ( v529 == -805306333 )
                                                                                                                      {
                                                                                                                        LODWORD(v699) = -2147024774;
                                                                                                                        v311 = v308;
                                                                                                                        goto LABEL_432;
                                                                                                                      }
                                                                                                                      if ( v529 >= 0 )
                                                                                                                        goto LABEL_639;
                                                                                                                      LODWORD(v699) = v529;
                                                                                                                      goto LABEL_764;
                                                                                                                    }
                                                                                                                  }
                                                                                                                  else
                                                                                                                  {
                                                                                                                    v529 = GetLastError();
                                                                                                                    v543 = v529 < 0;
                                                                                                                    if ( v529 <= 0 )
                                                                                                                      goto LABEL_656;
                                                                                                                  }
                                                                                                                  v529 = (unsigned __int16)v529 | 0x80070000;
                                                                                                                  v543 = v529 < 0;
                                                                                                                  goto LABEL_656;
                                                                                                                }
                                                                                                              }
                                                                                                            }
                                                                                                            v310 = -1073741811;
                                                                                                          }
                                                                                                        }
LABEL_430:
                                                                                                        v311 = v644;
LABEL_431:
                                                                                                        LODWORD(v699) = v310;
                                                                                                        goto LABEL_432;
                                                                                                      }
                                                                                                    }
                                                                                                  }
                                                                                                }
                                                                                              }
                                                                                            }
                                                                                            v514 = GetProcessHeap();
                                                                                            HeapFree(v514, 0, v308);
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                  v308 = 0;
                                                                                  goto LABEL_428;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                LODWORD(v673) = v627 >> (8 * (8 - v415)) << (8 * (8 - v415));
                                                                              }
                                                                              v416 = v701;
                                                                              goto LABEL_510;
                                                                            }
                                                                            v301 = v658;
                                                                            v300 = v662;
LABEL_424:
                                                                            v306 = 0;
                                                                            goto LABEL_461;
                                                                          }
                                                                          v496 = (v674 + 7) & 0xFFFFFFF8;
                                                                          if ( v496 >= v674 )
                                                                          {
                                                                            v674 = (v674 + 7) & 0xFFFFFFF8;
                                                                            v497 = v496;
                                                                            v498 = GetProcessHeap();
                                                                            v499 = (char *)HeapAlloc(v498, 8u, v497);
                                                                            v500 = v499;
                                                                            if ( v499 )
                                                                            {
                                                                              v657 = v499;
                                                                              *(_DWORD *)v499 = v663[0];
                                                                              LODWORD(lpMem) = RtlULongLongAdd(
                                                                                                 v499,
                                                                                                 4,
                                                                                                 &v657);
                                                                              if ( (int)lpMem >= 0
                                                                                && (v398 = v657,
                                                                                    *(_DWORD *)v657 = HIDWORD(v663[0]),
                                                                                    LODWORD(lpMem) = RtlULongLongAdd(v398, 4, &v657),
                                                                                    (int)lpMem >= 0) )
                                                                              {
                                                                                *(_QWORD *)&v500[v674 - 8] = Size;
                                                                                memcpy_0(
                                                                                  v657,
                                                                                  (const void *)v663[1],
                                                                                  HIDWORD(v663[0]));
                                                                                v400 = v674;
                                                                                v386 = v500;
                                                                                v659 = v674;
                                                                                v653 = v500;
                                                                              }
                                                                              else
                                                                              {
                                                                                v399 = GetProcessHeap();
                                                                                HeapFree(v399, 0, v500);
                                                                                v400 = 0;
                                                                              }
                                                                              v401 = (int)lpMem;
                                                                              v311 = 0;
                                                                              goto LABEL_497;
                                                                            }
                                                                          }
                                                                          v301 = v658;
                                                                        }
                                                                      }
LABEL_423:
                                                                      v300 = v304;
                                                                      goto LABEL_424;
                                                                    }
                                                                  }
LABEL_20:
                                                                  v13 = -1073741675;
LABEL_21:
                                                                  LODWORD(v698) = v13;
                                                                  goto LABEL_79;
                                                                }
                                                                goto LABEL_34;
                                                              }
                                                              v46 = GetProcessHeap();
                                                              v47 = v664;
LABEL_134:
                                                              HeapFree(v46, 0, v47);
                                                              goto LABEL_135;
                                                            }
LABEL_111:
                                                            v49 = GetProcessHeap();
                                                            HeapFree(v49, 0, v646);
                                                            goto LABEL_112;
                                                          }
                                                          v271 = GetProcessHeap();
                                                          v676 = HeapAlloc(v271, 8u, v672);
                                                          v268 = v676;
                                                          if ( v676 )
                                                          {
                                                            v263 = v698;
                                                            v264 = 0;
                                                            v261 = (_DWORD *)v666;
                                                            goto LABEL_348;
                                                          }
                                                          v260 = -1073741801;
LABEL_332:
                                                          v48 = v646;
                                                          v13 = v260 | 0x10000000;
                                                          LODWORD(v698) = v13;
                                                          goto LABEL_110;
                                                        }
                                                        if ( v267 >= (unsigned __int64)v261 )
                                                        {
                                                          v269 = v651;
                                                          v264 = 0;
                                                          v270 = v643;
                                                          while ( 1 )
                                                          {
                                                            v265 = v261;
                                                            if ( (unsigned __int64)v261 >= v267 )
                                                              break;
                                                            if ( v261 + 1 < v261 )
                                                              goto LABEL_331;
                                                            if ( (unsigned __int64)(v261 + 1) > v267 )
                                                              goto LABEL_842;
                                                            if ( *v261 >= 0xFFFFFFFC )
                                                              goto LABEL_331;
                                                            v48 = v646;
                                                            v261 = (_DWORD *)((char *)v261 + (unsigned int)(*v261 + 4));
                                                            if ( v261 < v265 )
                                                              goto LABEL_340;
                                                            v262 = v653;
                                                            v651 = v269;
                                                            v643 = v270;
                                                            if ( (unsigned __int64)v261 > v267 )
                                                            {
                                                              v264 = -1073741811;
                                                              goto LABEL_841;
                                                            }
                                                            LODWORD(v698) = ++v263;
                                                            v264 = 0;
                                                          }
                                                          if ( v261 == (_DWORD *)v267 )
                                                          {
                                                            v261 = (_DWORD *)v666;
                                                            v266 = (unsigned int *)v664;
                                                            goto LABEL_347;
                                                          }
LABEL_842:
                                                          v260 = -1073741811;
                                                          goto LABEL_332;
                                                        }
LABEL_331:
                                                        v260 = -1073741675;
                                                        goto LABEL_332;
                                                      }
                                                    }
                                                    v260 = -1073741762;
                                                    goto LABEL_332;
                                                  }
                                                }
                                                else
                                                {
                                                  v246 = v659;
                                                }
                                                do
                                                  v246 ^= *((_BYTE *)v207 + v248++);
                                                while ( v248 < v205 );
                                                goto LABEL_299;
                                              }
                                              v13 = -805306355;
                                              LODWORD(v698) = -805306355;
                                            }
                                            else
                                            {
                                              v13 = -805306355;
                                              LODWORD(v698) = -805306355;
                                            }
                                          }
                                          else
                                          {
                                            v13 = -805306355;
                                            LODWORD(v698) = -805306355;
                                          }
LABEL_812:
                                          v643 = v654;
                                          goto LABEL_268;
                                        }
                                        v643 = v654;
                                        v48 = Src;
LABEL_216:
                                        v646 = v48;
                                        goto LABEL_110;
                                      }
                                      v190 = v698;
                                      goto LABEL_815;
                                    }
                                    goto LABEL_213;
                                  }
                                  v13 = -805306306;
                                  v643 = v654;
LABEL_313:
                                  v651 = v169;
                                  goto LABEL_267;
                                }
                                v13 = -2147024774;
LABEL_315:
                                v169 = v651;
                                v643 = v654;
                                goto LABEL_313;
                              }
                            }
                            else
                            {
                              LastError = GetLastError();
                              LODWORD(v698) = LastError;
                              v13 = LastError;
                              if ( LastError <= 0 )
                                goto LABEL_245;
                            }
                            v13 = (unsigned __int16)LastError | 0x80070000;
                            LODWORD(v698) = v13;
                            goto LABEL_245;
                          }
                          v13 = -2147418113;
                          v643 = v160;
                          v646 = v158;
                        }
                      }
                      else
                      {
                        v13 = -1073741811;
                        v643 = lpMem;
                      }
LABEL_109:
                      LODWORD(v698) = v13;
                      v48 = v646;
                      goto LABEL_110;
                    }
                  }
LABEL_29:
                  v13 = -805306219;
                  LODWORD(v698) = -805306219;
                  goto LABEL_79;
                }
                goto LABEL_77;
              }
              LODWORD(v701) = 0;
              LODWORD(v698) = RtlUIntAdd(4, 4, &v701);
              v13 = v698;
              if ( (v698 & 0x80000000) == 0LL )
              {
                LODWORD(v698) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v701, (char *)cchMax + 4);
                v13 = v698;
                if ( (v698 & 0x80000000) == 0LL )
                  goto LABEL_103;
              }
LABEL_78:
              if ( v13 < 0 )
                goto LABEL_79;
              goto LABEL_180;
            }
            v13 = -1073741789;
          }
          else
          {
            LODWORD(v701) = 0;
            LODWORD(v698) = RtlUIntAdd(4, (unsigned int)v28, &v701);
            v13 = v698;
            if ( (v698 & 0x80000000) != 0LL )
            {
              v30 = 4;
              goto LABEL_72;
            }
            v607 = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v701, (char *)cchMax + 4);
            v30 = 4;
            v13 = v607;
            LODWORD(v698) = v607;
            if ( v607 < 0 )
              goto LABEL_72;
            v30 = 5;
            LODWORD(cchMax[0]) = 5;
            v13 = 0;
          }
        }
        else
        {
          v30 = 4;
          v13 = -1073741811;
        }
        LODWORD(v698) = v13;
        goto LABEL_72;
      }
      v682 = -1;
    }
LABEL_34:
    v13 = -1073741675;
LABEL_35:
    LODWORD(v698) = v13;
    goto LABEL_78;
  }
  result = GetLastError();
  v1 = result;
  if ( !result )
    goto LABEL_322;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = 81;
LABEL_773:
    WPP_SF_d(v2[2], v3, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, result);
    goto LABEL_322;
  }
LABEL_323:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 89, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000b230  push    rbp
0x18000b232  push    rbx
0x18000b233  push    rsi
0x18000b234  push    r15
0x18000b236  lea     rbp, [rsp-138h]
0x18000b23e  sub     rsp, 238h
0x18000b245  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b24c  lea     rsi, WPP_GLOBAL_Control
0x18000b253  cmp     rcx, rsi
0x18000b256  jnz     short loc_18000B2CD
0x18000b258  xor     r15d, r15d
0x18000b25b  lea     rcx, [rbp+150h+arg_0]
0x18000b262  mov     [rbp+150h+var_120], r15d
0x18000b266  mov     [rbp+150h+Binding], r15
0x18000b26d  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b274  call    GetProcessLowBoxStatus
0x18000b279  cmp     dword ptr [rbp+150h+arg_0], r15d
0x18000b280  jnz     short loc_18000B287
0x18000b282  call    DebugInitEx
0x18000b287  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000b28e  jnz     loc_18000D336
0x18000b294  call    RasInitializeNoWait
0x18000b299  mov     ebx, eax
0x18000b29b  test    eax, eax
0x18000b29d  jz      short loc_18000B2F7
0x18000b29f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2a6  cmp     rcx, rsi
0x18000b2a9  jz      loc_18000D445
0x18000b2af  test    byte ptr [rcx+1Ch], 40h
0x18000b2b3  jz      loc_18000D43E
0x18000b2b9  cmp     byte ptr [rcx+19h], 2
0x18000b2bd  jb      loc_18000D43E
0x18000b2c3  mov     edx, 50h ; 'P'
0x18000b2c8  jmp     loc_180010673
0x18000b2cd  test    byte ptr [rcx+1Ch], 40h
0x18000b2d1  jz      short loc_18000B258
0x18000b2d3  cmp     byte ptr [rcx+19h], 6
0x18000b2d7  jb      loc_18000B258
0x18000b2dd  mov     rcx, [rcx+10h]
0x18000b2e1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000b2e8  mov     edx, 4Fh ; 'O'
0x18000b2ed  call    WPP_SF_
0x18000b2f2  jmp     loc_18000B258
0x18000b2f7  xor     edx, edx; lpDatabaseName
0x18000b2f9  xor     ecx, ecx; lpMachineName
0x18000b2fb  mov     r8d, 1; dwDesiredAccess
0x18000b301  call    cs:__imp_OpenSCManagerA
0x18000b308  nop     dword ptr [rax+rax+00h]
0x18000b30d  mov     [rbp+150h+hSCObject], rax
0x18000b314  test    rax, rax
0x18000b317  jz      loc_18001068B
0x18000b31d  mov     [rsp+250h+var_20], rdi
0x18000b325  mov     rbx, r15
0x18000b328  mov     [rsp+250h+var_28], r12
0x18000b330  mov     edx, 4; uBytes
0x18000b335  mov     [rsp+250h+var_30], r13
0x18000b33d  mov     ecx, 40h ; '@'; uFlags
0x18000b342  mov     [rsp+250h+var_38], r14
0x18000b34a  mov     [rbp+150h+var_108], r15d
0x18000b34e  mov     [rbp+150h+var_D8], rbx
0x18000b352  call    cs:__imp_LocalAlloc
0x18000b359  nop     dword ptr [rax+rax+00h]
0x18000b35e  mov     [rbp+150h+var_110], rax
0x18000b362  mov     r14, rax
0x18000b365  test    rax, rax
0x18000b368  jz      loc_18000B4D8
0x18000b36e  xorps   xmm0, xmm0
0x18000b371  mov     [rbp+150h+var_EC], r15d
0x18000b375  movups  xmmword ptr [rsp+250h+cchMax], xmm0
0x18000b37a  mov     [rbp+150h+var_F8], r15d
0x18000b37e  mov     r13, r15
0x18000b381  mov     [rsp+250h+var_1D8], r15
0x18000b386  call    cs:__imp_GetProcessHeap
0x18000b38d  nop     dword ptr [rax+rax+00h]
0x18000b392  mov     edx, 8; dwFlags
0x18000b397  mov     r8d, 0A0h; dwBytes
0x18000b39d  mov     rcx, rax; hHeap
0x18000b3a0  call    cs:__imp_HeapAlloc
0x18000b3a7  nop     dword ptr [rax+rax+00h]
0x18000b3ac  mov     dword ptr [rbp+150h+arg_8], 0D0000017h
0x18000b3b6  mov     rdi, 0C81ECB17B1B54A58h
0x18000b3c0  mov     [rbp+150h+var_138], rax
0x18000b3c4  mov     r12, rax
0x18000b3c7  mov     rsi, 7F1137FAB69605Eh
0x18000b3d1  test    rax, rax
0x18000b3d4  jz      loc_1800106C7
0x18000b3da  movups  xmm0, cs:?DecryptionCipher@?1??WarbirdUmGetDecryptionCipher@@9@4PAEA; uchar near * `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher
0x18000b3e1  movups  xmmword ptr [rax], xmm0
0x18000b3e4  movups  xmm1, cs:xmmword_1800311A0
0x18000b3eb  movups  xmmword ptr [rax+10h], xmm1
0x18000b3ef  movups  xmm0, cs:xmmword_1800311B0
0x18000b3f6  movups  xmmword ptr [rax+20h], xmm0
0x18000b3fa  movups  xmm1, cs:xmmword_1800311C0
0x18000b401  movups  xmmword ptr [rax+30h], xmm1
0x18000b405  movups  xmm0, cs:xmmword_1800311D0
0x18000b40c  movups  xmmword ptr [rax+40h], xmm0
0x18000b410  movups  xmm1, cs:xmmword_1800311E0
0x18000b417  movups  xmmword ptr [rax+50h], xmm1
0x18000b41b  movups  xmm0, cs:xmmword_1800311F0
0x18000b422  movups  xmmword ptr [rax+60h], xmm0
0x18000b426  movups  xmm1, cs:xmmword_180031200
0x18000b42d  movups  xmmword ptr [rax+70h], xmm1
0x18000b431  movups  xmm0, cs:xmmword_180031210
0x18000b438  movups  xmmword ptr [rax+80h], xmm0
0x18000b43f  movups  xmm1, cs:xmmword_180031220
0x18000b446  movups  xmmword ptr [rax+90h], xmm1
0x18000b44d  call    cs:__imp_GetProcessHeap
0x18000b454  nop     dword ptr [rax+rax+00h]
0x18000b459  mov     edx, 8; dwFlags
0x18000b45e  mov     rcx, rax; hHeap
0x18000b461  mov     r8d, edx; dwBytes
0x18000b464  call    cs:__imp_HeapAlloc
0x18000b46b  nop     dword ptr [rax+rax+00h]
0x18000b470  mov     rcx, rax; psz
0x18000b473  test    rax, rax
0x18000b476  jz      loc_1800106D5
0x18000b47c  mov     rax, cs:?nDecryptionKey@?1??WarbirdUmGetDecryptionKey@@9@4_KA; unsigned __int64 `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey
0x18000b483  mov     r13, rcx
0x18000b486  mov     [rcx], rax
0x18000b489  mov     [rbp+150h+var_118], rcx
0x18000b48d  rdtsc
0x18000b48f  shl     rdx, 20h; cchMax
0x18000b493  or      rax, rdx
0x18000b496  mov     [rbp+150h+var_160], rax
0x18000b49a  lea     r8, [rbp+150h+pcchLength]; pcchLength
0x18000b49e  mov     [rbp+150h+pcchLength], r15
0x18000b4a2  call    StringLengthWorkerW
0x18000b4a7  test    eax, eax
0x18000b4a9  js      loc_1800106E0
0x18000b4af  mov     rax, [rbp+150h+pcchLength]
0x18000b4b3  inc     rax
0x18000b4b6  mov     [rbp+150h+pcchLength], rax
0x18000b4ba  lea     eax, ds:4[rax*2]
0x18000b4c1  cmp     eax, 4
0x18000b4c4  jnb     short loc_18000B510
0x18000b4c6  mov     r15d, 0C0000095h
0x18000b4cc  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b4d3  jmp     loc_18000B862
0x18000b4d8  mov     eax, r15d
0x18000b4db  mov     r15d, 8007000Eh
0x18000b4e1  jmp     short loc_18000B4F3
0x18000b4e3  cmp     [rbp+150h+var_EC], 0
0x18000b4e7  jnz     loc_18000D9BD
0x18000b4ed  mov     eax, [rbp+150h+var_F8]
0x18000b4f0  mov     rbx, r14
0x18000b4f3  test    r15d, r15d
0x18000b4f6  js      loc_18000B8FB
0x18000b4fc  cmp     eax, 4
0x18000b4ff  jz      loc_180010115
0x18000b505  mov     r15d, 0C004F01Eh
0x18000b50b  jmp     loc_18000D7F3
0x18000b510  add     eax, 0C4h
0x18000b515  cmp     eax, 0C4h
0x18000b51a  jnb     short loc_18000B52E
0x18000b51c  mov     r15d, 0D0000095h
0x18000b522  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b529  jmp     loc_18000B862
0x18000b52e  lea     ecx, [rax+8]
0x18000b531  cmp     ecx, eax
0x18000b533  jb      short loc_18000B51C
0x18000b535  lea     eax, [rcx+8]
0x18000b538  cmp     eax, ecx
0x18000b53a  jb      short loc_18000B51C
0x18000b53c  mov     dword ptr [rsp+250h+cchMax+4], eax
0x18000b540  mov     r15d, eax
0x18000b543  call    cs:__imp_GetProcessHeap
0x18000b54a  nop     dword ptr [rax+rax+00h]
0x18000b54f  mov     r8d, r15d; dwBytes
0x18000b552  mov     edx, 8; dwFlags
0x18000b557  mov     rcx, rax; hHeap
0x18000b55a  call    cs:__imp_HeapAlloc
0x18000b561  nop     dword ptr [rax+rax+00h]
0x18000b566  mov     rdx, rax
0x18000b569  test    rax, rax
0x18000b56c  jz      loc_1800106EF
0x18000b572  xor     r9d, r9d
0x18000b575  mov     dword ptr [rbp+150h+lpMem], ebx
0x18000b57b  mov     [rsp+250h+cchMax+8], rax
0x18000b580  mov     dword ptr [rsp+250h+cchMax], r9d
0x18000b585  test    rax, rax
0x18000b588  jz      loc_18000E9EF
0x18000b58e  xor     r8d, r8d
0x18000b591  cmp     r8d, r9d
0x18000b594  jnb     short loc_18000B5B6
0x18000b596  mov     eax, [rdx]
0x18000b598  add     eax, 4
0x18000b59b  cmp     eax, 4
0x18000b59e  jnb     loc_18000C54E
0x18000b5a4  mov     r15d, 0C0000095h
0x18000b5aa  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b5b1  jmp     loc_18000B859
0x18000b5b6  lea     r8, [rdx+4]
0x18000b5ba  cmp     r8, rdx
0x18000b5bd  jb      short loc_18000B5A4
0x18000b5bf  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b5c3  lea     rax, [rdx+8]
0x18000b5c7  add     rcx, [rsp+250h+cchMax+8]
0x18000b5cc  cmp     rax, rcx
0x18000b5cf  ja      loc_1800106FA
0x18000b5d5  mov     dword ptr [rdx], 4
0x18000b5db  mov     [r8], ebx
0x18000b5de  mov     r8d, dword ptr [rsp+250h+cchMax]
0x18000b5e3  mov     rdx, [rsp+250h+cchMax+8]
0x18000b5e8  inc     r8d
0x18000b5eb  mov     dword ptr [rsp+250h+cchMax], r8d
0x18000b5f0  test    rdx, rdx
0x18000b5f3  jz      loc_18000EA43
0x18000b5f9  cmp     r9d, r8d
0x18000b5fc  jnb     short loc_18000B61A
0x18000b5fe  mov     eax, [rdx]
0x18000b600  add     eax, 4
0x18000b603  cmp     eax, 4
0x18000b606  jb      short loc_18000B5A4
0x18000b608  mov     ecx, eax
0x18000b60a  add     rcx, rdx
0x18000b60d  cmp     rcx, rdx
0x18000b610  jb      short loc_18000B5A4
0x18000b612  mov     rdx, rcx
0x18000b615  inc     r9d
0x18000b618  jmp     short loc_18000B5F9
0x18000b61a  lea     r8, [rdx+4]
0x18000b61e  cmp     r8, rdx
0x18000b621  jb      short loc_18000B5A4
0x18000b623  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b627  lea     rax, [rdx+0A4h]
0x18000b62e  add     rcx, [rsp+250h+cchMax+8]
0x18000b633  cmp     rax, rcx
0x18000b636  ja      loc_180010705
0x18000b63c  mov     dword ptr [rdx], 0A0h
0x18000b642  movups  xmm0, xmmword ptr [r12]
0x18000b647  movups  xmmword ptr [r8], xmm0
0x18000b64b  movups  xmm1, xmmword ptr [r12+10h]
0x18000b651  movups  xmmword ptr [r8+10h], xmm1
0x18000b656  movups  xmm0, xmmword ptr [r12+20h]
0x18000b65c  movups  xmmword ptr [r8+20h], xmm0
0x18000b661  movups  xmm1, xmmword ptr [r12+30h]
0x18000b667  movups  xmmword ptr [r8+30h], xmm1
0x18000b66c  movups  xmm0, xmmword ptr [r12+40h]
0x18000b672  movups  xmmword ptr [r8+40h], xmm0
0x18000b677  movups  xmm1, xmmword ptr [r12+50h]
0x18000b67d  movups  xmmword ptr [r8+50h], xmm1
0x18000b682  movups  xmm0, xmmword ptr [r12+60h]
0x18000b688  movups  xmmword ptr [r8+60h], xmm0
0x18000b68d  movups  xmm1, xmmword ptr [r12+70h]
0x18000b693  movups  xmmword ptr [r8+70h], xmm1
0x18000b698  movups  xmm0, xmmword ptr [r12+80h]
0x18000b6a1  movups  xmmword ptr [r8+80h], xmm0
0x18000b6a9  movups  xmm1, xmmword ptr [r12+90h]
0x18000b6b2  movups  xmmword ptr [r8+90h], xmm1
0x18000b6ba  mov     r8d, dword ptr [rsp+250h+cchMax]
0x18000b6bf  mov     rdx, [rsp+250h+cchMax+8]
0x18000b6c4  inc     r8d
0x18000b6c7  mov     dword ptr [rsp+250h+cchMax], r8d
0x18000b6cc  test    rdx, rdx
0x18000b6cf  jz      loc_18000EA9A
0x18000b6d5  xor     r9d, r9d
0x18000b6d8  cmp     r9d, r8d
0x18000b6db  jnb     short loc_18000B701
0x18000b6dd  mov     eax, [rdx]
0x18000b6df  add     eax, 4
0x18000b6e2  cmp     eax, 4
0x18000b6e5  jb      loc_18000B5A4
0x18000b6eb  mov     ecx, eax
0x18000b6ed  add     rcx, rdx
0x18000b6f0  cmp     rcx, rdx
0x18000b6f3  jb      loc_18000B5A4
0x18000b6f9  mov     rdx, rcx
0x18000b6fc  inc     r9d
0x18000b6ff  jmp     short loc_18000B6D8
0x18000b701  lea     r8, [rdx+4]
0x18000b705  cmp     r8, rdx
0x18000b708  jb      loc_18000B5A4
0x18000b70e  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b712  lea     rax, [rdx+0Ch]
0x18000b716  add     rcx, [rsp+250h+cchMax+8]
0x18000b71b  cmp     rax, rcx
0x18000b71e  ja      loc_180010710
0x18000b724  mov     dword ptr [rdx], 8
0x18000b72a  movsd   xmm0, qword ptr [r13+0]
0x18000b730  movsd   qword ptr [r8], xmm0
0x18000b735  mov     r8d, dword ptr [rsp+250h+cchMax]
0x18000b73a  mov     rdx, [rsp+250h+cchMax+8]; cchMax
0x18000b73f  inc     r8d
0x18000b742  mov     dword ptr [rsp+250h+cchMax], r8d
0x18000b747  test    rdx, rdx
0x18000b74a  jz      loc_18000EAF1
0x18000b750  xor     r9d, r9d
0x18000b753  cmp     r9d, r8d
0x18000b756  jnb     short loc_18000B77C
0x18000b758  mov     eax, [rdx]
0x18000b75a  add     eax, 4
0x18000b75d  cmp     eax, 4
0x18000b760  jb      loc_18000B5A4
0x18000b766  mov     ecx, eax
0x18000b768  add     rcx, rdx
0x18000b76b  cmp     rcx, rdx
0x18000b76e  jb      loc_18000B5A4
0x18000b774  mov     rdx, rcx
0x18000b777  inc     r9d
0x18000b77a  jmp     short loc_18000B753
  ... truncated ...
```
