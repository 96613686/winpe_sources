# RasInitialize

- ea: `0x18000b010`
- end: `0x180010cac`
- name: `RasInitialize`
- size: `23708`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180011200`
- `0x180013700`

## callees

- `0x180001760`
- `0x180001c70`
- `0x180001fd0`
- `0x1800021c0`
- `0x18000b010`
- `0x180010e00`
- `0x180013bf0`
- `0x180013c80`
- `0x180013cb0`
- `0x180013d10`
- `0x180014990`
- `0x180014ab0`
- `0x180020fd8`
- `0x180021000`
- `0x180023810`
- `0x1800263b6`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cfc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cfc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfe4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cf45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cf45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c6d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000f251`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c6d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000f251`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c8b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f26d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c8b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f26d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b12c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b12c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f46e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f46e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b63c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b663`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b815`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b84b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b880`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b912`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b97d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c31e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c445`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d72f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d799`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d7b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d7ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d7e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d856`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d86e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d88b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d8fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d91b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f03e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f719`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f777`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fafa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fbf7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fda9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000feaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fee6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010570`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b63c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b663`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b815`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b84b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b880`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b912`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b97d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c31e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c445`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d72f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d799`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d7b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d7ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d7e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d812`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d856`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d86e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d88b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d8fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d91b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f03e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f6e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f719`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f777`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fafa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fbf7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fd7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fda9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fdef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000feaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fee6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b15a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b62a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b78e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b86e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b936`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b96b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bfc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c066`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c30c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c333`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c355`

## string_xrefs

- `0x18000c6cc`: `ntdll.dll`
- `0x18000f225`: `ntdll.dll`
- `0x18000d4e3`: `SSTP service initialization failed, error = %d`
- `0x18000d48e`: `RASMAN service initialization failed, error = %d`
- `0x180010ad2`: `Rasman service was started by RasInitialize`
- `0x180010b1e`: `TapiSrv service initialization failed, error = %d`

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
  __m128 v70; // xmm2
  __m128 v71; // xmm1
  __m128 v72; // xmm0
  __m128 v73; // xmm1
  __m128 v74; // xmm1
  __m128 v75; // xmm1
  __m128 v76; // xmm1
  int v77; // edx
  char *v78; // r13
  unsigned __int8 *v79; // rdi
  SIZE_T v80; // rbx
  int v81; // r9d
  int v82; // r8d
  int v83; // r14d
  int v84; // r12d
  int v85; // eax
  int v86; // r11d
  int v87; // r10d
  int v88; // r11d
  int v89; // r10d
  int v90; // ecx
  int v91; // r8d
  int v92; // r9d
  int v93; // edx
  int v94; // r8d
  unsigned int v95; // ecx
  int v96; // edx
  int v97; // eax
  int v98; // ecx
  int v99; // edx
  int v100; // r8d
  int v101; // ecx
  unsigned int v102; // edx
  unsigned int v103; // r8d
  int v104; // ecx
  int v105; // edx
  int v106; // r8d
  int v107; // ecx
  int v108; // edx
  int v109; // r9d
  int v110; // ecx
  int v111; // r8d
  unsigned int v112; // edx
  int v113; // r9d
  int v114; // ecx
  int v115; // r8d
  HANDLE v116; // rax
  _DWORD *v117; // rax
  HANDLE v118; // rax
  void *v119; // rcx
  SIZE_T *v120; // rdx
  void *v121; // rax
  SIZE_T v122; // r15
  HANDLE v123; // rax
  _OWORD *v124; // rax
  HANDLE v125; // rax
  _QWORD *v126; // rax
  int v127; // r15d
  unsigned int *v128; // rax
  SIZE_T *v129; // r9
  HANDLE v130; // rax
  SIZE_T v131; // rax
  HANDLE v132; // rax
  HANDLE v133; // rax
  HANDLE v134; // rax
  HANDLE v135; // rax
  _QWORD *v136; // rax
  _DWORD *v137; // rcx
  unsigned int v138; // edx
  unsigned int v139; // r8d
  unsigned int v140; // edx
  unsigned int v141; // eax
  unsigned int v142; // r15d
  HANDLE v143; // rax
  _DWORD *v144; // rax
  HANDLE v145; // rax
  _DWORD *v146; // rcx
  SIZE_T v147; // rdx
  _DWORD *v148; // rcx
  unsigned int *v149; // rdx
  _DWORD *v150; // rax
  int v151; // r9d
  __int64 v152; // r11
  unsigned int *v153; // r8
  unsigned int *v154; // rdx
  unsigned int *v155; // r8
  _DWORD *v156; // r10
  __int64 v157; // rax
  LPVOID v158; // r9
  unsigned int v159; // r11d
  unsigned int v160; // ecx
  unsigned int v161; // eax
  unsigned int v162; // r15d
  HANDLE v163; // rax
  void *v164; // rax
  signed int LastError; // eax
  unsigned int v166; // r8d
  unsigned int *v167; // rcx
  size_t v168; // r9
  size_t v169; // r11
  unsigned int *v170; // r10
  unsigned int v171; // r9d
  SIZE_T v172; // r15
  unsigned int *v173; // r11
  unsigned int v174; // r10d
  unsigned __int64 v175; // r9
  unsigned int v176; // r11d
  unsigned int v177; // r9d
  unsigned int v178; // r10d
  int v179; // ecx
  SIZE_T v180; // r15
  FARPROC ProcAddress; // rax
  int v182; // eax
  HANDLE v183; // rax
  _QWORD *v184; // rax
  SIZE_T v185; // rcx
  HANDLE v186; // rax
  void *v187; // rcx
  SIZE_T v188; // rax
  size_t v189; // r8
  const void *v190; // rdx
  int v191; // r15d
  HANDLE v192; // rax
  void *v193; // rcx
  SIZE_T v194; // r8
  void *v195; // rdx
  unsigned __int64 v196; // rax
  HANDLE v197; // rax
  void *v198; // rcx
  LPVOID v199; // r8
  void *v200; // rdx
  SIZE_T *v201; // rax
  __int64 v202; // rcx
  SIZE_T v203; // r15
  void *v204; // rax
  unsigned int *v205; // rcx
  unsigned __int8 *v206; // rdx
  unsigned __int8 *v207; // r9
  _BYTE *v208; // r11
  unsigned int v209; // r10d
  unsigned int v210; // r9d
  unsigned int v211; // r8d
  int v212; // esi
  LPVOID v213; // r14
  int v214; // ebx
  int v215; // r10d
  int v216; // r15d
  int v217; // r11d
  unsigned int v218; // edx
  int v219; // r8d
  unsigned int v220; // ecx
  int v221; // edx
  int v222; // r8d
  unsigned int v223; // ecx
  int v224; // edx
  int v225; // r9d
  int v226; // r10d
  unsigned int v227; // r8d
  int v228; // ecx
  int v229; // edx
  unsigned int v230; // r8d
  unsigned int v231; // ecx
  int v232; // edx
  int v233; // r8d
  int v234; // ecx
  int v235; // edx
  int v236; // r8d
  int v237; // r9d
  int v238; // ecx
  unsigned int v239; // edx
  int v240; // r9d
  _BYTE *v241; // rcx
  int v242; // eax
  int v243; // r8d
  unsigned __int8 v244; // r8
  HANDLE v245; // rax
  unsigned __int64 v246; // rax
  __m128 v247; // xmm1
  __m128 v248; // xmm2
  __m128 v249; // xmm0
  __m128 v250; // xmm0
  __m128 v251; // xmm1
  __m128 v252; // xmm1
  __m128 v253; // xmm1
  __m128 v254; // xmm1
  DWORD CurrentProcessId; // eax
  unsigned int v256; // ebx
  unsigned int v257; // eax
  int v258; // r15d
  _DWORD *v259; // r9
  void *v260; // r8
  int v261; // r11d
  int v262; // r15d
  _DWORD *v263; // r8
  unsigned int *v264; // r8
  unsigned __int64 v265; // r10
  void *v266; // r10
  unsigned int *v267; // rcx
  void *v268; // rdx
  HANDLE v269; // rax
  _DWORD *v270; // rax
  unsigned int jj; // r8d
  _DWORD *v272; // rdx
  int *v273; // r9
  int v274; // r15d
  unsigned int *v275; // rax
  unsigned int kk; // r8d
  size_t v277; // r9
  unsigned int *v278; // rdx
  SIZE_T v279; // r10
  unsigned int v280; // r8d
  unsigned int *v281; // rax
  __int64 v282; // r10
  unsigned int *v283; // rdx
  unsigned int *v284; // r8
  unsigned int v285; // r11d
  unsigned int *v286; // rax
  unsigned int mm; // r10d
  __int64 v288; // r8
  unsigned int *v289; // rdx
  int v290; // edi
  SC_HANDLE v291; // rdi
  DWORD v292; // eax
  DWORD v293; // eax
  PVOID *v294; // rcx
  __int64 v295; // rdx
  unsigned int *v296; // rcx
  SIZE_T v297; // rcx
  unsigned __int8 *v298; // rbx
  _QWORD *v299; // r12
  HANDLE v300; // rax
  unsigned __int8 *v301; // rax
  unsigned __int8 *v302; // r13
  HANDLE v303; // rax
  void *v304; // rsi
  int v305; // ebx
  void *v306; // rsi
  int v307; // ebx
  int v308; // eax
  void *v309; // rbx
  HANDLE v310; // rax
  void *v311; // rdi
  HANDLE v312; // rax
  void *v313; // rdi
  HANDLE v314; // rax
  void *v315; // rdi
  HANDLE v316; // rax
  HANDLE v317; // rax
  HANDLE v318; // rax
  void *v319; // rbx
  HANDLE v320; // rax
  _QWORD *v321; // rdi
  void *v322; // rbx
  HANDLE v323; // rax
  void *v324; // rbx
  HANDLE v325; // rax
  void *v326; // rbx
  HANDLE v327; // rax
  HANDLE v328; // rax
  void *v329; // rbx
  HANDLE v330; // rax
  unsigned int v331; // r9d
  void *v332; // rdi
  HANDLE v333; // rax
  HANDLE v334; // rax
  HANDLE v335; // rax
  HANDLE v336; // rax
  int v337; // ebx
  int v338; // r9d
  int v339; // r10d
  int v340; // r11d
  SIZE_T *v341; // rax
  __int64 v342; // rax
  unsigned __int64 v343; // rbx
  void *v344; // rax
  unsigned int v345; // r11d
  _BYTE *v346; // rcx
  unsigned __int8 *v347; // rdx
  _BYTE *v348; // r9
  unsigned int v349; // r10d
  unsigned int v350; // r8d
  SIZE_T v351; // rsi
  int v352; // r12d
  SIZE_T v353; // r14
  int v354; // r13d
  int v355; // r10d
  int v356; // r9d
  int v357; // ebx
  int v358; // r11d
  int v359; // edx
  int v360; // r8d
  unsigned int v361; // ecx
  int v362; // edx
  int v363; // r8d
  unsigned int v364; // ecx
  int v365; // edx
  int v366; // r9d
  int v367; // r10d
  unsigned int v368; // r8d
  int v369; // ecx
  int v370; // edx
  unsigned int v371; // r8d
  unsigned int v372; // ecx
  int v373; // edx
  unsigned int v374; // r8d
  int v375; // ecx
  unsigned int v376; // edx
  int v377; // r8d
  int v378; // r9d
  int v379; // ecx
  unsigned int v380; // edx
  int v381; // eax
  int v382; // ecx
  unsigned int v383; // ecx
  _BYTE *v384; // r12
  _QWORD *v385; // r13
  unsigned __int64 v386; // rax
  __m128 v387; // xmm1
  __m128 v388; // xmm2
  __m128 v389; // xmm0
  __m128 v390; // xmm0
  __m128 v391; // xmm1
  __m128 v392; // xmm1
  __m128 v393; // xmm1
  __m128 v394; // xmm1
  HANDLE v395; // rax
  void *v396; // rcx
  HANDLE v397; // rax
  unsigned int v398; // r9d
  int v399; // eax
  int v400; // r9d
  SIZE_T v401; // r8
  int v402; // edx
  unsigned __int64 v403; // rax
  unsigned __int64 v404; // rcx
  __m128 v405; // xmm1
  __m128 v406; // xmm2
  __m128 v407; // xmm0
  __m128 v408; // xmm0
  __m128 v409; // xmm1
  __m128 v410; // xmm1
  __m128 v411; // xmm1
  __m128 v412; // xmm1
  int v413; // r11d
  unsigned int v414; // edx
  LPVOID v415; // rdi
  int v416; // r8d
  unsigned __int8 *v417; // r14
  SIZE_T v418; // r15
  int v419; // ebx
  int v420; // r13d
  int v421; // r12d
  int v422; // eax
  int v423; // r11d
  int v424; // r10d
  int v425; // r11d
  int v426; // r10d
  int v427; // edx
  int v428; // r9d
  int v429; // edx
  int v430; // r9d
  int v431; // r8d
  int v432; // edx
  unsigned int v433; // ecx
  int v434; // r8d
  int v435; // eax
  int v436; // ecx
  int v437; // edx
  unsigned int v438; // r8d
  int v439; // ecx
  unsigned int v440; // edx
  unsigned int v441; // r8d
  int v442; // ecx
  int v443; // edx
  int v444; // r8d
  int v445; // ecx
  int v446; // edx
  int v447; // r8d
  int v448; // ecx
  int v449; // edx
  unsigned int v450; // r8d
  unsigned int v451; // eax
  int v452; // ecx
  int v453; // r8d
  int v454; // ecx
  HANDLE v455; // rax
  LPVOID v456; // rsi
  HANDLE v457; // rax
  void *v458; // rax
  size_t v459; // r8
  const void *v460; // rdx
  HANDLE v461; // rax
  _OWORD *v462; // rax
  HANDLE v463; // rax
  _QWORD *v464; // rax
  unsigned int v465; // ebx
  HANDLE v466; // rax
  LPVOID v467; // rax
  _DWORD *v468; // r9
  _DWORD *v469; // rax
  unsigned int *v470; // r9
  unsigned int v471; // r10d
  unsigned int v472; // r11d
  __int64 v473; // rdx
  __int64 v474; // r9
  int v475; // r11d
  _DWORD *v476; // r9
  _OWORD *v477; // rax
  unsigned int *v478; // r9
  unsigned int v479; // r10d
  unsigned int v480; // r11d
  __int64 v481; // rdx
  __int64 v482; // r9
  int v483; // r11d
  _DWORD *v484; // r9
  _QWORD *v485; // rax
  unsigned int *v486; // r9
  unsigned int v487; // r10d
  unsigned int v488; // r11d
  __int64 v489; // rdx
  __int64 v490; // r9
  int v491; // r11d
  _DWORD *v492; // r9
  size_t *v493; // rax
  size_t v494; // rcx
  __int64 v495; // rcx
  unsigned int v496; // r9d
  unsigned int v497; // edx
  unsigned int v498; // ebx
  HANDLE v499; // rax
  char *v500; // rax
  char *v501; // rbx
  void *v502; // rax
  HANDLE v503; // rax
  HANDLE v504; // rax
  HANDLE v505; // rax
  HANDLE v506; // rax
  HANDLE v507; // rax
  __int64 v508; // rdx
  unsigned int v509; // ecx
  unsigned int v510; // ebx
  HANDLE v511; // rax
  _DWORD *v512; // rax
  SIZE_T v513; // rcx
  SIZE_T v514; // rcx
  HANDLE v515; // rax
  __int64 v516; // rcx
  unsigned int *v517; // rcx
  int nn; // r10d
  unsigned int v519; // ebx
  SIZE_T v520; // rcx
  unsigned int i1; // r10d
  int v522; // r9d
  unsigned int v523; // ecx
  unsigned int v524; // r10d
  unsigned int v525; // ebx
  HANDLE v526; // rax
  _DWORD *v527; // rax
  _DWORD *v528; // rbx
  FARPROC v529; // rax
  int v530; // eax
  unsigned int v531; // r9d
  SIZE_T *v532; // rcx
  int v533; // r9d
  SIZE_T v534; // r11
  unsigned int v535; // r10d
  unsigned int v536; // r11d
  int v537; // r9d
  int v538; // r9d
  SIZE_T v539; // r10
  unsigned int v540; // r10d
  int v541; // r9d
  int v542; // r9d
  unsigned int v543; // r10d
  bool v544; // sf
  unsigned int v545; // r11d
  int v546; // r10d
  unsigned int v547; // r11d
  int v548; // r10d
  HANDLE v549; // rax
  HANDLE v550; // rax
  void *v551; // rcx
  _QWORD *v552; // rax
  SIZE_T v553; // r8
  const void *v554; // rdx
  HANDLE v555; // rax
  void *v556; // rcx
  SIZE_T v557; // r8
  const void *v558; // rdx
  HANDLE v559; // rax
  void *v560; // rcx
  LPVOID v561; // r8
  const void *v562; // rdx
  HANDLE v563; // rax
  HANDLE v564; // rax
  HANDLE v565; // rax
  HANDLE v566; // rax
  int v567; // ecx
  unsigned int v568; // r9d
  unsigned int v569; // r11d
  _DWORD *v570; // r10
  __int64 v571; // r11
  const void *v572; // rdi
  void *v573; // rbx
  int v574; // esi
  SIZE_T v575; // r9
  int v576; // r10d
  LPVOID v577; // r10
  unsigned int *v578; // r9
  SIZE_T v579; // r10
  __int64 v580; // rdx
  __int64 v581; // r9
  HANDLE v582; // rax
  int v583; // eax
  int *v584; // rcx
  SIZE_T v585; // rcx
  int v586; // r9d
  unsigned int v587; // r10d
  int v588; // r9d
  int *v589; // rax
  HANDLE v590; // rax
  HANDLE v591; // rax
  HANDLE v592; // rax
  HANDLE v593; // rax
  SIZE_T v594; // rcx
  HANDLE v595; // rax
  HANDLE v596; // rax
  HANDLE v597; // rax
  HANDLE v598; // rax
  HANDLE v599; // rax
  HANDLE v600; // rax
  HANDLE v601; // rax
  HANDLE v602; // rax
  SIZE_T v603; // rcx
  HANDLE v604; // rax
  HANDLE v605; // rax
  HANDLE v606; // rax
  HANDLE v607; // rax
  int v608; // eax
  SIZE_T *v609; // rcx
  int v610; // esi
  int v611; // edi
  unsigned int v612; // ebx
  int v613; // ecx
  int v614; // eax
  int v615; // edx
  int v616; // ecx
  char v617; // r14
  HANDLE v618; // rax
  HANDLE v619; // rax
  unsigned int v620; // ecx
  unsigned __int8 *v621; // rdi
  int v622; // r14d
  int v623; // r15d
  int v624; // r10d
  char v625; // bl
  unsigned int v626; // r10d
  int v627; // ecx
  int v628; // r13d
  _BYTE *v629; // rsi
  unsigned int v630; // r10d
  int v631; // ecx
  unsigned int v632; // edx
  char v633; // r9
  unsigned int v634; // ecx
  int v635; // r8d
  int v636; // r11d
  int v637; // eax
  char v638; // r14
  int v639; // eax
  int v640; // ecx
  unsigned int v641; // r8d
  int v642; // r11d
  char v643; // si
  DWORD v644; // eax
  void *v645; // [rsp+30h] [rbp-D0h]
  LPVOID v646; // [rsp+30h] [rbp-D0h]
  LPVOID v647; // [rsp+30h] [rbp-D0h]
  _DWORD *v648; // [rsp+38h] [rbp-C8h]
  unsigned int v649; // [rsp+38h] [rbp-C8h]
  unsigned int v650; // [rsp+38h] [rbp-C8h]
  SIZE_T dwBytes; // [rsp+40h] [rbp-C0h]
  _DWORD *dwBytesa; // [rsp+40h] [rbp-C0h]
  unsigned int *v653; // [rsp+48h] [rbp-B8h]
  size_t cchMax[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v655; // [rsp+60h] [rbp-A0h]
  LPVOID v656; // [rsp+68h] [rbp-98h]
  LPVOID v657; // [rsp+70h] [rbp-90h]
  LPVOID v658; // [rsp+78h] [rbp-88h] BYREF
  void *v659; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v660; // [rsp+88h] [rbp-78h]
  unsigned int v661; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h]
  unsigned int v663; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v664; // [rsp+A8h] [rbp-58h]
  size_t v665[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v666; // [rsp+C0h] [rbp-40h]
  int v667; // [rsp+C8h] [rbp-38h]
  SIZE_T v668; // [rsp+D0h] [rbp-30h]
  LPVOID v669; // [rsp+D8h] [rbp-28h]
  _DWORD *v670; // [rsp+E0h] [rbp-20h] BYREF
  SIZE_T v671; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v672; // [rsp+F0h] [rbp-10h]
  size_t Size; // [rsp+F8h] [rbp-8h]
  SIZE_T v674; // [rsp+100h] [rbp+0h]
  LPVOID v675; // [rsp+108h] [rbp+8h]
  unsigned int v676; // [rsp+110h] [rbp+10h] BYREF
  _OWORD *v677; // [rsp+118h] [rbp+18h]
  void *v678; // [rsp+120h] [rbp+20h]
  SIZE_T v679; // [rsp+128h] [rbp+28h]
  int v680; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v681; // [rsp+138h] [rbp+38h]
  void *v682; // [rsp+140h] [rbp+40h]
  int v683; // [rsp+148h] [rbp+48h]
  size_t v684; // [rsp+150h] [rbp+50h] BYREF
  int v685; // [rsp+158h] [rbp+58h]
  unsigned int v686; // [rsp+15Ch] [rbp+5Ch] BYREF
  unsigned int v687; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v688; // [rsp+164h] [rbp+64h]
  size_t pcchLength; // [rsp+168h] [rbp+68h] BYREF
  LPVOID v690; // [rsp+170h] [rbp+70h]
  int *v691; // [rsp+178h] [rbp+78h]
  HMODULE phModule; // [rsp+180h] [rbp+80h] BYREF
  HMODULE hModule; // [rsp+188h] [rbp+88h] BYREF
  SC_HANDLE hSCObject; // [rsp+190h] [rbp+90h]
  RPC_BINDING_HANDLE Binding; // [rsp+198h] [rbp+98h] BYREF
  __int128 v696; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v697; // [rsp+1B0h] [rbp+B0h]
  __int128 v698; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v699; // [rsp+1D0h] [rbp+D0h]
  SIZE_T v700; // [rsp+260h] [rbp+160h] BYREF
  SIZE_T v701; // [rsp+268h] [rbp+168h] BYREF
  LPVOID lpMem; // [rsp+270h] [rbp+170h] BYREF
  SIZE_T v703; // [rsp+278h] [rbp+178h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v680 = 0;
  Binding = 0;
  LODWORD(v700) = 0;
  GetProcessLowBoxStatus(&v700);
  if ( !(_DWORD)v700 )
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
    v683 = 0;
    v691 = 0;
    v682 = LocalAlloc(0x40u, 4u);
    v5 = v682;
    if ( !v682 )
    {
      v14 = 0;
      v13 = -2147024882;
      goto LABEL_25;
    }
    v688 = 0;
    *(_OWORD *)cchMax = 0;
    v685 = 0;
    v6 = 0;
    v658 = 0;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
    LODWORD(v701) = -805306345;
    v677 = v8;
    v9 = v8;
    if ( !v8 )
    {
      v9 = 0;
      v13 = -1073741801;
      goto LABEL_21;
    }
    *v8 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
    v8[1] = xmmword_1800301A0;
    v8[2] = xmmword_1800301B0;
    v8[3] = xmmword_1800301C0;
    v8[4] = xmmword_1800301D0;
    v8[5] = xmmword_1800301E0;
    v8[6] = xmmword_1800301F0;
    v8[7] = xmmword_180030200;
    v8[8] = xmmword_180030210;
    v8[9] = xmmword_180030220;
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
    v681 = v11;
    v672 = __rdtsc();
    pcchLength = 0;
    if ( StringLengthWorkerW(v12, (unsigned __int64)HIDWORD(v672) << 32, &pcchLength) < 0 )
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
        LODWORD(v703) = 0;
        LODWORD(v700) = RtlUIntAdd(4, 160, &v703);
        v13 = v700;
        if ( (v700 & 0x80000000) != 0LL )
          goto LABEL_78;
        LODWORD(v700) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v703, (char *)cchMax + 4);
        v13 = v700;
        if ( (v700 & 0x80000000) != 0LL )
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
        LODWORD(v703) = 0;
        LODWORD(v700) = RtlUIntAdd(4, 8, &v703);
        v13 = v700;
        if ( (v700 & 0x80000000) != 0LL )
          goto LABEL_78;
        LODWORD(v700) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v703, (char *)cchMax + 4);
        v13 = v700;
        if ( (v700 & 0x80000000) != 0LL )
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
        v27 = v672;
        *(_DWORD *)v23 = 8;
        *(_QWORD *)(v23 + 4) = v27;
      }
      else
      {
        LODWORD(v703) = 0;
        LODWORD(v700) = RtlUIntAdd(4, 8, &v703);
        v13 = v700;
        if ( (v700 & 0x80000000) != 0LL )
          goto LABEL_78;
        LODWORD(v700) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v703, (char *)cchMax + 4);
        v13 = v700;
        if ( (v700 & 0x80000000) != 0LL )
          goto LABEL_78;
      }
      LODWORD(cchMax[0]) = 4;
      v684 = 0;
      if ( StringLengthWorkerW(v26, v23, &v684) < 0 )
      {
        v684 = 0;
        v13 = -1073741762;
        goto LABEL_35;
      }
      if ( v684 + 1 >= v684 )
      {
        v28 = (unsigned int)(2 * ++v684);
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
              LODWORD(v700) = -1073741675;
              goto LABEL_72;
            }
            if ( (unsigned __int64)v29 + v28 + 4 <= cchMax[1] + HIDWORD(cchMax[0]) )
            {
              *v29 = v28;
              v13 = 0;
              LODWORD(v700) = 0;
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
                  LODWORD(v700) = -1073741675;
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
                LODWORD(v703) = 0;
                LODWORD(v700) = RtlUIntAdd(4, 4, &v703);
                v13 = v700;
                if ( (v700 & 0x80000000) != 0LL )
                  goto LABEL_78;
                LODWORD(v700) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v703, (char *)cchMax + 4);
                v13 = v700;
                if ( (v700 & 0x80000000) != 0LL )
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
                  v700 = __rdtsc();
                  if ( HIDWORD(cchMax[0]) < 0xFFFFFFF8 )
                  {
                    v42 = (void *)((HIDWORD(cchMax[0]) + 15) & 0xFFFFFFF8);
                    v659 = v42;
                    if ( (unsigned int)v42 >= HIDWORD(cchMax[0]) + 8 )
                    {
                      v43 = (HIDWORD(cchMax[0]) + 15) & 0xFFFFFFF8;
                      lpMem = (LPVOID)(unsigned int)v42;
                      v44 = GetProcessHeap();
                      v648 = HeapAlloc(v44, 8u, v43);
                      v45 = v648;
                      if ( !v648 )
                      {
                        v13 = -805306345;
                        LODWORD(v700) = -805306345;
                        goto LABEL_79;
                      }
                      *v648 = cchMax[0];
                      v667 = 0;
                      if ( v648 + 1 < v648 || (v648[1] = HIDWORD(cchMax[0]), v648 + 2 < v648 + 1) )
                      {
                        v13 = -805306219;
                        LODWORD(v700) = -805306219;
                        v46 = GetProcessHeap();
                        v47 = v648;
                        goto LABEL_134;
                      }
                      v653 = 0;
                      v645 = 0;
                      *(_QWORD *)((char *)v648 + (_QWORD)lpMem - 8) = v700;
                      v675 = 0;
                      v655 = 0;
                      v666 = 0;
                      memcpy_0(v648 + 2, (const void *)cchMax[1], HIDWORD(cchMax[0]));
                      if ( !(_DWORD)v659
                        || (dwBytes = (unsigned int)v659 + 8LL, Src = MemoryAlloc(dwBytes), (v67 = (char *)Src) == 0) )
                      {
                        v13 = -805306367;
                        LODWORD(v700) = -805306367;
                        goto LABEL_111;
                      }
                      v68 = (unsigned int)v659;
                      LOBYTE(v66) = 0;
                      v657 = 0;
                      LODWORD(v700) = v66;
                      v664 = (unsigned __int8 *)v648;
                      if ( (_DWORD)v659 )
                      {
                        v69 = 0;
                        if ( (unsigned int)v659 < 0x20uLL )
                          goto LABEL_966;
                        v664 = (unsigned __int8 *)v648;
                        v657 = 0;
                        v70 = 0;
                        v71 = 0;
                        do
                        {
                          v70 = _mm_xor_ps(v70, (__m128)_mm_loadu_si128((const __m128i *)((char *)v648 + v69)));
                          v72 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v648 + v69 + 16));
                          v69 += 32LL;
                          v71 = _mm_xor_ps(v71, v72);
                        }
                        while ( v69 < ((unsigned int)v659 & 0xFFFFFFE0) );
                        v73 = _mm_xor_ps(v71, v70);
                        v74 = _mm_xor_ps(v73, (__m128)_mm_srli_si128((__m128i)v73, 8));
                        v75 = _mm_xor_ps(v74, (__m128)_mm_srli_si128((__m128i)v74, 4));
                        v76 = _mm_xor_ps(v75, (__m128)_mm_srli_si128((__m128i)v75, 2));
                        v66 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v76, (__m128)_mm_srli_si128((__m128i)v76, 1)));
                        LODWORD(v700) = v66;
                        if ( v69 < (unsigned int)v659 )
                        {
LABEL_966:
                          do
                            LOBYTE(v66) = *((_BYTE *)v648 + v69++) ^ v66;
                          while ( v69 < (unsigned int)v659 );
                          LODWORD(v700) = v66;
                        }
                      }
                      v660 = (unsigned __int8 *)0xC81ECB17B1B54A58LL;
                      Size = (unsigned __int64)(unsigned int)v659 >> 3;
                      if ( Size )
                      {
                        v77 = HIDWORD(v660);
                        v78 = (char *)Src;
                        v79 = v664;
                        v80 = Size;
                        v81 = 0;
                        v661 = HIWORD(HIDWORD(v660));
                        v82 = -1;
                        LODWORD(v656) = 19032;
                        v663 = WORD1(v660);
                        v668 = 0;
                        v83 = WORD2(v660);
                        v84 = HIWORD(HIDWORD(v660));
                        LODWORD(lpMem) = 0;
                        LODWORD(v703) = 0;
                        v648 = v664;
                        do
                        {
                          v85 = v79[1];
                          v86 = *v79;
                          v87 = v79[4];
                          v79 += 8;
                          v88 = *(v79 - 5) | ((*(v79 - 6) | ((v85 | (v86 << 8)) << 8)) << 8);
                          v89 = *(v79 - 1) | ((*(v79 - 2) | ((*(v79 - 3) | (v87 << 8)) << 8)) << 8);
                          v90 = v82 ^ v89;
                          v91 = v81 ^ v88 ^ v77 ^ ((v82 ^ v89) - 19032);
                          v92 = v90 ^ (__ROR4__(v91, 7) + WORD1(v660) * __ROR4__(v77 ^ v91, 15));
                          v93 = v91 ^ (v83 * __ROR4__(v92 - 1313519016, 9) - __ROR4__(v92, 10));
                          v94 = v92 ^ (__ROR4__(v93, 27) + v84 * __ROR4__(v83 ^ v93, 28));
                          v95 = v93 ^ (HIDWORD(v660) - (v94 ^ 0xB1B54A58));
                          v96 = v94 ^ (WORD1(v660) * (v95 - 19032) - (v95 >> 6));
                          v97 = v95 ^ (19032 * (v83 ^ __ROR4__(v96, 15)));
                          v98 = v96 ^ (v83 * (v84 + __ROR4__(~v97, 3)));
                          v99 = v97 ^ (v98 - HIDWORD(v660) - 19032);
                          v100 = v98 ^ (v663 * (v99 ^ v661)) ^ __ROR4__(v99, 10);
                          v101 = v99 ^ __ROR4__(v100, 3) ^ (v83 * __ROR4__(v100 ^ 0x4A58, 26));
                          v102 = v100 ^ (19032 * (__ROR4__(v101, 15) - v84));
                          v103 = v101
                               ^ (19032 * (v661 ^ v102))
                               ^ ((v102 ^ (v102 >> 14)) >> 1)
                               ^ (19032 * ((8 * (v102 - v83)) | ((v102 - v83) >> 29)));
                          v104 = v102 ^ (WORD1(v660) * (v103 - v83) - (v103 >> 13));
                          v105 = v103 ^ __ROR4__(v104, 11) ^ (v83 * __ROR4__(-1313519016 - v104, 9));
                          v106 = v104 ^ (v105 + 1313519016 - v84);
                          v107 = v105 ^ (19032 * (v106 ^ WORD1(v660)) - __ROR4__(v106, 7));
                          v108 = v106 ^ (WORD1(v660) * __ROR4__(v661 ^ v107, 28) - __ROR4__(v107, 16));
                          v109 = v107 ^ (__ROR4__(v108, 4) + v83 * __ROR4__(-1313519016 - v108, 10));
                          v78 += 8;
                          v110 = v108 ^ __ROR4__(v109, 9) ^ (v84 * __ROR4__(v109 + 1313519016, 4));
                          v111 = v109 ^ (19032 * __ROR4__(v110 ^ HIDWORD(v660), 24) - __ROR4__(v110, 30));
                          v112 = v110 ^ (WORD1(v660) * __ROR4__(HIDWORD(v660) - v111, 11) - __ROR4__(v111, 12));
                          v113 = (int)lpMem;
                          LODWORD(lpMem) = v88;
                          v114 = v111 ^ (v112 >> 8) ^ (v83 * (v112 ^ WORD1(v660)));
                          v81 = v114 ^ v113;
                          v115 = v703 ^ v112 ^ 0xB1B54A58;
                          v77 = HIDWORD(v660);
                          v82 = v114 ^ HIDWORD(v660) ^ v115;
                          *(v78 - 5) = v81;
                          *(v78 - 1) = v82;
                          *(v78 - 6) = __ROR4__(v81, 8);
                          *(v78 - 2) = __ROR4__(v82, 8);
                          *(v78 - 7) = __ROR4__(v81, 16);
                          *(v78 - 3) = __ROR4__(v82, 16);
                          *(v78 - 8) = __ROR4__(v81, 24);
                          *(v78 - 4) = __ROR4__(v82, 24);
                          LODWORD(v703) = v89;
                          ++v668;
                        }
                        while ( v668 < v80 );
                        v4 = v691;
                        v5 = v682;
                        v9 = v677;
                        v6 = v681;
                        v45 = v648;
                        v68 = (unsigned int)v659;
                        v67 = (char *)Src;
                      }
                      else
                      {
                        v657 = 0;
                      }
                      *(_QWORD *)&v67[v68] = (unsigned __int8)v700;
                      v116 = GetProcessHeap();
                      v117 = HeapAlloc(v116, 8u, 0x30u);
                      v700 = (SIZE_T)v117;
                      if ( v117 )
                      {
                        *v117 = dwBytes;
                        v118 = GetProcessHeap();
                        v119 = HeapAlloc(v118, 8u, (unsigned int)dwBytes);
                        v120 = (SIZE_T *)(v700 + 8);
                        lpMem = (LPVOID)(v700 + 8);
                        v121 = v657;
                        if ( v119 )
                        {
                          *v120 = (SIZE_T)v119;
                          v657 = v121;
                          v648 = v45;
                          memcpy_0(v119, Src, (unsigned int)dwBytes);
                          v122 = v700;
                          *(_DWORD *)(v700 + 16) = 160;
                          v123 = GetProcessHeap();
                          v124 = HeapAlloc(v123, 8u, 0xA0u);
                          if ( v124 )
                          {
                            *(_QWORD *)(v122 + 24) = v124;
                            *v124 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                            v124[1] = xmmword_1800300F0;
                            v124[2] = xmmword_180030100;
                            v124[3] = xmmword_180030110;
                            v124[4] = xmmword_180030120;
                            v124[5] = xmmword_180030130;
                            v124[6] = xmmword_180030140;
                            v124[7] = xmmword_180030150;
                            v124[8] = xmmword_180030160;
                            v124[9] = xmmword_180030170;
                            *(_DWORD *)(v122 + 32) = 8;
                            v125 = GetProcessHeap();
                            v126 = HeapAlloc(v125, 8u, 8u);
                            if ( v126 )
                            {
                              *(_QWORD *)(v122 + 40) = v126;
                              *v126 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                              v653 = (unsigned int *)v122;
                              v127 = 0;
                              v657 = 0;
                              goto LABEL_202;
                            }
                          }
                          v120 = (SIZE_T *)lpMem;
                          v121 = v657;
                        }
                        v127 = -1073741801;
                        v657 = v121;
                        v703 = *v120;
                        if ( v703 )
                        {
                          v130 = GetProcessHeap();
                          HeapFree(v130, 0, (LPVOID)v703);
                          *(_QWORD *)lpMem = 0;
                        }
                        v131 = v700;
                        lpMem = *(LPVOID *)(v700 + 24);
                        if ( lpMem )
                        {
                          v132 = GetProcessHeap();
                          HeapFree(v132, 0, lpMem);
                          v131 = v700;
                          *(_QWORD *)(v700 + 24) = 0;
                        }
                        lpMem = *(LPVOID *)(v131 + 40);
                        if ( lpMem )
                        {
                          v133 = GetProcessHeap();
                          HeapFree(v133, 0, lpMem);
                          *(_QWORD *)(v700 + 40) = 0;
                        }
                        v134 = GetProcessHeap();
                        HeapFree(v134, 0, (LPVOID)v700);
                      }
                      else
                      {
                        v127 = -1073741801;
                      }
LABEL_202:
                      v135 = GetProcessHeap();
                      HeapFree(v135, 0, Src);
                      v136 = v657;
                      if ( v657 )
                      {
                        v700 = *((_QWORD *)v657 + 1);
                        if ( v700 )
                        {
                          v590 = GetProcessHeap();
                          HeapFree(v590, 0, (LPVOID)v700);
                          v136 = v657;
                          *((_QWORD *)v657 + 1) = 0;
                        }
                        v700 = v136[3];
                        if ( v700 )
                        {
                          v591 = GetProcessHeap();
                          HeapFree(v591, 0, (LPVOID)v700);
                          v136 = v657;
                          *((_QWORD *)v657 + 3) = 0;
                        }
                        v700 = v136[5];
                        if ( v700 )
                        {
                          v592 = GetProcessHeap();
                          HeapFree(v592, 0, (LPVOID)v700);
                          *((_QWORD *)v657 + 5) = 0;
                        }
                        v593 = GetProcessHeap();
                        HeapFree(v593, 0, v657);
                        v137 = v653;
                      }
                      else
                      {
                        v137 = v653;
                      }
                      v13 = v127 | 0x10000000;
                      LODWORD(v700) = v13;
                      if ( v13 < 0 )
                        goto LABEL_215;
                      if ( *v137 >= 0xFFFFFFFC
                        || (v138 = *v137 + 8, v138 < *v137 + 4)
                        || (v139 = v138 + v137[4], v139 < v138)
                        || (v140 = v139 + 4, v139 + 4 < v139)
                        || (v141 = v140 + v137[8], LODWORD(v703) = v141, v141 < v140) )
                      {
LABEL_214:
                        v13 = -805306219;
                        LODWORD(v700) = -805306219;
LABEL_215:
                        v48 = v648;
                        goto LABEL_216;
                      }
                      v142 = v141;
                      v143 = GetProcessHeap();
                      v144 = HeapAlloc(v143, 8u, v142);
                      lpMem = v144;
                      if ( !v144 )
                      {
                        v48 = v648;
                        v13 = -805306345;
                        LODWORD(v700) = -805306345;
                        goto LABEL_110;
                      }
                      *v144 = *v653;
                      v700 = (SIZE_T)(v144 + 1);
                      if ( v144 + 1 < v144 )
                        goto LABEL_212;
                      memcpy_0(v144 + 1, *((const void **)v653 + 1), *v653);
                      v146 = (_DWORD *)(v700 + *v653);
                      if ( (unsigned __int64)v146 < v700 )
                        goto LABEL_212;
                      *v146 = v653[4];
                      v700 = (SIZE_T)(v146 + 1);
                      if ( v146 + 1 < v146
                        || (memcpy_0(v146 + 1, *((const void **)v653 + 3), v653[4]),
                            v147 = v700,
                            v148 = (_DWORD *)(v700 + v653[4]),
                            v700 = (SIZE_T)v148,
                            (unsigned __int64)v148 < v147)
                        || (*v148 = v653[8], v148 + 1 < v148)
                        || (memcpy_0(v148 + 1, *((const void **)v653 + 5), v653[8]), v700 + 4 + v653[8] < v700 + 4) )
                      {
LABEL_212:
                        v13 = -805306219;
                        LODWORD(v700) = -805306219;
                        v145 = GetProcessHeap();
                        HeapFree(v145, 0, lpMem);
                        v48 = v648;
                        v645 = 0;
                        goto LABEL_110;
                      }
                      v149 = (unsigned int *)cchMax[1];
                      v150 = v648;
                      if ( cchMax[1] )
                      {
                        if ( LODWORD(cchMax[0]) <= 1 )
                        {
                          v13 = -1073741811;
                          v645 = lpMem;
                        }
                        else
                        {
                          v151 = 0;
                          v645 = lpMem;
                          while ( 1 )
                          {
                            v152 = *v149;
                            v153 = v149 + 1;
                            if ( v151 )
                              break;
                            if ( v153 < v149 )
                              goto LABEL_108;
                            v149 = (unsigned int *)((char *)v153 + v152);
                            if ( (unsigned int *)((char *)v153 + v152) < v153 )
                              goto LABEL_108;
                            v151 = 1;
                          }
                          if ( v153 < v149 )
                            goto LABEL_108;
                          v645 = lpMem;
                          if ( LODWORD(cchMax[0]) <= 2 )
                          {
                            v13 = -1073741811;
                            goto LABEL_109;
                          }
                          v154 = (unsigned int *)cchMax[1];
                          LODWORD(v700) = 0;
                          while ( 1 )
                          {
                            v155 = v154 + 1;
                            v156 = v150;
                            Src = v150;
                            v157 = *v154;
                            v158 = lpMem;
                            v656 = lpMem;
                            if ( (unsigned int)v700 >= 2 )
                              break;
                            if ( v155 < v154 )
                              goto LABEL_108;
                            v154 = (unsigned int *)((char *)v155 + v157);
                            if ( (unsigned int *)((char *)v155 + v157) < v155 )
                              goto LABEL_108;
                            LODWORD(v700) = v700 + 1;
                            v150 = v648;
                          }
                          if ( v155 < v154
                            || (v159 = v152 + 80, v159 < 0x50)
                            || (v160 = v159 + 4, v159 + 4 < v159)
                            || (v161 = v160 + v157, LODWORD(lpMem) = v161, v161 < v160) )
                          {
LABEL_108:
                            v13 = -1073741675;
                            goto LABEL_109;
                          }
                          if ( v161 <= 0x400000 )
                          {
                            v162 = v161;
                            v163 = GetProcessHeap();
                            v164 = HeapAlloc(v163, 8u, v162);
                            Size = (size_t)v164;
                            if ( !v164 )
                            {
                              v13 = -805306345;
                              LODWORD(v700) = -805306345;
                              v645 = v656;
                              v48 = Src;
                              goto LABEL_216;
                            }
                            v675 = v164;
                            phModule = 0;
                            v698 = 0;
                            v699 = 0;
                            if ( !v656 )
                            {
                              v48 = Src;
                              v13 = -2147024809;
                              v645 = 0;
                              LODWORD(v700) = -2147024809;
                              goto LABEL_216;
                            }
                            *(_QWORD *)&v698 = v656;
                            LODWORD(v699) = v703;
                            *((_QWORD *)&v698 + 1) = v164;
                            *(_QWORD *)((char *)&v699 + 4) = (unsigned int)lpMem;
                            if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule) )
                            {
                              ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation");
                              if ( ProcAddress )
                              {
                                v182 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, _QWORD))ProcAddress)(
                                         134,
                                         &v698,
                                         32,
                                         0);
                                v13 = v182 | 0x10000000;
                                LODWORD(v700) = v182 | 0x10000000;
                                if ( v182 >= 0 )
                                {
                                  v166 = DWORD1(v699);
                                  goto LABEL_248;
                                }
                                goto LABEL_246;
                              }
                              LastError = GetLastError();
                              LODWORD(v700) = LastError;
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
                                v166 = (unsigned int)lpMem;
                                if ( v13 != -805306333 )
                                {
                                  if ( v13 < 0 )
                                    goto LABEL_812;
LABEL_248:
                                  v167 = v653;
                                  if ( v166 < 4 )
                                  {
                                    v13 = -805306306;
                                    v645 = v656;
                                    goto LABEL_267;
                                  }
                                  v648 = Src;
                                  v645 = v656;
                                  v168 = *(unsigned int *)Size;
                                  v169 = Size + 4;
                                  LODWORD(v700) = *(_DWORD *)Size;
                                  v668 = Size + 4;
                                  if ( Size + 4 < Size )
                                    goto LABEL_213;
                                  if ( v166 - 4 < (unsigned int)v168 )
                                  {
                                    v13 = -805306306;
                                    v645 = v656;
                                    goto LABEL_313;
                                  }
                                  v170 = (unsigned int *)(v168 + v169);
                                  Size = v168;
                                  if ( v168 + v169 < v169 )
                                    goto LABEL_213;
                                  v171 = v168 + 4;
                                  if ( v171 < 4 )
                                    goto LABEL_213;
                                  if ( v166 - v171 < 4 )
                                  {
                                    v13 = -805306306;
                                    v645 = v656;
                                    goto LABEL_313;
                                  }
                                  v172 = *v170;
                                  v173 = v170 + 1;
                                  LODWORD(lpMem) = *v170;
                                  v659 = v170 + 1;
                                  if ( v170 + 1 < v170 )
                                    goto LABEL_213;
                                  v174 = v171 + 4;
                                  if ( v171 + 4 < v171 )
                                    goto LABEL_213;
                                  if ( v166 - v174 < (unsigned int)v172 )
                                  {
                                    v13 = -805306306;
                                    v645 = v656;
                                    goto LABEL_313;
                                  }
                                  v175 = (unsigned __int64)v173 + v172;
                                  v674 = v172;
                                  if ( (unsigned int *)((char *)v173 + v172) < v173 )
                                    goto LABEL_213;
                                  v176 = v174 + v172;
                                  if ( v174 + (unsigned int)v172 < v174 )
                                    goto LABEL_213;
                                  if ( v166 - v176 < 4 )
                                  {
                                    v13 = -805306306;
                                    v645 = v656;
                                    goto LABEL_313;
                                  }
                                  v678 = (void *)(v175 + 4);
                                  if ( v175 + 4 < v175 || (v177 = v176 + 4, v176 + 4 < v176) )
                                  {
LABEL_213:
                                    v645 = v656;
                                    goto LABEL_214;
                                  }
                                  v178 = *(_DWORD *)((char *)v659 + v172);
                                  LODWORD(v703) = v178;
                                  if ( v166 - v177 >= v178 )
                                  {
                                    if ( v177 + v178 >= v177 )
                                    {
                                      if ( v166 != v177 + v178 )
                                      {
                                        v13 = -805306306;
                                        v645 = v656;
                                        goto LABEL_267;
                                      }
                                      v179 = v178 + v172;
                                      v180 = (unsigned int)v700;
                                      if ( (unsigned int)(v700 + v179) + 12LL != v166 )
                                      {
                                        v13 = -805306306;
                                        v645 = v656;
LABEL_267:
                                        LODWORD(v700) = v13;
LABEL_268:
                                        v48 = Src;
                                        v648 = Src;
                                        goto LABEL_110;
                                      }
                                      v183 = GetProcessHeap();
                                      v184 = HeapAlloc(v183, 8u, 0x30u);
                                      v700 = (SIZE_T)v184;
                                      v185 = (SIZE_T)v184;
                                      if ( !v184 )
                                      {
                                        v13 = -805306345;
                                        LODWORD(v700) = -805306345;
                                        goto LABEL_812;
                                      }
                                      if ( v668 )
                                      {
                                        *(_DWORD *)v184 = v180;
                                        v186 = GetProcessHeap();
                                        v187 = HeapAlloc(v186, 8u, v180);
                                        v188 = v700;
                                        if ( !v187 )
                                        {
                                          v609 = (SIZE_T *)(v700 + 8);
                                          v664 = (unsigned __int8 *)(v700 + 8);
LABEL_745:
                                          v191 = -1073741801;
                                          v594 = *v609;
                                          lpMem = 0;
                                          v703 = v594;
                                          if ( v594 )
                                          {
                                            v595 = GetProcessHeap();
                                            HeapFree(v595, 0, (LPVOID)v703);
                                            *(_QWORD *)v664 = 0;
                                            v188 = v700;
                                          }
                                          v703 = *(_QWORD *)(v188 + 24);
                                          if ( v703 )
                                          {
                                            v596 = GetProcessHeap();
                                            HeapFree(v596, 0, (LPVOID)v703);
                                            v188 = v700;
                                            *(_QWORD *)(v700 + 24) = 0;
                                          }
                                          v703 = *(_QWORD *)(v188 + 40);
                                          if ( v703 )
                                          {
                                            v597 = GetProcessHeap();
                                            HeapFree(v597, 0, (LPVOID)v703);
                                            *(_QWORD *)(v700 + 40) = 0;
                                          }
                                          v598 = GetProcessHeap();
                                          HeapFree(v598, 0, (LPVOID)v700);
                                          v201 = (SIZE_T *)lpMem;
                                          goto LABEL_283;
                                        }
                                        v189 = Size;
                                        v190 = (const void *)v668;
                                        v191 = 0;
                                        v664 = (unsigned __int8 *)(v700 + 8);
                                        *(_QWORD *)(v700 + 8) = v187;
                                        memcpy_0(v187, v190, v189);
                                        v185 = v700;
                                      }
                                      else
                                      {
                                        v191 = 0;
                                        *(_DWORD *)v184 = 0;
                                        v664 = (unsigned __int8 *)(v184 + 1);
                                        v184[1] = 0;
                                      }
                                      if ( v659 )
                                      {
                                        *(_DWORD *)(v185 + 16) = (_DWORD)lpMem;
                                        v192 = GetProcessHeap();
                                        v193 = HeapAlloc(v192, 8u, v674);
                                        v188 = v700;
                                        if ( !v193 )
                                        {
LABEL_815:
                                          v609 = (SIZE_T *)v664;
                                          goto LABEL_745;
                                        }
                                        v194 = v674;
                                        v195 = v659;
                                        *(_QWORD *)(v700 + 24) = v193;
                                        memcpy_0(v193, v195, v194);
                                        v185 = v700;
                                      }
                                      else
                                      {
                                        *(_DWORD *)(v185 + 16) = 0;
                                        *(_QWORD *)(v185 + 24) = 0;
                                      }
                                      if ( !v678 )
                                      {
                                        *(_DWORD *)(v185 + 32) = 0;
                                        *(_QWORD *)(v185 + 40) = 0;
                                        goto LABEL_282;
                                      }
                                      v196 = (unsigned int)v703;
                                      *(_DWORD *)(v185 + 32) = v703;
                                      lpMem = (LPVOID)v196;
                                      v197 = GetProcessHeap();
                                      v198 = HeapAlloc(v197, 8u, (SIZE_T)lpMem);
                                      if ( v198 )
                                      {
                                        v199 = lpMem;
                                        v200 = v678;
                                        *(_QWORD *)(v700 + 40) = v198;
                                        memcpy_0(v198, v200, (size_t)v199);
                                        v185 = v700;
LABEL_282:
                                        v201 = (SIZE_T *)v185;
                                        lpMem = (LPVOID)v185;
LABEL_283:
                                        if ( v191 >= 0 )
                                        {
                                          v655 = v201;
                                        }
                                        else
                                        {
                                          if ( v201 )
                                          {
                                            v700 = v201[1];
                                            if ( v700 )
                                            {
                                              v599 = GetProcessHeap();
                                              HeapFree(v599, 0, (LPVOID)v700);
                                              v201 = (SIZE_T *)lpMem;
                                              *((_QWORD *)lpMem + 1) = 0;
                                            }
                                            v700 = v201[3];
                                            if ( v700 )
                                            {
                                              v600 = GetProcessHeap();
                                              HeapFree(v600, 0, (LPVOID)v700);
                                              v201 = (SIZE_T *)lpMem;
                                              *((_QWORD *)lpMem + 3) = 0;
                                            }
                                            v700 = v201[5];
                                            if ( v700 )
                                            {
                                              v601 = GetProcessHeap();
                                              HeapFree(v601, 0, (LPVOID)v700);
                                              *((_QWORD *)lpMem + 5) = 0;
                                            }
                                            v602 = GetProcessHeap();
                                            HeapFree(v602, 0, lpMem);
                                          }
                                          v201 = (SIZE_T *)v655;
                                        }
                                        v13 = v191 | 0x10000000;
                                        LODWORD(v700) = v13;
                                        if ( v13 >= 0 )
                                        {
                                          if ( v201 )
                                          {
                                            v664 = (unsigned __int8 *)v201[1];
                                            if ( v664 )
                                            {
                                              v202 = *(unsigned int *)v201;
                                              if ( (_DWORD)v202 )
                                              {
                                                v203 = v202 - 8;
                                                v671 = v202 - 8;
                                                v204 = MemoryAlloc(v202 - 8);
                                                v659 = v204;
                                                v205 = (unsigned int *)v204;
                                                if ( !v204 )
                                                {
                                                  v645 = v656;
                                                  v648 = Src;
                                                  goto LABEL_301;
                                                }
                                                v206 = v664;
                                                LOBYTE(v661) = 0;
                                                v207 = v664;
                                                Size = 0x7F1137FAB69605ELL;
                                                v208 = v204;
                                                v660 = v664;
                                                v657 = v204;
                                                v209 = v203 & 7;
                                                if ( (v203 & 7) == 0 )
                                                {
                                                  v210 = 0;
                                                  LODWORD(lpMem) = v203 & 7;
                                                  v211 = 0;
                                                  LODWORD(v703) = -1;
                                                  goto LABEL_293;
                                                }
                                                v610 = 0;
                                                v611 = 0;
                                                v612 = 0;
                                                do
                                                {
                                                  v613 = *v207++;
                                                  LODWORD(v700) = v613;
                                                  LODWORD(lpMem) = 8 * v612;
                                                  if ( v612 >= 4 )
                                                  {
                                                    LODWORD(v700) = (_DWORD)v700 << (56 - (_BYTE)lpMem);
                                                    v611 |= v700;
                                                  }
                                                  else
                                                  {
                                                    LODWORD(v700) = (_DWORD)v700 << (24 - (_BYTE)lpMem);
                                                    v610 |= v700;
                                                  }
                                                  ++v612;
                                                }
                                                while ( (int)v612 < (int)v209 );
                                                v4 = v691;
                                                v614 = v610 ^ 0x92F65A5;
                                                LODWORD(v703) = v611;
                                                v615 = v611 ^ 0x699A899C;
                                                LODWORD(lpMem) = v610;
                                                v660 = v207;
                                                v211 = v610 ^ 0x92F65A5;
                                                v616 = (int)v691;
                                                do
                                                {
                                                  v700 = (SIZE_T)(v208 + 1);
                                                  if ( v616 >= 4 )
                                                  {
                                                    v615 = __ROR4__(v615, 24);
                                                    v617 = v615;
                                                  }
                                                  else
                                                  {
                                                    v614 = __ROR4__(v614, 24);
                                                    v617 = v614;
                                                  }
                                                  *v208 = v617;
                                                  ++v616;
                                                  v208 = (_BYTE *)v700;
                                                }
                                                while ( v616 < (int)v209 );
                                                v657 = (LPVOID)v700;
                                                v5 = v682;
                                                if ( v209 <= 4 )
                                                {
                                                  v210 = 0;
                                                  if ( v209 < 4 )
                                                  {
                                                    v206 = v664;
                                                    v211 = v211 >> (8 * (4 - v209)) << (8 * (4 - v209));
                                                    goto LABEL_834;
                                                  }
                                                }
                                                else
                                                {
                                                  v210 = (v611 ^ 0x699A899Cu) >> (8 * (8 - v209)) << (8 * (8 - v209));
                                                }
                                                v206 = v664;
LABEL_834:
                                                v205 = (unsigned int *)v659;
LABEL_293:
                                                v690 = (LPVOID)(v203 >> 3);
                                                if ( v203 >> 3 )
                                                {
                                                  v212 = HIDWORD(Size);
                                                  v213 = v690;
                                                  LODWORD(v700) = 24670;
                                                  v214 = HIWORD(HIDWORD(Size));
                                                  v215 = WORD2(Size);
                                                  v663 = HIDWORD(Size) ^ 0xAB69605E;
                                                  v668 = 0;
                                                  LODWORD(v656) = WORD2(Size);
                                                  do
                                                  {
                                                    v216 = v660[3] | ((v660[2] | ((v660[1] | (*v660 << 8)) << 8)) << 8);
                                                    v217 = v660[7]
                                                         | ((v660[6] | ((v660[5] | (v660[4] << 8)) << 8)) << 8);
                                                    v660 += 8;
                                                    v218 = v212 ^ v210 ^ v217 ^ v211 ^ v216 ^ 0xAB69605E;
                                                    v219 = v211
                                                         ^ v216
                                                         ^ (__ROR4__(v218, 22) + v215 * __ROR4__(v218 + 1419157410, 27));
                                                    v220 = v218
                                                         ^ (43881 * __ROR4__(v212 + v219, 9) - __ROR4__(v219, 30));
                                                    v221 = v219 ^ (v700 * (v220 - v215) - (v220 >> 13));
                                                    v222 = v220
                                                         ^ (v214 * __ROR4__(v221 ^ 0xAB69, 26) - __ROR4__(v221, 30));
                                                    v223 = v221 ^ (v212 - (v222 ^ 0xAB69605E));
                                                    v224 = v222 ^ (43881 * (v215 ^ v223)) ^ __ROR4__(v223, 6);
                                                    v225 = v223
                                                         ^ (__ROR4__(v224, 30) + v700 * __ROR4__(v212 + v224, 15));
                                                    v226 = v224
                                                         ^ (v214 * __ROR4__(v225 + 1419157410, 14) - __ROR4__(v225, 24));
                                                    v227 = v225
                                                         ^ __ROR4__(v226, 10)
                                                         ^ ((_DWORD)v656 * __ROR4__(v226 ^ 0xAB69605E, 12));
                                                    v228 = v226 ^ (v227 >> 10) ^ (43881 * (v214 ^ v227));
                                                    v215 = (int)v656;
                                                    v229 = v227 ^ (v214 * (v700 + __ROR4__(~v228, 5)));
                                                    v230 = v228 ^ (v229 - v214) ^ 0xAB69605E;
                                                    v231 = v229
                                                         ^ ((v230 >> 2) + (_DWORD)v656 * __ROR4__(v214 ^ v230, 30));
                                                    v232 = v230
                                                         ^ (__ROR4__(v231, 25) + 43881 * __ROR4__(v231 - v212, 6));
                                                    v233 = v231
                                                         ^ (v700 * ((unsigned int)v656 ^ v232) + __ROR4__(v232, 9));
                                                    v234 = v232
                                                         ^ (__ROR4__(v233, 25) + v214 * __ROR4__(v233 ^ 0xAB69, 27));
                                                    v235 = v233 ^ v234 ^ v663;
                                                    v236 = v234 ^ ((_DWORD)v656 * (__ROR4__(v235, 3) - 43881));
                                                    v237 = v235 ^ (v700 * __ROR4__(v236 - v212, 1) - __ROR4__(v236, 6));
                                                    v238 = v236
                                                         ^ (__ROR4__(v237, 18) + v214 * __ROR4__(v237 - 1419157410, 29));
                                                    v239 = v237
                                                         ^ ((_DWORD)v656 * __ROR4__(v238 - 1419157410, 17)
                                                          - __ROR4__(v238, 14));
                                                    v240 = v238 ^ (v239 >> 3) ^ (43881 * (v239 ^ v700));
                                                    v241 = v657;
                                                    v242 = v240;
                                                    v243 = v240;
                                                    v210 = v703 ^ v240;
                                                    LODWORD(v703) = v217;
                                                    v211 = (unsigned int)lpMem
                                                         ^ v239
                                                         ^ __ROR4__(v242, 30)
                                                         ^ (v700 * __ROR4__(v212 ^ v243, 28));
                                                    *((_BYTE *)v657 + 3) = v211;
                                                    v241[7] = v210;
                                                    v241[2] = __ROR4__(v211, 8);
                                                    v241[6] = __ROR4__(v210, 8);
                                                    v241[1] = __ROR4__(v211, 16);
                                                    v241[5] = __ROR4__(v210, 16);
                                                    *v241 = __ROR4__(v211, 24);
                                                    v241[4] = __ROR4__(v210, 24);
                                                    LODWORD(lpMem) = v216;
                                                    v657 = v241 + 8;
                                                    ++v668;
                                                  }
                                                  while ( v668 < (unsigned __int64)v213 );
                                                  v4 = v691;
                                                  v5 = v682;
                                                  v9 = v677;
                                                  v6 = v681;
                                                  v203 = v671;
                                                  v205 = (unsigned int *)v659;
                                                  v206 = v664;
                                                }
                                                if ( !v203 )
                                                {
                                                  v244 = v661;
                                                  goto LABEL_299;
                                                }
                                                v246 = 0;
                                                if ( v203 >= 0x20 )
                                                {
                                                  v247 = 0;
                                                  v248 = 0;
                                                  do
                                                  {
                                                    v247 = _mm_xor_ps(
                                                             v247,
                                                             (__m128)_mm_loadu_si128((const __m128i *)((char *)v205 + v246)));
                                                    v249 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v205 + v246 + 16));
                                                    v246 += 32LL;
                                                    v250 = _mm_xor_ps(v249, v248);
                                                    v248 = v250;
                                                  }
                                                  while ( v246 < (v203 & 0xFFFFFFFFFFFFFFE0uLL) );
                                                  v251 = _mm_xor_ps(v247, v250);
                                                  v252 = _mm_xor_ps(v251, (__m128)_mm_srli_si128((__m128i)v251, 8));
                                                  v253 = _mm_xor_ps(v252, (__m128)_mm_srli_si128((__m128i)v252, 4));
                                                  v254 = _mm_xor_ps(v253, (__m128)_mm_srli_si128((__m128i)v253, 2));
                                                  v244 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                      v254,
                                                                                      (__m128)_mm_srli_si128(
                                                                                                (__m128i)v254,
                                                                                                1)));
                                                  if ( v246 >= v203 )
                                                  {
LABEL_299:
                                                    if ( v244 != *(_QWORD *)&v206[v203] )
                                                    {
                                                      v245 = GetProcessHeap();
                                                      HeapFree(v245, 0, v659);
LABEL_301:
                                                      v48 = v648;
                                                      v13 = -805306367;
                                                      LODWORD(v700) = -805306367;
                                                      goto LABEL_110;
                                                    }
                                                    v666 = v205;
                                                    v264 = v205;
                                                    if ( (unsigned int)v203 >= 4 )
                                                    {
                                                      v296 = v205 + 1;
                                                      if ( v296 < v264 )
                                                        goto LABEL_331;
                                                      if ( (unsigned int)(v203 - 4) < 4 )
                                                      {
                                                        v258 = -1073741762;
                                                        goto LABEL_332;
                                                      }
                                                      v259 = v296 + 1;
                                                      v668 = (SIZE_T)(v296 + 1);
                                                      if ( v296 + 1 < v296 )
                                                      {
                                                        v48 = v648;
LABEL_340:
                                                        v13 = -805306219;
                                                        LODWORD(v700) = -805306219;
                                                        goto LABEL_110;
                                                      }
                                                      v297 = *v296;
                                                      LODWORD(lpMem) = v297;
                                                      if ( (int)v203 - 8 < (unsigned int)v297 )
                                                      {
                                                        v258 = -1073741762;
                                                        goto LABEL_332;
                                                      }
                                                      if ( (unsigned int)v297 >= 0xFFFFFFF8 )
                                                        goto LABEL_331;
                                                      v265 = (unsigned __int64)v259 + v297;
                                                      v674 = v297;
                                                      if ( (char *)v264 + (unsigned int)v203 >= (char *)v259 + v297
                                                        && (unsigned __int64)v264
                                                         + (unsigned int)v203
                                                         - v297
                                                         - (_QWORD)v259 < 8 )
                                                      {
                                                        LODWORD(v700) = 0;
                                                        v261 = 0;
                                                        if ( !v259 )
                                                        {
                                                          v262 = 0;
LABEL_347:
                                                          v266 = 0;
                                                          LODWORD(v703) = *v264;
                                                          v678 = 0;
                                                          if ( !(_DWORD)lpMem )
                                                          {
LABEL_348:
                                                            v48 = v648;
                                                            v267 = v653;
                                                            v268 = v645;
                                                            v260 = v655;
                                                            if ( v259 )
                                                            {
                                                              memcpy_0(v266, v259, v674);
                                                              v48 = v648;
                                                              v267 = v653;
                                                              v268 = v645;
                                                              v260 = v655;
                                                              v261 = v700;
                                                              v266 = v678;
                                                            }
                                                            v667 = v261;
                                                            v658 = v266;
                                                            if ( (_DWORD)v703 == v261 )
                                                            {
LABEL_841:
                                                              v13 = v262 | 0x10000000;
                                                              v655 = v260;
                                                              LODWORD(v700) = v13;
                                                              v645 = v268;
                                                              v653 = v267;
                                                              v648 = v48;
                                                            }
                                                            else
                                                            {
                                                              v13 = -805306306;
                                                              LODWORD(v700) = -805306306;
                                                            }
LABEL_110:
                                                            if ( !v48 )
                                                            {
LABEL_112:
                                                              v50 = v653;
                                                              if ( v653 )
                                                              {
                                                                lpMem = (LPVOID)*((_QWORD *)v653 + 1);
                                                                if ( lpMem )
                                                                {
                                                                  v51 = GetProcessHeap();
                                                                  HeapFree(v51, 0, lpMem);
                                                                  v50 = v653;
                                                                  *((_QWORD *)v653 + 1) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v50 + 3);
                                                                if ( lpMem )
                                                                {
                                                                  v52 = GetProcessHeap();
                                                                  HeapFree(v52, 0, lpMem);
                                                                  v50 = v653;
                                                                  *((_QWORD *)v653 + 3) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v50 + 5);
                                                                if ( lpMem )
                                                                {
                                                                  v53 = GetProcessHeap();
                                                                  HeapFree(v53, 0, lpMem);
                                                                  *((_QWORD *)v653 + 5) = 0;
                                                                }
                                                                v54 = GetProcessHeap();
                                                                HeapFree(v54, 0, v653);
                                                              }
                                                              if ( v645 )
                                                              {
                                                                v55 = GetProcessHeap();
                                                                HeapFree(v55, 0, v645);
                                                              }
                                                              if ( v675 )
                                                              {
                                                                v56 = GetProcessHeap();
                                                                HeapFree(v56, 0, v675);
                                                              }
                                                              v57 = v655;
                                                              if ( v655 )
                                                              {
                                                                lpMem = (LPVOID)*((_QWORD *)v655 + 1);
                                                                if ( lpMem )
                                                                {
                                                                  v58 = GetProcessHeap();
                                                                  HeapFree(v58, 0, lpMem);
                                                                  v57 = v655;
                                                                  *((_QWORD *)v655 + 1) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v57 + 3);
                                                                if ( lpMem )
                                                                {
                                                                  v59 = GetProcessHeap();
                                                                  HeapFree(v59, 0, lpMem);
                                                                  v57 = v655;
                                                                  *((_QWORD *)v655 + 3) = 0;
                                                                }
                                                                lpMem = (LPVOID)*((_QWORD *)v57 + 5);
                                                                if ( lpMem )
                                                                {
                                                                  v60 = GetProcessHeap();
                                                                  HeapFree(v60, 0, lpMem);
                                                                  *((_QWORD *)v655 + 5) = 0;
                                                                }
                                                                v61 = GetProcessHeap();
                                                                HeapFree(v61, 0, v655);
                                                              }
                                                              if ( !v666 )
                                                              {
LABEL_135:
                                                                if ( v13 < 0 )
                                                                  goto LABEL_79;
                                                                if ( !v667 )
                                                                {
                                                                  v13 = -1073425151;
                                                                  goto LABEL_21;
                                                                }
                                                                if ( !v658 )
                                                                {
                                                                  v13 = -1073741811;
                                                                  LODWORD(v700) = -1073741811;
                                                                  goto LABEL_79;
                                                                }
                                                                if ( (char *)v658 + 4 < v658 )
                                                                  goto LABEL_20;
                                                                v62 = 0;
                                                                if ( *(_DWORD *)v658 )
                                                                  v62 = (int *)((char *)v658 + 4);
                                                                if ( *(_DWORD *)v658 != 4 )
                                                                {
                                                                  v13 = -1073741789;
                                                                  goto LABEL_21;
                                                                }
                                                                v13 = *v62;
                                                                LODWORD(v700) = v13;
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
                                                                if ( v667 != 6 )
                                                                {
                                                                  v13 = -1073425151;
                                                                  goto LABEL_21;
                                                                }
                                                                v63 = v658;
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
                                                                v129 = 0;
                                                                if ( *v63 )
                                                                  v129 = (SIZE_T *)(v63 + 1);
                                                                if ( *v63 != 8 )
                                                                {
                                                                  v13 = -1073741789;
                                                                  goto LABEL_21;
                                                                }
                                                                v270 = v658;
                                                                v700 = *v129;
                                                                for ( jj = 0; ; ++jj )
                                                                {
                                                                  v272 = v270 + 1;
                                                                  if ( jj >= 2 )
                                                                    break;
                                                                  if ( v272 < v270 )
                                                                    goto LABEL_20;
                                                                  v270 = (_DWORD *)((char *)v272 + (unsigned int)*v270);
                                                                  if ( v270 < v272 )
                                                                    goto LABEL_20;
                                                                }
                                                                if ( v272 < v270 )
                                                                  goto LABEL_20;
                                                                v273 = 0;
                                                                if ( *v270 )
                                                                  v273 = v270 + 1;
                                                                if ( *v270 != 4 )
                                                                {
                                                                  v13 = -1073741789;
                                                                  goto LABEL_21;
                                                                }
                                                                v274 = *v273;
                                                                v275 = (unsigned int *)v658;
                                                                for ( kk = 0; ; ++kk )
                                                                {
                                                                  v277 = *v275;
                                                                  v278 = v275 + 1;
                                                                  if ( kk >= 3 )
                                                                    break;
                                                                  if ( v278 < v275 )
                                                                    goto LABEL_34;
                                                                  v275 = (unsigned int *)((char *)v278 + v277);
                                                                  if ( (unsigned int *)((char *)v278 + v277) < v278 )
                                                                    goto LABEL_34;
                                                                }
                                                                if ( v278 >= v275 )
                                                                {
                                                                  v279 = 0;
                                                                  v280 = 0;
                                                                  v281 = (unsigned int *)v658;
                                                                  if ( (_DWORD)v277 )
                                                                    v279 = (SIZE_T)v278;
                                                                  v703 = v279;
                                                                  while ( 1 )
                                                                  {
                                                                    v282 = *v281;
                                                                    v283 = v281 + 1;
                                                                    if ( v280 >= 4 )
                                                                      break;
                                                                    if ( v283 < v281 )
                                                                      goto LABEL_20;
                                                                    v281 = (unsigned int *)((char *)v283 + v282);
                                                                    if ( (unsigned int *)((char *)v283 + v282) < v283 )
                                                                      goto LABEL_20;
                                                                    ++v280;
                                                                  }
                                                                  if ( v283 >= v281 )
                                                                  {
                                                                    v284 = 0;
                                                                    if ( (_DWORD)v282 )
                                                                      v284 = v281 + 1;
                                                                    if ( (_DWORD)v282 != 4 )
                                                                    {
                                                                      v13 = -1073741789;
                                                                      goto LABEL_21;
                                                                    }
                                                                    v285 = *v284;
                                                                    v286 = (unsigned int *)v658;
                                                                    for ( mm = 0; ; ++mm )
                                                                    {
                                                                      v288 = *v286;
                                                                      v289 = v286 + 1;
                                                                      if ( mm >= 5 )
                                                                        break;
                                                                      if ( v289 < v286 )
                                                                        goto LABEL_20;
                                                                      v286 = (unsigned int *)((char *)v289 + v288);
                                                                      if ( (unsigned int *)((char *)v289 + v288) < v289 )
                                                                        goto LABEL_20;
                                                                    }
                                                                    if ( v289 >= v286 )
                                                                    {
                                                                      v128 = 0;
                                                                      if ( (_DWORD)v288 )
                                                                        v128 = v289;
                                                                      if ( (_DWORD)v288 != 4 )
                                                                      {
                                                                        v13 = -1073741789;
                                                                        goto LABEL_21;
                                                                      }
                                                                      if ( v672 != v700 )
                                                                      {
                                                                        v13 = -1073425151;
                                                                        goto LABEL_21;
                                                                      }
                                                                      v688 = *v128;
                                                                      v685 = v274;
                                                                      if ( v285 > 4 )
                                                                      {
                                                                        v13 = -2147024774;
                                                                        goto LABEL_21;
                                                                      }
                                                                      if ( (unsigned int)v277 > 4 )
                                                                      {
                                                                        v13 = -2147024774;
                                                                        goto LABEL_21;
                                                                      }
                                                                      memcpy_0(v5, (const void *)v703, v277);
                                                                      v13 = 0;
                                                                      LODWORD(v700) = 0;
LABEL_180:
                                                                      if ( (_DWORD)lpMem )
                                                                      {
                                                                        v13 = (int)lpMem;
                                                                        LODWORD(v700) = (_DWORD)lpMem;
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
                                                                      if ( v658 )
                                                                      {
                                                                        v37 = GetProcessHeap();
                                                                        HeapFree(v37, 0, v658);
                                                                      }
                                                                      if ( v9 )
                                                                      {
                                                                        v618 = GetProcessHeap();
                                                                        HeapFree(v618, 0, v9);
                                                                      }
                                                                      if ( v6 )
                                                                      {
                                                                        v619 = GetProcessHeap();
                                                                        HeapFree(v619, 0, v6);
                                                                      }
                                                                      if ( v13 < 0 )
                                                                      {
                                                                        LocalFree(v5);
                                                                        goto LABEL_89;
                                                                      }
                                                                      if ( !v688 )
                                                                        goto LABEL_24;
                                                                      v298 = 0;
                                                                      v299 = 0;
                                                                      dwBytesa = 0;
                                                                      *(_OWORD *)v665 = 0;
                                                                      v300 = GetProcessHeap();
                                                                      v301 = (unsigned __int8 *)HeapAlloc(
                                                                                                  v300,
                                                                                                  8u,
                                                                                                  0xA0u);
                                                                      v664 = v301;
                                                                      v302 = v301;
                                                                      if ( !v301 )
                                                                        goto LABEL_424;
                                                                      *(_OWORD *)v301 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
                                                                      *((_OWORD *)v301 + 1) = xmmword_1800301A0;
                                                                      *((_OWORD *)v301 + 2) = xmmword_1800301B0;
                                                                      *((_OWORD *)v301 + 3) = xmmword_1800301C0;
                                                                      *((_OWORD *)v301 + 4) = xmmword_1800301D0;
                                                                      *((_OWORD *)v301 + 5) = xmmword_1800301E0;
                                                                      *((_OWORD *)v301 + 6) = xmmword_1800301F0;
                                                                      *((_OWORD *)v301 + 7) = xmmword_180030200;
                                                                      *((_OWORD *)v301 + 8) = xmmword_180030210;
                                                                      *((_OWORD *)v301 + 9) = xmmword_180030220;
                                                                      v303 = GetProcessHeap();
                                                                      v660 = (unsigned __int8 *)HeapAlloc(v303, 8u, 8u);
                                                                      if ( !v660 )
                                                                        goto LABEL_423;
                                                                      v299 = v660;
                                                                      *(_QWORD *)v660 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
                                                                      LODWORD(lpMem) = 0;
                                                                      Size = __rdtsc();
                                                                      LODWORD(v703) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 4, &v703) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  0,
                                                                                  (unsigned int)v703,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      LODWORD(v703) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 160, &v703) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  (unsigned int)lpMem,
                                                                                  (unsigned int)v703,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      LODWORD(v703) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 8, &v703) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  (unsigned int)lpMem,
                                                                                  (unsigned int)v703,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      LODWORD(v703) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 8, &v703) < 0 )
                                                                        goto LABEL_423;
                                                                      if ( (int)RtlUIntAdd(
                                                                                  (unsigned int)lpMem,
                                                                                  (unsigned int)v703,
                                                                                  &lpMem) < 0 )
                                                                        goto LABEL_423;
                                                                      HIDWORD(v665[0]) = (_DWORD)lpMem;
                                                                      v465 = (unsigned int)lpMem;
                                                                      v466 = GetProcessHeap();
                                                                      v467 = HeapAlloc(v466, 8u, v465);
                                                                      if ( !v467 )
                                                                        goto LABEL_423;
                                                                      v309 = 0;
                                                                      v665[1] = (size_t)v467;
                                                                      LODWORD(v665[0]) = 0;
                                                                      LODWORD(v670) = 0;
                                                                      v669 = 0;
                                                                      v703 = (SIZE_T)v467;
                                                                      if ( (int)RtlULongLongAdd(v467, 4, &v670) < 0
                                                                        || (unsigned __int64)(v468 + 2) > v665[1] + HIDWORD(v665[0]) )
                                                                      {
                                                                        goto LABEL_423;
                                                                      }
                                                                      v469 = v670;
                                                                      *v468 = 4;
                                                                      *v469 = 4;
                                                                      v470 = (unsigned int *)v665[1];
                                                                      v471 = LODWORD(v665[0]) + 1;
                                                                      LODWORD(v670) = 0;
                                                                      ++LODWORD(v665[0]);
                                                                      v669 = 0;
                                                                      if ( v665[1] )
                                                                      {
                                                                        v703 = v665[1];
                                                                        v472 = 0;
                                                                        while ( v472 < v471 )
                                                                        {
                                                                          v473 = *v470;
                                                                          LODWORD(lpMem) = 0;
                                                                          if ( (int)RtlUIntAdd(4, v473, &lpMem) < 0 )
                                                                            goto LABEL_423;
                                                                          v298 = v302;
                                                                          if ( (int)RtlULongLongAdd(
                                                                                      v474,
                                                                                      (unsigned int)lpMem,
                                                                                      &v703) < 0 )
                                                                            goto LABEL_424;
                                                                          v470 = (unsigned int *)v703;
                                                                          v472 = v475 + 1;
                                                                          v299 = v660;
                                                                          v309 = 0;
                                                                        }
                                                                        if ( (int)RtlULongLongAdd(v470, 4, &v670) < 0
                                                                          || (unsigned __int64)(v476 + 41) > v665[1] + HIDWORD(v665[0]) )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                        v477 = v670;
                                                                        *v476 = 160;
                                                                        *v477 = *(_OWORD *)v302;
                                                                        v477[1] = *((_OWORD *)v302 + 1);
                                                                        v477[2] = *((_OWORD *)v302 + 2);
                                                                        v477[3] = *((_OWORD *)v302 + 3);
                                                                        v477[4] = *((_OWORD *)v302 + 4);
                                                                        v477[5] = *((_OWORD *)v302 + 5);
                                                                        v477[6] = *((_OWORD *)v302 + 6);
                                                                        v477[7] = *((_OWORD *)v302 + 7);
                                                                        v477[8] = *((_OWORD *)v302 + 8);
                                                                        v477[9] = *((_OWORD *)v302 + 9);
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(4, 160, &lpMem) < 0
                                                                          || (int)RtlUIntAdd(
                                                                                    HIDWORD(v665[0]),
                                                                                    (unsigned int)lpMem,
                                                                                    (char *)v665 + 4) < 0 )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                      }
                                                                      v478 = (unsigned int *)v665[1];
                                                                      v479 = LODWORD(v665[0]) + 1;
                                                                      LODWORD(v670) = 0;
                                                                      ++LODWORD(v665[0]);
                                                                      v669 = 0;
                                                                      if ( v665[1] )
                                                                      {
                                                                        v703 = v665[1];
                                                                        v480 = 0;
                                                                        while ( v480 < v479 )
                                                                        {
                                                                          v481 = *v478;
                                                                          LODWORD(lpMem) = 0;
                                                                          if ( (int)RtlUIntAdd(4, v481, &lpMem) < 0 )
                                                                            goto LABEL_423;
                                                                          v298 = v302;
                                                                          if ( (int)RtlULongLongAdd(
                                                                                      v482,
                                                                                      (unsigned int)lpMem,
                                                                                      &v703) < 0 )
                                                                            goto LABEL_424;
                                                                          v478 = (unsigned int *)v703;
                                                                          v480 = v483 + 1;
                                                                          v299 = v660;
                                                                          v309 = 0;
                                                                        }
                                                                        if ( (int)RtlULongLongAdd(v478, 4, &v670) < 0
                                                                          || (unsigned __int64)(v484 + 3) > v665[1] + HIDWORD(v665[0]) )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                        v485 = v670;
                                                                        *v484 = 8;
                                                                        *v485 = *v299;
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(4, 8, &lpMem) < 0
                                                                          || (int)RtlUIntAdd(
                                                                                    HIDWORD(v665[0]),
                                                                                    (unsigned int)lpMem,
                                                                                    (char *)v665 + 4) < 0 )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                      }
                                                                      v486 = (unsigned int *)v665[1];
                                                                      v487 = LODWORD(v665[0]) + 1;
                                                                      LODWORD(v670) = 0;
                                                                      ++LODWORD(v665[0]);
                                                                      v669 = 0;
                                                                      if ( v665[1] )
                                                                      {
                                                                        v703 = v665[1];
                                                                        v488 = 0;
                                                                        while ( v488 < v487 )
                                                                        {
                                                                          v489 = *v486;
                                                                          LODWORD(lpMem) = 0;
                                                                          if ( (int)RtlUIntAdd(4, v489, &lpMem) < 0 )
                                                                            goto LABEL_423;
                                                                          v298 = v302;
                                                                          if ( (int)RtlULongLongAdd(
                                                                                      v490,
                                                                                      (unsigned int)lpMem,
                                                                                      &v703) < 0 )
                                                                            goto LABEL_424;
                                                                          v486 = (unsigned int *)v703;
                                                                          v488 = v491 + 1;
                                                                          v299 = v660;
                                                                          v309 = 0;
                                                                        }
                                                                        if ( (int)RtlULongLongAdd(v486, 4, &v670) < 0
                                                                          || (unsigned __int64)(v492 + 3) > v665[1] + HIDWORD(v665[0]) )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                        v493 = (size_t *)v670;
                                                                        v494 = Size;
                                                                        *v492 = 8;
                                                                        *v493 = v494;
                                                                      }
                                                                      else
                                                                      {
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(4, 8, &lpMem) < 0
                                                                          || (int)RtlUIntAdd(
                                                                                    HIDWORD(v665[0]),
                                                                                    (unsigned int)lpMem,
                                                                                    (char *)v665 + 4) < 0 )
                                                                        {
                                                                          goto LABEL_423;
                                                                        }
                                                                      }
                                                                      ++LODWORD(v665[0]);
                                                                      LODWORD(lpMem) = 0;
                                                                      if ( (int)RtlUIntAdd(4, 4, &lpMem) >= 0 )
                                                                      {
                                                                        LODWORD(v703) = (_DWORD)lpMem;
                                                                        LODWORD(lpMem) = 0;
                                                                        if ( (int)RtlUIntAdd(v495, 8, &lpMem) >= 0
                                                                          && (int)RtlUIntAdd(
                                                                                    v496,
                                                                                    (unsigned int)lpMem,
                                                                                    &v703) >= 0 )
                                                                        {
                                                                          v384 = 0;
                                                                          v655 = 0;
                                                                          Size = __rdtsc();
                                                                          v661 = 0;
                                                                          v676 = 8;
                                                                          v399 = RtlUIntAdd(8, HIDWORD(v665[0]), &v676);
                                                                          if ( v399 < 0 )
                                                                          {
LABEL_497:
                                                                            v667 = 0;
                                                                            v308 = v399 | 0x10000000;
                                                                            v666 = 0;
                                                                            v385 = 0;
                                                                            v646 = 0;
                                                                            v690 = 0;
                                                                            v657 = 0;
                                                                            Size = 0;
                                                                            if ( v308 < 0 )
                                                                              goto LABEL_431;
                                                                            if ( v384 )
                                                                            {
                                                                              if ( !v398
                                                                                || (v674 = v398 + 8LL,
                                                                                    v668 = (SIZE_T)MemoryAlloc(v674),
                                                                                    (v401 = v668) == 0) )
                                                                              {
                                                                                LODWORD(v701) = -805306367;
                                                                                goto LABEL_433;
                                                                              }
                                                                              LOBYTE(v400) = 0;
                                                                              v402 = v703;
                                                                              v403 = v661;
                                                                              LODWORD(lpMem) = v703;
                                                                              v663 = v400;
                                                                              if ( v661 )
                                                                              {
                                                                                v404 = 0;
                                                                                if ( v661 < 0x20uLL )
                                                                                  goto LABEL_967;
                                                                                LODWORD(lpMem) = v703;
                                                                                v405 = 0;
                                                                                v406 = 0;
                                                                                do
                                                                                {
                                                                                  v405 = _mm_xor_ps(
                                                                                           v405,
                                                                                           (__m128)_mm_loadu_si128((const __m128i *)&v384[v404]));
                                                                                  v407 = (__m128)_mm_loadu_si128((const __m128i *)&v384[v404 + 16]);
                                                                                  v404 += 32LL;
                                                                                  v408 = _mm_xor_ps(v407, v406);
                                                                                  v406 = v408;
                                                                                }
                                                                                while ( v404 < (v661 & 0xFFFFFFE0) );
                                                                                v409 = _mm_xor_ps(v405, v408);
                                                                                v410 = _mm_xor_ps(
                                                                                         v409,
                                                                                         (__m128)_mm_srli_si128(
                                                                                                   (__m128i)v409,
                                                                                                   8));
                                                                                v411 = _mm_xor_ps(
                                                                                         v410,
                                                                                         (__m128)_mm_srli_si128(
                                                                                                   (__m128i)v410,
                                                                                                   4));
                                                                                v412 = _mm_xor_ps(
                                                                                         v411,
                                                                                         (__m128)_mm_srli_si128(
                                                                                                   (__m128i)v411,
                                                                                                   2));
                                                                                v400 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v412, (__m128)_mm_srli_si128((__m128i)v412, 1)));
                                                                                v663 = v400;
                                                                                if ( v404 < v661 )
                                                                                {
LABEL_967:
                                                                                  do
                                                                                    LOBYTE(v400) = v384[v404++] ^ v400;
                                                                                  while ( v404 < v661 );
                                                                                  v663 = v400;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                LODWORD(lpMem) = v703;
                                                                              }
                                                                              v659 = (void *)0xC81ECB17B1B54A58LL;
                                                                              v678 = v384;
                                                                              v679 = v668;
                                                                              v413 = v661 & 7;
                                                                              if ( (v661 & 7) == 0 )
                                                                              {
                                                                                v414 = 0;
                                                                                LODWORD(v675) = -1;
                                                                                LODWORD(v681) = 0;
                                                                                LODWORD(v677) = 0;
                                                                                goto LABEL_510;
                                                                              }
                                                                              v620 = 0;
                                                                              LODWORD(v703) = 0;
                                                                              v621 = v384;
                                                                              v622 = 0;
                                                                              v623 = 0;
                                                                              do
                                                                              {
                                                                                v624 = *v621;
                                                                                v625 = 8 * v620;
                                                                                ++v621;
                                                                                if ( v620 >= 4 )
                                                                                  v623 |= v624 << (56 - v625);
                                                                                else
                                                                                  v622 |= v624 << (24 - v625);
                                                                                v620 = v703 + 1;
                                                                                LODWORD(v703) = v620;
                                                                              }
                                                                              while ( (int)v620 < v413 );
                                                                              LODWORD(v672) = 0;
                                                                              LODWORD(v677) = v623;
                                                                              v626 = v622 ^ 0xB17A307A;
                                                                              LODWORD(v681) = v622;
                                                                              v5 = v682;
                                                                              v627 = v623;
                                                                              v13 = v700;
                                                                              LODWORD(v675) = v626;
                                                                              v309 = 0;
                                                                              v628 = 0;
                                                                              v629 = (_BYTE *)v668;
                                                                              LODWORD(v703) = v626;
                                                                              v630 = v627 ^ 0x42F6B18D;
                                                                              v631 = (int)v675;
                                                                              v678 = v621;
                                                                              LODWORD(lpMem) = v402;
                                                                              v632 = v630;
                                                                              v655 = v384;
                                                                              do
                                                                              {
                                                                                v671 = (SIZE_T)(v629 + 1);
                                                                                if ( v628 >= 4 )
                                                                                {
                                                                                  v632 = __ROR4__(v632, 24);
                                                                                  v633 = v632;
                                                                                }
                                                                                else
                                                                                {
                                                                                  v631 = __ROR4__(v631, 24);
                                                                                  v633 = v631;
                                                                                }
                                                                                *v629 = v633;
                                                                                ++v628;
                                                                                v629 = (_BYTE *)v671;
                                                                              }
                                                                              while ( v628 < v413 );
                                                                              v679 = v671;
                                                                              LOBYTE(v400) = v663;
                                                                              v385 = 0;
                                                                              if ( (unsigned int)v413 <= 4 )
                                                                              {
                                                                                LODWORD(v675) = 0;
                                                                                if ( (unsigned int)v413 < 4 )
                                                                                {
                                                                                  v414 = (unsigned int)v703 >> (8 * (4 - v413)) << (8 * (4 - v413));
LABEL_510:
                                                                                  v669 = (LPVOID)(v403 >> 3);
                                                                                  if ( v403 >> 3 )
                                                                                  {
                                                                                    v415 = v669;
                                                                                    v416 = (int)v675;
                                                                                    v417 = (unsigned __int8 *)v678;
                                                                                    v418 = v679;
                                                                                    v419 = (int)v681;
                                                                                    v420 = (int)v677;
                                                                                    LODWORD(v672) = WORD2(v659);
                                                                                    LODWORD(v656) = HIWORD(HIDWORD(v659));
                                                                                    LODWORD(v703) = 19032;
                                                                                    LODWORD(v658) = WORD1(v659);
                                                                                    LODWORD(Src) = HIWORD(HIDWORD(v659));
                                                                                    v421 = HIWORD(HIDWORD(v659));
                                                                                    v649 = HIDWORD(v659) ^ 0xB1B54A58;
                                                                                    v671 = 0;
                                                                                    do
                                                                                    {
                                                                                      v422 = v417[1];
                                                                                      v423 = *v417;
                                                                                      v424 = v417[4];
                                                                                      v417 += 8;
                                                                                      v425 = *(v417 - 5)
                                                                                           | ((*(v417 - 6)
                                                                                             | ((v422 | (v423 << 8)) << 8)) << 8);
                                                                                      v426 = *(v417 - 1)
                                                                                           | ((*(v417 - 2)
                                                                                             | ((*(v417 - 3)
                                                                                               | (v424 << 8)) << 8)) << 8);
                                                                                      v427 = v414
                                                                                           ^ v425
                                                                                           ^ ((v416 ^ v426) - v703);
                                                                                      v428 = __ROR4__(v427, 15);
                                                                                      v429 = HIDWORD(v659) ^ v427;
                                                                                      v430 = v416
                                                                                           ^ v426
                                                                                           ^ (__ROR4__(v429, 7)
                                                                                            + WORD1(v659) * v428);
                                                                                      v431 = v429
                                                                                           ^ (v672
                                                                                            * __ROR4__(
                                                                                                v430 - 1313519016,
                                                                                                9)
                                                                                            - __ROR4__(v430, 10));
                                                                                      v432 = v430
                                                                                           ^ (__ROR4__(v431, 27)
                                                                                            + v421
                                                                                            * __ROR4__(v672 ^ v431, 28));
                                                                                      v433 = v431
                                                                                           ^ (HIDWORD(v659)
                                                                                            - (v432 ^ 0xB1B54A58));
                                                                                      v434 = v432
                                                                                           ^ (WORD1(v659)
                                                                                            * (v433 - v703)
                                                                                            - (v433 >> 6));
                                                                                      v435 = v433
                                                                                           ^ (v703
                                                                                            * (v672 ^ __ROR4__(v434, 15)));
                                                                                      v436 = v434
                                                                                           ^ (v672
                                                                                            * (v421 + __ROR4__(~v435, 3)));
                                                                                      v437 = v435
                                                                                           ^ (v436 - v703 - HIDWORD(v659));
                                                                                      v438 = v436
                                                                                           ^ ((_DWORD)v658
                                                                                            * (v437 ^ (unsigned int)v656))
                                                                                           ^ __ROR4__(v437, 10);
                                                                                      v439 = v437
                                                                                           ^ __ROR4__(v438, 3)
                                                                                           ^ (v672
                                                                                            * __ROR4__(v438 ^ v703, 26));
                                                                                      v440 = v438
                                                                                           ^ (v703
                                                                                            * (__ROR4__(v439, 15) - v421));
                                                                                      v441 = v439
                                                                                           ^ ((v440 ^ (v440 >> 14)) >> 1)
                                                                                           ^ (v703
                                                                                            * (v440 ^ (unsigned int)v656))
                                                                                           ^ (v703
                                                                                            * ((8 * (v440 - v672))
                                                                                             | ((v440
                                                                                               - (unsigned int)v672) >> 29)));
                                                                                      v442 = v440
                                                                                           ^ (WORD1(v659)
                                                                                            * (v441 - v672)
                                                                                            - (v441 >> 13));
                                                                                      v443 = v441
                                                                                           ^ __ROR4__(v442, 11)
                                                                                           ^ (v672
                                                                                            * __ROR4__(
                                                                                                -1313519016 - v442,
                                                                                                9));
                                                                                      v444 = v442
                                                                                           ^ (v443 - v421 + 1313519016);
                                                                                      v445 = v443
                                                                                           ^ (v703
                                                                                            * (v444 ^ WORD1(v659))
                                                                                            - __ROR4__(v444, 7));
                                                                                      v446 = v444
                                                                                           ^ (WORD1(v659)
                                                                                            * __ROR4__(
                                                                                                v445
                                                                                              ^ (unsigned int)v656,
                                                                                                28)
                                                                                            - __ROR4__(v445, 16));
                                                                                      v447 = v445
                                                                                           ^ (__ROR4__(v446, 4)
                                                                                            + v672
                                                                                            * __ROR4__(
                                                                                                -1313519016 - v446,
                                                                                                10));
                                                                                      v418 += 8LL;
                                                                                      v448 = v446
                                                                                           ^ __ROR4__(v447, 9)
                                                                                           ^ (v421
                                                                                            * __ROR4__(
                                                                                                v447 + 1313519016,
                                                                                                4));
                                                                                      v449 = v447
                                                                                           ^ (v703
                                                                                            * __ROR4__(
                                                                                                v448 ^ HIDWORD(v659),
                                                                                                24)
                                                                                            - __ROR4__(v448, 30));
                                                                                      v450 = v448
                                                                                           ^ (WORD1(v659)
                                                                                            * __ROR4__(
                                                                                                HIDWORD(v659) - v449,
                                                                                                11)
                                                                                            - __ROR4__(v449, 12));
                                                                                      v451 = v450 >> 8;
                                                                                      v452 = v672 * (WORD1(v659) ^ v450);
                                                                                      v453 = v649 ^ v420 ^ v450;
                                                                                      v420 = v426;
                                                                                      v454 = v449 ^ v451 ^ v452;
                                                                                      v414 = v454 ^ v419;
                                                                                      v416 = v454 ^ v453;
                                                                                      *(_BYTE *)(v418 - 5) = v454 ^ v419;
                                                                                      LOBYTE(v451) = __ROR4__(v454 ^ v419, 8);
                                                                                      v419 = v425;
                                                                                      *(_BYTE *)(v418 - 1) = v416;
                                                                                      *(_BYTE *)(v418 - 6) = v451;
                                                                                      *(_BYTE *)(v418 - 2) = __ROR4__(v416, 8);
                                                                                      *(_BYTE *)(v418 - 7) = __ROR4__(v414, 16);
                                                                                      *(_BYTE *)(v418 - 3) = __ROR4__(v416, 16);
                                                                                      *(_BYTE *)(v418 - 8) = __ROR4__(v414, 24);
                                                                                      *(_BYTE *)(v418 - 4) = __ROR4__(v416, 24);
                                                                                      ++v671;
                                                                                    }
                                                                                    while ( v671 < (unsigned __int64)v415 );
                                                                                    v385 = v666;
                                                                                    v5 = v682;
                                                                                    v309 = v666;
                                                                                    v13 = v700;
                                                                                    v384 = v655;
                                                                                    v401 = v668;
                                                                                    LOBYTE(v400) = v663;
                                                                                  }
                                                                                  *(_QWORD *)(v401 + v661) = (unsigned __int8)v400;
                                                                                  v455 = GetProcessHeap();
                                                                                  v456 = HeapAlloc(v455, 8u, 0x30u);
                                                                                  if ( v456 )
                                                                                  {
                                                                                    *(_DWORD *)v456 = v674;
                                                                                    v457 = GetProcessHeap();
                                                                                    v458 = HeapAlloc(
                                                                                             v457,
                                                                                             8u,
                                                                                             (unsigned int)v674);
                                                                                    if ( v458 )
                                                                                    {
                                                                                      v459 = (unsigned int)v674;
                                                                                      v460 = (const void *)v668;
                                                                                      *((_QWORD *)v456 + 1) = v458;
                                                                                      memcpy_0(v458, v460, v459);
                                                                                      *((_DWORD *)v456 + 4) = 160;
                                                                                      v461 = GetProcessHeap();
                                                                                      v462 = HeapAlloc(v461, 8u, 0xA0u);
                                                                                      if ( v462 )
                                                                                      {
                                                                                        *((_QWORD *)v456 + 3) = v462;
                                                                                        *v462 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                                                                                        v462[1] = xmmword_1800300F0;
                                                                                        v462[2] = xmmword_180030100;
                                                                                        v462[3] = xmmword_180030110;
                                                                                        v462[4] = xmmword_180030120;
                                                                                        v462[5] = xmmword_180030130;
                                                                                        v462[6] = xmmword_180030140;
                                                                                        v462[7] = xmmword_180030150;
                                                                                        v462[8] = xmmword_180030160;
                                                                                        v462[9] = xmmword_180030170;
                                                                                        *((_DWORD *)v456 + 8) = 8;
                                                                                        v463 = GetProcessHeap();
                                                                                        v464 = HeapAlloc(v463, 8u, 8u);
                                                                                        if ( v464 )
                                                                                        {
                                                                                          *((_QWORD *)v456 + 5) = v464;
                                                                                          *v464 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                                                                                          LODWORD(v703) = 0;
LABEL_519:
                                                                                          v385 = v456;
                                                                                          goto LABEL_601;
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                    v502 = (void *)*((_QWORD *)v456 + 1);
                                                                                    LODWORD(v703) = -1073741801;
                                                                                    v669 = v502;
                                                                                    if ( v502 )
                                                                                    {
                                                                                      v503 = GetProcessHeap();
                                                                                      HeapFree(v503, 0, v669);
                                                                                      *((_QWORD *)v456 + 1) = 0;
                                                                                    }
                                                                                    v669 = (LPVOID)*((_QWORD *)v456 + 3);
                                                                                    if ( v669 )
                                                                                    {
                                                                                      v504 = GetProcessHeap();
                                                                                      HeapFree(v504, 0, v669);
                                                                                      *((_QWORD *)v456 + 3) = 0;
                                                                                    }
                                                                                    v669 = (LPVOID)*((_QWORD *)v456 + 5);
                                                                                    if ( v669 )
                                                                                    {
                                                                                      v505 = GetProcessHeap();
                                                                                      HeapFree(v505, 0, v669);
                                                                                      *((_QWORD *)v456 + 5) = 0;
                                                                                    }
                                                                                    v506 = GetProcessHeap();
                                                                                    HeapFree(v506, 0, v456);
                                                                                    v456 = 0;
                                                                                    if ( (v703 & 0x80000000) == 0LL )
                                                                                      goto LABEL_519;
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    LODWORD(v703) = -1073741801;
                                                                                  }
LABEL_601:
                                                                                  v507 = GetProcessHeap();
                                                                                  HeapFree(v507, 0, (LPVOID)v668);
                                                                                  v308 = v703 | 0x10000000;
                                                                                  if ( (v703 & 0x80000000) != 0LL )
                                                                                    goto LABEL_431;
                                                                                  v508 = *(unsigned int *)v385;
                                                                                  LODWORD(v656) = 0;
                                                                                  LODWORD(v703) = 4;
                                                                                  v305 = RtlUIntAdd(4, v508, &v703);
                                                                                  if ( v305 >= 0 )
                                                                                  {
                                                                                    v305 = RtlUIntAdd(
                                                                                             (unsigned int)v703,
                                                                                             v509,
                                                                                             &v703);
                                                                                    if ( v305 >= 0 )
                                                                                    {
                                                                                      v305 = RtlUIntAdd(
                                                                                               (unsigned int)v703,
                                                                                               *((unsigned int *)v385 + 4),
                                                                                               &v703);
                                                                                      if ( v305 >= 0 )
                                                                                      {
                                                                                        v305 = RtlUIntAdd(
                                                                                                 (unsigned int)v703,
                                                                                                 4,
                                                                                                 &v703);
                                                                                        if ( v305 >= 0 )
                                                                                        {
                                                                                          v305 = RtlUIntAdd(
                                                                                                   (unsigned int)v703,
                                                                                                   *((unsigned int *)v385 + 8),
                                                                                                   &v703);
                                                                                          if ( v305 >= 0 )
                                                                                          {
                                                                                            v510 = v703;
                                                                                            v511 = GetProcessHeap();
                                                                                            v512 = HeapAlloc(
                                                                                                     v511,
                                                                                                     8u,
                                                                                                     v510);
                                                                                            v306 = v512;
                                                                                            if ( !v512 )
                                                                                            {
                                                                                              v309 = 0;
                                                                                              goto LABEL_432;
                                                                                            }
                                                                                            v701 = (SIZE_T)v512;
                                                                                            *v512 = *(_DWORD *)v385;
                                                                                            v305 = RtlULongLongAdd(
                                                                                                     v512,
                                                                                                     4,
                                                                                                     &v701);
                                                                                            if ( v305 >= 0 )
                                                                                            {
                                                                                              memcpy_0(
                                                                                                (void *)v701,
                                                                                                (const void *)v385[1],
                                                                                                *(unsigned int *)v385);
                                                                                              v305 = RtlULongLongAdd(v701, *(unsigned int *)v385, &v701);
                                                                                              if ( v305 >= 0 )
                                                                                              {
                                                                                                v513 = v701;
                                                                                                *(_DWORD *)v701 = *((_DWORD *)v385 + 4);
                                                                                                v305 = RtlULongLongAdd(v513, 4, &v701);
                                                                                                if ( v305 >= 0 )
                                                                                                {
                                                                                                  memcpy_0(
                                                                                                    (void *)v701,
                                                                                                    (const void *)v385[3],
                                                                                                    *((unsigned int *)v385 + 4));
                                                                                                  v305 = RtlULongLongAdd(v701, *((unsigned int *)v385 + 4), &v701);
                                                                                                  if ( v305 >= 0 )
                                                                                                  {
                                                                                                    v514 = v701;
                                                                                                    *(_DWORD *)v701 = *((_DWORD *)v385 + 8);
                                                                                                    v305 = RtlULongLongAdd(v514, 4, &v701);
                                                                                                    if ( v305 >= 0 )
                                                                                                    {
                                                                                                      memcpy_0((void *)v701, (const void *)v385[5], *((unsigned int *)v385 + 8));
                                                                                                      v305 = RtlULongLongAdd(v701, *((unsigned int *)v385 + 8), &v701);
                                                                                                      if ( v305 >= 0 )
                                                                                                      {
                                                                                                        LODWORD(v656) = v703;
                                                                                                        v646 = v306;
LABEL_428:
                                                                                                        v307 = v305 | 0x10000000;
                                                                                                        if ( v307 < 0 )
                                                                                                        {
                                                                                                          LODWORD(v701) = v307;
                                                                                                          v309 = v646;
                                                                                                          goto LABEL_432;
                                                                                                        }
                                                                                                        v687 = 8;
                                                                                                        v308 = RtlUIntAdd(8, (unsigned int)lpMem, &v687) | 0x10000000;
                                                                                                        if ( v308 >= 0 )
                                                                                                        {
                                                                                                          v516 = (v687 + 7) & 0xFFFFFFF8;
                                                                                                          if ( (unsigned int)v516 < v687 )
                                                                                                          {
                                                                                                            v308 = -1073741675;
                                                                                                            goto LABEL_430;
                                                                                                          }
                                                                                                          v686 = (v687 + 7) & 0xFFFFFFF8;
                                                                                                          v308 = RtlUIntAdd(v516, 8, &v686);
                                                                                                          if ( v308 >= 0 )
                                                                                                          {
                                                                                                            LODWORD(lpMem) = 0;
                                                                                                            v517 = (unsigned int *)v665[1];
                                                                                                            if ( v665[1] && LODWORD(v665[0]) > 1 )
                                                                                                            {
                                                                                                              v701 = v665[1];
                                                                                                              for ( nn = 0;
                                                                                                                    !nn;
                                                                                                                    nn = v546 + 1 )
                                                                                                              {
                                                                                                                v308 = RtlULongLongAdd(v517, 4, &v701);
                                                                                                                if ( v308 < 0 )
                                                                                                                  goto LABEL_430;
                                                                                                                v308 = RtlULongLongAdd(v701, v545, &v701);
                                                                                                                if ( v308 < 0 )
                                                                                                                  goto LABEL_430;
                                                                                                                v517 = (unsigned int *)v701;
                                                                                                              }
                                                                                                              v519 = *v517;
                                                                                                              v308 = RtlULongLongAdd(v517, 4, &v701);
                                                                                                              if ( v308 < 0 )
                                                                                                                goto LABEL_430;
                                                                                                              v520 = v665[1];
                                                                                                              if ( v665[1] )
                                                                                                              {
                                                                                                                if ( LODWORD(v665[0]) > 2 )
                                                                                                                {
                                                                                                                  v701 = v665[1];
                                                                                                                  for ( i1 = 0;
                                                                                                                        i1 < 2;
                                                                                                                        i1 = v548 + 1 )
                                                                                                                  {
                                                                                                                    v308 = RtlULongLongAdd(v520, 4, &v701);
                                                                                                                    if ( v308 < 0 )
                                                                                                                      goto LABEL_430;
                                                                                                                    v308 = RtlULongLongAdd(v701, v547, &v701);
                                                                                                                    if ( v308 < 0 )
                                                                                                                      goto LABEL_430;
                                                                                                                    v520 = v701;
                                                                                                                  }
                                                                                                                  v308 = RtlULongLongAdd(v520, 4, &v701);
                                                                                                                  if ( v308 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  LODWORD(lpMem) = v522;
                                                                                                                  LODWORD(v701) = 4;
                                                                                                                  v308 = RtlUIntAdd(4, v686, &v701);
                                                                                                                  if ( v308 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v308 = RtlUIntAdd((unsigned int)v701, v523, &v701);
                                                                                                                  if ( v308 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v308 = RtlUIntAdd((unsigned int)v701, v519, &v701);
                                                                                                                  if ( v308 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v308 = RtlUIntAdd((unsigned int)v701, 4, &v701);
                                                                                                                  if ( v308 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  v308 = RtlUIntAdd((unsigned int)v701, v524, &v701);
                                                                                                                  if ( v308 < 0 )
                                                                                                                    goto LABEL_430;
                                                                                                                  LODWORD(lpMem) = v701;
                                                                                                                  if ( (unsigned int)v701 > 0x400000 )
                                                                                                                  {
                                                                                                                    v308 = -2147418113;
                                                                                                                    goto LABEL_430;
                                                                                                                  }
                                                                                                                  v525 = v701;
                                                                                                                  v526 = GetProcessHeap();
                                                                                                                  v527 = HeapAlloc(v526, 8u, v525);
                                                                                                                  v528 = v527;
                                                                                                                  if ( !v527 )
                                                                                                                  {
                                                                                                                    v309 = v646;
                                                                                                                    LODWORD(v701) = -805306345;
                                                                                                                    goto LABEL_432;
                                                                                                                  }
                                                                                                                  v690 = v527;
                                                                                                                  hModule = 0;
                                                                                                                  v696 = 0;
                                                                                                                  v697 = 0;
                                                                                                                  if ( !v306 )
                                                                                                                  {
                                                                                                                    LODWORD(v701) = -2147024809;
                                                                                                                    goto LABEL_765;
                                                                                                                  }
                                                                                                                  LODWORD(v697) = (_DWORD)v656;
                                                                                                                  *(_QWORD *)((char *)&v697 + 4) = (unsigned int)lpMem;
                                                                                                                  *(_QWORD *)&v696 = v306;
                                                                                                                  *((_QWORD *)&v696 + 1) = v527;
                                                                                                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule) )
                                                                                                                  {
                                                                                                                    v529 = GetProcAddress(hModule, "NtQuerySystemInformation");
                                                                                                                    if ( v529 )
                                                                                                                    {
                                                                                                                      v530 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, _QWORD))v529)(134, &v696, 32, 0) | 0x10000000;
                                                                                                                      if ( v530 >= 0 )
                                                                                                                      {
                                                                                                                        v531 = DWORD1(v697);
LABEL_639:
                                                                                                                        LODWORD(v701) = 0;
                                                                                                                        v658 = v528;
                                                                                                                        if ( v531 < 4 )
                                                                                                                        {
                                                                                                                          LODWORD(v701) = -805306306;
                                                                                                                          v309 = v306;
                                                                                                                        }
                                                                                                                        else
                                                                                                                        {
                                                                                                                          LODWORD(v703) = *v528;
                                                                                                                          v337 = RtlULongLongAdd(v528, 4, &v658);
                                                                                                                          if ( v337 < 0 )
                                                                                                                            goto LABEL_471;
                                                                                                                          v337 = RtlUIntAdd(0, 4, &v701);
                                                                                                                          if ( v337 < 0 )
                                                                                                                          {
                                                                                                                            v666 = v385;
                                                                                                                            v341 = v532;
                                                                                                                            v655 = v384;
                                                                                                                            v647 = v306;
                                                                                                                            goto LABEL_473;
                                                                                                                          }
                                                                                                                          if ( v533 - (int)v701 < (unsigned int)v534 )
                                                                                                                          {
                                                                                                                            LODWORD(v701) = -805306306;
                                                                                                                            v309 = v306;
                                                                                                                          }
                                                                                                                          else
                                                                                                                          {
                                                                                                                            v679 = (SIZE_T)v658;
                                                                                                                            v671 = v534;
                                                                                                                            v337 = RtlULongLongAdd(v658, (unsigned int)v534, &v658);
                                                                                                                            if ( v337 < 0 )
                                                                                                                              goto LABEL_471;
                                                                                                                            v337 = RtlUIntAdd(v535, v536, &v701);
                                                                                                                            if ( v337 < 0 )
                                                                                                                              goto LABEL_471;
                                                                                                                            if ( (unsigned int)(v537 - v701) < 4 )
                                                                                                                            {
                                                                                                                              LODWORD(v701) = -805306306;
                                                                                                                              v309 = v306;
                                                                                                                            }
                                                                                                                            else
                                                                                                                            {
                                                                                                                              LODWORD(lpMem) = *(_DWORD *)v658;
                                                                                                                              v337 = RtlULongLongAdd(v658, 4, &v658);
                                                                                                                              if ( v337 < 0 )
                                                                                                                                goto LABEL_471;
                                                                                                                              v337 = RtlUIntAdd((unsigned int)v701, 4, &v701);
                                                                                                                              if ( v337 < 0 )
                                                                                                                                goto LABEL_471;
                                                                                                                              if ( v538 - (int)v701 < (unsigned int)v539 )
                                                                                                                              {
                                                                                                                                LODWORD(v701) = -805306306;
                                                                                                                                v309 = v306;
                                                                                                                              }
                                                                                                                              else
                                                                                                                              {
                                                                                                                                v674 = (SIZE_T)v658;
                                                                                                                                v668 = v539;
                                                                                                                                v337 = RtlULongLongAdd(v658, (unsigned int)v539, &v658);
                                                                                                                                if ( v337 < 0 )
                                                                                                                                  goto LABEL_471;
                                                                                                                                v337 = RtlUIntAdd((unsigned int)v701, v540, &v701);
                                                                                                                                if ( v337 < 0 )
                                                                                                                                  goto LABEL_471;
                                                                                                                                if ( (unsigned int)(v541 - v701) < 4 )
                                                                                                                                {
                                                                                                                                  LODWORD(v701) = -805306306;
                                                                                                                                  v309 = v306;
                                                                                                                                }
                                                                                                                                else
                                                                                                                                {
                                                                                                                                  v650 = *(_DWORD *)v658;
                                                                                                                                  v337 = RtlULongLongAdd(v658, 4, &v658);
                                                                                                                                  if ( v337 < 0 )
                                                                                                                                    goto LABEL_471;
                                                                                                                                  v337 = RtlUIntAdd((unsigned int)v701, 4, &v701);
                                                                                                                                  if ( v337 < 0 )
                                                                                                                                    goto LABEL_471;
                                                                                                                                  if ( v542 - (int)v701 < v543 )
                                                                                                                                  {
                                                                                                                                    LODWORD(v701) = -805306306;
                                                                                                                                    v309 = v306;
                                                                                                                                  }
                                                                                                                                  else
                                                                                                                                  {
                                                                                                                                    v337 = RtlUIntAdd((unsigned int)v701, v543, &v701);
                                                                                                                                    if ( v337 < 0 )
                                                                                                                                    {
LABEL_471:
                                                                                                                                      v647 = v306;
                                                                                                                                      v655 = v384;
                                                                                                                                      v666 = v385;
LABEL_472:
                                                                                                                                      v341 = (SIZE_T *)v657;
                                                                                                                                      goto LABEL_473;
                                                                                                                                    }
                                                                                                                                    if ( v338 == (_DWORD)v701 )
                                                                                                                                    {
                                                                                                                                      if ( (unsigned int)(v340 + v339 + (_DWORD)lpMem) + 12LL == v338 )
                                                                                                                                      {
                                                                                                                                        v549 = GetProcessHeap();
                                                                                                                                        v341 = (SIZE_T *)HeapAlloc(v549, 8u, 0x30u);
                                                                                                                                        v701 = (SIZE_T)v341;
                                                                                                                                        if ( v341 )
                                                                                                                                        {
                                                                                                                                          v655 = v384;
                                                                                                                                          v666 = v385;
                                                                                                                                          v647 = v306;
                                                                                                                                          if ( v679 )
                                                                                                                                          {
                                                                                                                                            *(_DWORD *)v341 = v703;
                                                                                                                                            v550 = GetProcessHeap();
                                                                                                                                            v551 = HeapAlloc(v550, 8u, v671);
                                                                                                                                            v552 = (_QWORD *)v701;
                                                                                                                                            if ( !v551 )
                                                                                                                                            {
LABEL_766:
                                                                                                                                              v603 = v552[1];
                                                                                                                                              v337 = -1073741801;
                                                                                                                                              lpMem = 0;
                                                                                                                                              v703 = v603;
                                                                                                                                              if ( v603 )
                                                                                                                                              {
                                                                                                                                                v604 = GetProcessHeap();
                                                                                                                                                HeapFree(v604, 0, (LPVOID)v703);
                                                                                                                                                v552 = (_QWORD *)v701;
                                                                                                                                                *(_QWORD *)(v701 + 8) = 0;
                                                                                                                                              }
                                                                                                                                              v703 = v552[3];
                                                                                                                                              if ( v703 )
                                                                                                                                              {
                                                                                                                                                v605 = GetProcessHeap();
                                                                                                                                                HeapFree(v605, 0, (LPVOID)v703);
                                                                                                                                                v552 = (_QWORD *)v701;
                                                                                                                                                *(_QWORD *)(v701 + 24) = 0;
                                                                                                                                              }
                                                                                                                                              v703 = v552[5];
                                                                                                                                              if ( v703 )
                                                                                                                                              {
                                                                                                                                                v606 = GetProcessHeap();
                                                                                                                                                HeapFree(v606, 0, (LPVOID)v703);
                                                                                                                                                *(_QWORD *)(v701 + 40) = 0;
                                                                                                                                              }
                                                                                                                                              v607 = GetProcessHeap();
                                                                                                                                              HeapFree(v607, 0, (LPVOID)v701);
                                                                                                                                              v341 = (SIZE_T *)lpMem;
                                                                                                                                              goto LABEL_678;
                                                                                                                                            }
                                                                                                                                            v553 = v671;
                                                                                                                                            v337 = 0;
                                                                                                                                            v554 = (const void *)v679;
                                                                                                                                            *(_QWORD *)(v701 + 8) = v551;
                                                                                                                                            memcpy_0(v551, v554, v553);
                                                                                                                                            v341 = (SIZE_T *)v701;
                                                                                                                                          }
                                                                                                                                          else
                                                                                                                                          {
                                                                                                                                            *(_DWORD *)v341 = 0;
                                                                                                                                            v337 = 0;
                                                                                                                                            v341[1] = 0;
                                                                                                                                          }
                                                                                                                                          if ( v674 )
                                                                                                                                          {
                                                                                                                                            *((_DWORD *)v341 + 4) = (_DWORD)lpMem;
                                                                                                                                            v555 = GetProcessHeap();
                                                                                                                                            v556 = HeapAlloc(v555, 8u, v668);
                                                                                                                                            v552 = (_QWORD *)v701;
                                                                                                                                            if ( !v556 )
                                                                                                                                            {
LABEL_889:
                                                                                                                                              v655 = v384;
                                                                                                                                              v666 = v385;
                                                                                                                                              v647 = v306;
                                                                                                                                              v701 = (SIZE_T)v552;
                                                                                                                                              goto LABEL_766;
                                                                                                                                            }
                                                                                                                                            v557 = v668;
                                                                                                                                            v337 = 0;
                                                                                                                                            v558 = (const void *)v674;
                                                                                                                                            *(_QWORD *)(v701 + 24) = v556;
                                                                                                                                            memcpy_0(v556, v558, v557);
                                                                                                                                            v341 = (SIZE_T *)v701;
                                                                                                                                          }
                                                                                                                                          else
                                                                                                                                          {
                                                                                                                                            *((_DWORD *)v341 + 4) = 0;
                                                                                                                                            v341[3] = 0;
                                                                                                                                          }
                                                                                                                                          if ( !v658 )
                                                                                                                                          {
                                                                                                                                            *((_DWORD *)v341 + 8) = 0;
                                                                                                                                            v341[5] = 0;
                                                                                                                                            goto LABEL_677;
                                                                                                                                          }
                                                                                                                                          *((_DWORD *)v341 + 8) = v650;
                                                                                                                                          lpMem = (LPVOID)v650;
                                                                                                                                          v559 = GetProcessHeap();
                                                                                                                                          v560 = HeapAlloc(v559, 8u, v650);
                                                                                                                                          v552 = (_QWORD *)v701;
                                                                                                                                          if ( v560 )
                                                                                                                                          {
                                                                                                                                            v561 = lpMem;
                                                                                                                                            v337 = 0;
                                                                                                                                            v562 = v658;
                                                                                                                                            *(_QWORD *)(v701 + 40) = v560;
                                                                                                                                            memcpy_0(v560, v562, (size_t)v561);
                                                                                                                                            v341 = (SIZE_T *)v701;
LABEL_677:
                                                                                                                                            lpMem = v341;
                                                                                                                                            v647 = v306;
                                                                                                                                            v666 = v385;
                                                                                                                                            v655 = v384;
LABEL_678:
                                                                                                                                            if ( v337 < 0 )
                                                                                                                                            {
                                                                                                                                              if ( v341 )
                                                                                                                                              {
                                                                                                                                                v701 = v341[1];
                                                                                                                                                if ( v701 )
                                                                                                                                                {
                                                                                                                                                  v563 = GetProcessHeap();
                                                                                                                                                  HeapFree(v563, 0, (LPVOID)v701);
                                                                                                                                                  v341 = (SIZE_T *)lpMem;
                                                                                                                                                  *((_QWORD *)lpMem + 1) = 0;
                                                                                                                                                }
                                                                                                                                                v701 = v341[3];
                                                                                                                                                if ( v701 )
                                                                                                                                                {
                                                                                                                                                  v564 = GetProcessHeap();
                                                                                                                                                  HeapFree(v564, 0, (LPVOID)v701);
                                                                                                                                                  v341 = (SIZE_T *)lpMem;
                                                                                                                                                  *((_QWORD *)lpMem + 3) = 0;
                                                                                                                                                }
                                                                                                                                                v701 = v341[5];
                                                                                                                                                if ( v701 )
                                                                                                                                                {
                                                                                                                                                  v565 = GetProcessHeap();
                                                                                                                                                  HeapFree(v565, 0, (LPVOID)v701);
                                                                                                                                                  *((_QWORD *)lpMem + 5) = 0;
                                                                                                                                                }
                                                                                                                                                v566 = GetProcessHeap();
                                                                                                                                                HeapFree(v566, 0, lpMem);
                                                                                                                                              }
                                                                                                                                              goto LABEL_472;
                                                                                                                                            }
                                                                                                                                            v657 = v341;
LABEL_473:
                                                                                                                                            LODWORD(v701) = v337 | 0x10000000;
                                                                                                                                            if ( v337 < 0 )
                                                                                                                                            {
LABEL_521:
                                                                                                                                              v309 = v647;
                                                                                                                                              goto LABEL_432;
                                                                                                                                            }
                                                                                                                                            if ( !v341 )
                                                                                                                                            {
                                                                                                                                              LODWORD(v701) = -805306355;
                                                                                                                                              goto LABEL_493;
                                                                                                                                            }
                                                                                                                                            v668 = v341[1];
                                                                                                                                            if ( !v668 )
                                                                                                                                            {
                                                                                                                                              LODWORD(v701) = -805306355;
                                                                                                                                              goto LABEL_493;
                                                                                                                                            }
                                                                                                                                            v342 = *(unsigned int *)v341;
                                                                                                                                            if ( !(_DWORD)v342 )
                                                                                                                                            {
                                                                                                                                              LODWORD(v701) = -805306355;
                                                                                                                                              goto LABEL_493;
                                                                                                                                            }
                                                                                                                                            v343 = v342 - 8;
                                                                                                                                            v678 = (void *)(v342 - 8);
                                                                                                                                            v344 = MemoryAlloc(v342 - 8);
                                                                                                                                            v659 = v344;
                                                                                                                                            v346 = v344;
                                                                                                                                            if ( !v344 )
                                                                                                                                            {
LABEL_492:
                                                                                                                                              LODWORD(v701) = -805306367;
LABEL_493:
                                                                                                                                              v309 = v647;
                                                                                                                                              goto LABEL_432;
                                                                                                                                            }
                                                                                                                                            v347 = (unsigned __int8 *)v668;
                                                                                                                                            LOBYTE(v345) = 0;
                                                                                                                                            v663 = v345;
                                                                                                                                            v674 = 0x7F1137FAB69605ELL;
                                                                                                                                            v348 = v344;
                                                                                                                                            v671 = (SIZE_T)v344;
                                                                                                                                            v349 = v343 & 7;
                                                                                                                                            if ( (v343 & 7) != 0 )
                                                                                                                                            {
                                                                                                                                              v634 = 0;
                                                                                                                                              v635 = 0;
                                                                                                                                              v636 = 0;
                                                                                                                                              LODWORD(v701) = 0;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v637 = *v347;
                                                                                                                                                v638 = 8 * v634;
                                                                                                                                                ++v347;
                                                                                                                                                if ( v634 >= 4 )
                                                                                                                                                  v635 |= v637 << (56 - v638);
                                                                                                                                                else
                                                                                                                                                  v636 |= v637 << (24 - v638);
                                                                                                                                                v634 = v701 + 1;
                                                                                                                                                LODWORD(v701) = v634;
                                                                                                                                              }
                                                                                                                                              while ( (int)v634 < (int)v349 );
                                                                                                                                              v5 = v682;
                                                                                                                                              LODWORD(v703) = v635;
                                                                                                                                              v639 = v636 ^ 0x92F65A5;
                                                                                                                                              LODWORD(lpMem) = v636;
                                                                                                                                              v640 = v635 ^ 0x699A899C;
                                                                                                                                              LODWORD(v701) = v636 ^ 0x92F65A5;
                                                                                                                                              v641 = v635 ^ 0x699A899C;
                                                                                                                                              v642 = 0;
                                                                                                                                              v647 = v306;
                                                                                                                                              v666 = v385;
                                                                                                                                              v655 = v384;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v669 = v348 + 1;
                                                                                                                                                if ( v642 >= 4 )
                                                                                                                                                {
                                                                                                                                                  v640 = __ROR4__(v640, 24);
                                                                                                                                                  v643 = v640;
                                                                                                                                                }
                                                                                                                                                else
                                                                                                                                                {
                                                                                                                                                  v639 = __ROR4__(v639, 24);
                                                                                                                                                  v643 = v639;
                                                                                                                                                }
                                                                                                                                                *v348 = v643;
                                                                                                                                                ++v642;
                                                                                                                                                v348 = v669;
                                                                                                                                              }
                                                                                                                                              while ( v642 < (int)v349 );
                                                                                                                                              v671 = (SIZE_T)v669;
                                                                                                                                              if ( v349 <= 4 )
                                                                                                                                              {
                                                                                                                                                v350 = 0;
                                                                                                                                                if ( v349 < 4 )
                                                                                                                                                  LODWORD(v701) = (unsigned int)v701 >> (8 * (4 - v349)) << (8 * (4 - v349));
                                                                                                                                              }
                                                                                                                                              else
                                                                                                                                              {
                                                                                                                                                v350 = v641 >> (8 * (8 - v349)) << (8 * (8 - v349));
                                                                                                                                              }
                                                                                                                                              v346 = v659;
                                                                                                                                              LOBYTE(v345) = v663;
                                                                                                                                            }
                                                                                                                                            else
                                                                                                                                            {
                                                                                                                                              v350 = 0;
                                                                                                                                              LODWORD(lpMem) = v343 & 7;
                                                                                                                                              LODWORD(v701) = 0;
                                                                                                                                              LODWORD(v703) = -1;
                                                                                                                                            }
                                                                                                                                            v351 = v343 >> 3;
                                                                                                                                            if ( v343 >> 3 )
                                                                                                                                            {
                                                                                                                                              v352 = HIDWORD(v674);
                                                                                                                                              v353 = v671;
                                                                                                                                              LODWORD(v677) = HIDWORD(v674) ^ 0xAB69605E;
                                                                                                                                              v354 = HIWORD(HIDWORD(v674));
                                                                                                                                              v355 = WORD2(v674);
                                                                                                                                              v356 = 24670;
                                                                                                                                              LODWORD(v675) = 43881;
                                                                                                                                              v679 = 0;
                                                                                                                                              LODWORD(v656) = WORD2(v674);
                                                                                                                                              v661 = 24670;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v357 = v347[3] | ((v347[2] | (((*v347 << 8) | v347[1]) << 8)) << 8);
                                                                                                                                                v358 = v347[7] | ((v347[6] | ((v347[5] | (v347[4] << 8)) << 8)) << 8);
                                                                                                                                                v669 = v347 + 8;
                                                                                                                                                v359 = v350 ^ v358 ^ (unsigned int)v677 ^ v701 ^ v357;
                                                                                                                                                v360 = v701 ^ v357 ^ (__ROR4__(v359, 22) + v355 * __ROR4__(v359 + 1419157410, 27));
                                                                                                                                                v361 = v359 ^ (43881 * __ROR4__(v352 + v360, 9) - __ROR4__(v360, 30));
                                                                                                                                                v362 = v360 ^ (v356 * (v361 - v355) - (v361 >> 13));
                                                                                                                                                v363 = v361 ^ (v354 * __ROR4__(v362 ^ (unsigned int)v675, 26) - __ROR4__(v362, 30));
                                                                                                                                                v364 = v362 ^ (v352 - (v363 ^ 0xAB69605E));
                                                                                                                                                v365 = v363 ^ (43881 * (v364 ^ v355)) ^ __ROR4__(v364, 6);
                                                                                                                                                v366 = v364 ^ (__ROR4__(v365, 30) + v661 * __ROR4__(v365 + v352, 15));
                                                                                                                                                v367 = v365 ^ (v354 * __ROR4__(v366 + 1419157410, 14) - __ROR4__(v366, 24));
                                                                                                                                                v368 = v366 ^ __ROR4__(v367, 10) ^ ((_DWORD)v656 * __ROR4__(v367 ^ 0xAB69605E, 12));
                                                                                                                                                v369 = v367 ^ (v368 >> 10) ^ (43881 * (v354 ^ v368));
                                                                                                                                                v355 = (int)v656;
                                                                                                                                                v370 = v368 ^ (v354 * (v661 + __ROR4__(~v369, 5)));
                                                                                                                                                v371 = v369 ^ (v370 - v354) ^ 0xAB69605E;
                                                                                                                                                v372 = v370 ^ ((v371 >> 2) + (_DWORD)v656 * __ROR4__(v354 ^ v371, 30));
                                                                                                                                                v373 = v371 ^ (__ROR4__(v372, 25) + 43881 * __ROR4__(v372 - v352, 6));
                                                                                                                                                v374 = v372 ^ (v661 * (v373 ^ (unsigned int)v656) + __ROR4__(v373, 9));
                                                                                                                                                v375 = v373 ^ (__ROR4__(v374, 25) + v354 * __ROR4__((unsigned int)v675 ^ v374, 27));
                                                                                                                                                v376 = v374 ^ v375 ^ (unsigned int)v677;
                                                                                                                                                v377 = v375 ^ ((_DWORD)v656 * (__ROR4__(v376, 3) - 43881));
                                                                                                                                                v378 = v376 ^ (v661 * __ROR4__(v377 - v352, 1) - __ROR4__(v377, 6));
                                                                                                                                                v353 += 8LL;
                                                                                                                                                v379 = v377 ^ (__ROR4__(v378, 18) + v354 * __ROR4__(v378 - 1419157410, 29));
                                                                                                                                                v380 = v378 ^ ((_DWORD)v656 * __ROR4__(v379 - 1419157410, 17) - __ROR4__(v379, 14));
                                                                                                                                                v356 = v661;
                                                                                                                                                v381 = v379 ^ (v380 >> 3) ^ (43881 * (v661 ^ v380));
                                                                                                                                                v350 = v703 ^ v381;
                                                                                                                                                LODWORD(v703) = v358;
                                                                                                                                                v382 = v380 ^ __ROR4__(v381, 30) ^ (v661 * __ROR4__(v352 ^ v381, 28));
                                                                                                                                                v347 = (unsigned __int8 *)v669;
                                                                                                                                                v383 = (unsigned int)lpMem ^ v382;
                                                                                                                                                *(_BYTE *)(v353 - 5) = v383;
                                                                                                                                                *(_BYTE *)(v353 - 1) = v350;
                                                                                                                                                *(_BYTE *)(v353 - 6) = __ROR4__(v383, 8);
                                                                                                                                                *(_BYTE *)(v353 - 2) = __ROR4__(v350, 8);
                                                                                                                                                *(_BYTE *)(v353 - 7) = __ROR4__(v383, 16);
                                                                                                                                                *(_BYTE *)(v353 - 3) = __ROR4__(v350, 16);
                                                                                                                                                *(_BYTE *)(v353 - 8) = __ROR4__(v383, 24);
                                                                                                                                                *(_BYTE *)(v353 - 4) = __ROR4__(v350, 24);
                                                                                                                                                LODWORD(v701) = v383;
                                                                                                                                                LODWORD(lpMem) = v357;
                                                                                                                                                ++v679;
                                                                                                                                              }
                                                                                                                                              while ( v679 < v351 );
                                                                                                                                              v5 = v682;
                                                                                                                                              v13 = v700;
                                                                                                                                              v384 = v655;
                                                                                                                                              v385 = v666;
                                                                                                                                              v343 = (unsigned __int64)v678;
                                                                                                                                              v346 = v659;
                                                                                                                                              LOBYTE(v345) = v663;
                                                                                                                                            }
                                                                                                                                            if ( v343 )
                                                                                                                                            {
                                                                                                                                              v386 = 0;
                                                                                                                                              if ( v343 < 0x20 )
                                                                                                                                                goto LABEL_968;
                                                                                                                                              v387 = 0;
                                                                                                                                              v388 = 0;
                                                                                                                                              do
                                                                                                                                              {
                                                                                                                                                v387 = _mm_xor_ps(v387, (__m128)_mm_loadu_si128((const __m128i *)&v346[v386]));
                                                                                                                                                v389 = (__m128)_mm_loadu_si128((const __m128i *)&v346[v386 + 16]);
                                                                                                                                                v386 += 32LL;
                                                                                                                                                v390 = _mm_xor_ps(v389, v388);
                                                                                                                                                v388 = v390;
                                                                                                                                              }
                                                                                                                                              while ( v386 < (v343 & 0xFFFFFFFFFFFFFFE0uLL) );
                                                                                                                                              v391 = _mm_xor_ps(v387, v390);
                                                                                                                                              v392 = _mm_xor_ps(v391, (__m128)_mm_srli_si128((__m128i)v391, 8));
                                                                                                                                              v393 = _mm_xor_ps(v392, (__m128)_mm_srli_si128((__m128i)v392, 4));
                                                                                                                                              v394 = _mm_xor_ps(v393, (__m128)_mm_srli_si128((__m128i)v393, 2));
                                                                                                                                              LOBYTE(v345) = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v394, (__m128)_mm_srli_si128((__m128i)v394, 1)));
                                                                                                                                              if ( v386 < v343 )
                                                                                                                                              {
LABEL_968:
                                                                                                                                                do
                                                                                                                                                  LOBYTE(v345) = v346[v386++] ^ v345;
                                                                                                                                                while ( v386 < v343 );
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                            if ( (unsigned __int8)v345 != *(_QWORD *)(v343 + v668) )
                                                                                                                                            {
                                                                                                                                              v395 = GetProcessHeap();
                                                                                                                                              HeapFree(v395, 0, v659);
                                                                                                                                              goto LABEL_492;
                                                                                                                                            }
                                                                                                                                            Size = (size_t)v346;
                                                                                                                                            LODWORD(v700) = 0;
                                                                                                                                            v701 = (SIZE_T)v346;
                                                                                                                                            if ( (unsigned int)v343 >= 4 )
                                                                                                                                            {
                                                                                                                                              v567 = RtlULongLongAdd(v346, 4, &v701);
                                                                                                                                              if ( v567 < 0 )
                                                                                                                                                goto LABEL_520;
                                                                                                                                              v567 = RtlUIntAdd(0, 4, &v700);
                                                                                                                                              if ( v567 < 0 )
                                                                                                                                                goto LABEL_520;
                                                                                                                                              if ( (unsigned int)(v343 - v700) >= 4 )
                                                                                                                                              {
                                                                                                                                                v567 = RtlULongLongAdd(v701, 4, &v701);
                                                                                                                                                if ( v567 < 0 )
                                                                                                                                                  goto LABEL_520;
                                                                                                                                                v567 = RtlUIntAdd(v568, 4, &v700);
                                                                                                                                                if ( v567 < 0 )
                                                                                                                                                  goto LABEL_520;
                                                                                                                                                if ( (int)v343 - (int)v700 >= v569 )
                                                                                                                                                {
                                                                                                                                                  v567 = RtlUIntAdd((unsigned int)v700, v569, &v700);
                                                                                                                                                  if ( v567 < 0 )
                                                                                                                                                  {
LABEL_520:
                                                                                                                                                    LODWORD(v701) = v567 | 0x10000000;
                                                                                                                                                    goto LABEL_521;
                                                                                                                                                  }
                                                                                                                                                  v572 = (const void *)v701;
                                                                                                                                                  v679 = (unsigned int)v571;
                                                                                                                                                  if ( (unsigned __int64)v570 + (unsigned int)v343 >= v701 + v571 && (unsigned __int64)v570 + (unsigned int)v343 - (unsigned int)v571 - v701 < 8 )
                                                                                                                                                  {
                                                                                                                                                    v573 = 0;
                                                                                                                                                    LODWORD(v700) = *v570;
                                                                                                                                                    v574 = 0;
                                                                                                                                                    lpMem = 0;
                                                                                                                                                    v703 = 0;
                                                                                                                                                    v671 = 0;
                                                                                                                                                    if ( v701 )
                                                                                                                                                    {
                                                                                                                                                      LODWORD(v701) = RtlULongLongAdd(v701, (unsigned int)v571, &lpMem);
                                                                                                                                                      if ( (v701 & 0x80000000) == 0LL )
                                                                                                                                                      {
                                                                                                                                                        v577 = lpMem;
                                                                                                                                                        while ( 1 )
                                                                                                                                                        {
                                                                                                                                                          if ( v575 >= (unsigned __int64)v577 )
                                                                                                                                                          {
                                                                                                                                                            if ( (LPVOID)v575 == v577 )
                                                                                                                                                              goto LABEL_711;
LABEL_911:
                                                                                                                                                            v567 = -1073741811;
                                                                                                                                                            goto LABEL_520;
                                                                                                                                                          }
                                                                                                                                                          LODWORD(v701) = RtlULongLongAdd(v575, 4, &v703);
                                                                                                                                                          if ( (v701 & 0x80000000) != 0LL )
                                                                                                                                                            break;
                                                                                                                                                          if ( v703 > v579 )
                                                                                                                                                            goto LABEL_911;
                                                                                                                                                          v580 = *v578;
                                                                                                                                                          LODWORD(v701) = 0;
                                                                                                                                                          v567 = RtlUIntAdd(4, v580, &v701);
                                                                                                                                                          if ( v567 < 0 )
                                                                                                                                                            goto LABEL_520;
                                                                                                                                                          LODWORD(v701) = RtlULongLongAdd(v581, (unsigned int)v701, &v671);
                                                                                                                                                          if ( (v701 & 0x80000000) != 0LL )
                                                                                                                                                            break;
                                                                                                                                                          v575 = v671;
                                                                                                                                                          if ( v671 > (unsigned __int64)v577 )
                                                                                                                                                            goto LABEL_911;
                                                                                                                                                          ++v574;
                                                                                                                                                        }
                                                                                                                                                        v576 = v700;
                                                                                                                                                      }
                                                                                                                                                      v583 = v667;
                                                                                                                                                    }
                                                                                                                                                    else
                                                                                                                                                    {
                                                                                                                                                      LODWORD(v701) = 0;
LABEL_711:
                                                                                                                                                      if ( (_DWORD)v571 )
                                                                                                                                                      {
                                                                                                                                                        v582 = GetProcessHeap();
                                                                                                                                                        v573 = HeapAlloc(v582, 8u, v679);
                                                                                                                                                        if ( !v573 )
                                                                                                                                                        {
                                                                                                                                                          v567 = -1073741801;
                                                                                                                                                          goto LABEL_520;
                                                                                                                                                        }
                                                                                                                                                        LODWORD(v701) = 0;
                                                                                                                                                      }
                                                                                                                                                      if ( v572 )
                                                                                                                                                        memcpy_0(v573, v572, v679);
                                                                                                                                                      v576 = v700;
                                                                                                                                                      v583 = v574;
                                                                                                                                                      v667 = v574;
                                                                                                                                                      dwBytesa = v573;
                                                                                                                                                    }
                                                                                                                                                    v567 = v701;
                                                                                                                                                    if ( (v701 & 0x80000000) != 0LL || v576 == v583 )
                                                                                                                                                      goto LABEL_520;
                                                                                                                                                  }
                                                                                                                                                }
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                            v567 = -1073741762;
                                                                                                                                            goto LABEL_520;
                                                                                                                                          }
                                                                                                                                          goto LABEL_889;
                                                                                                                                        }
                                                                                                                                        LODWORD(v701) = -805306345;
                                                                                                                                        v309 = v306;
                                                                                                                                      }
                                                                                                                                      else
                                                                                                                                      {
                                                                                                                                        LODWORD(v701) = -805306306;
                                                                                                                                        v309 = v306;
                                                                                                                                      }
                                                                                                                                    }
                                                                                                                                    else
                                                                                                                                    {
                                                                                                                                      LODWORD(v701) = -805306306;
                                                                                                                                      v309 = v306;
                                                                                                                                    }
                                                                                                                                  }
                                                                                                                                }
                                                                                                                              }
                                                                                                                            }
                                                                                                                          }
                                                                                                                        }
LABEL_432:
                                                                                                                        if ( !v384 )
                                                                                                                        {
LABEL_434:
                                                                                                                          if ( v385 )
                                                                                                                          {
                                                                                                                            v311 = (void *)v385[1];
                                                                                                                            if ( v311 )
                                                                                                                            {
                                                                                                                              v312 = GetProcessHeap();
                                                                                                                              HeapFree(v312, 0, v311);
                                                                                                                              v385[1] = 0;
                                                                                                                            }
                                                                                                                            v313 = (void *)v385[3];
                                                                                                                            if ( v313 )
                                                                                                                            {
                                                                                                                              v314 = GetProcessHeap();
                                                                                                                              HeapFree(v314, 0, v313);
                                                                                                                              v385[3] = 0;
                                                                                                                            }
                                                                                                                            v315 = (void *)v385[5];
                                                                                                                            if ( v315 )
                                                                                                                            {
                                                                                                                              v316 = GetProcessHeap();
                                                                                                                              HeapFree(v316, 0, v315);
                                                                                                                              v385[5] = 0;
                                                                                                                            }
                                                                                                                            v317 = GetProcessHeap();
                                                                                                                            HeapFree(v317, 0, v385);
                                                                                                                          }
                                                                                                                          if ( v309 )
                                                                                                                          {
                                                                                                                            v318 = GetProcessHeap();
                                                                                                                            HeapFree(v318, 0, v309);
                                                                                                                          }
                                                                                                                          v319 = v690;
                                                                                                                          if ( v690 )
                                                                                                                          {
                                                                                                                            v320 = GetProcessHeap();
                                                                                                                            HeapFree(v320, 0, v319);
                                                                                                                          }
                                                                                                                          v321 = v657;
                                                                                                                          if ( v657 )
                                                                                                                          {
                                                                                                                            v322 = (void *)*((_QWORD *)v657 + 1);
                                                                                                                            if ( v322 )
                                                                                                                            {
                                                                                                                              v323 = GetProcessHeap();
                                                                                                                              HeapFree(v323, 0, v322);
                                                                                                                              v321[1] = 0;
                                                                                                                            }
                                                                                                                            v324 = (void *)v321[3];
                                                                                                                            if ( v324 )
                                                                                                                            {
                                                                                                                              v325 = GetProcessHeap();
                                                                                                                              HeapFree(v325, 0, v324);
                                                                                                                              v321[3] = 0;
                                                                                                                            }
                                                                                                                            v326 = (void *)v321[5];
                                                                                                                            if ( v326 )
                                                                                                                            {
                                                                                                                              v327 = GetProcessHeap();
                                                                                                                              HeapFree(v327, 0, v326);
                                                                                                                              v321[5] = 0;
                                                                                                                            }
                                                                                                                            v328 = GetProcessHeap();
                                                                                                                            HeapFree(v328, 0, v321);
                                                                                                                          }
                                                                                                                          v329 = (void *)Size;
                                                                                                                          if ( Size )
                                                                                                                          {
                                                                                                                            v330 = GetProcessHeap();
                                                                                                                            HeapFree(v330, 0, v329);
                                                                                                                          }
                                                                                                                          v304 = dwBytesa;
                                                                                                                          if ( (v701 & 0x80000000) == 0LL && v667 )
                                                                                                                          {
                                                                                                                            if ( !dwBytesa )
                                                                                                                            {
                                                                                                                              v299 = v660;
                                                                                                                              v298 = v664;
                                                                                                                              goto LABEL_461;
                                                                                                                            }
                                                                                                                            v700 = (SIZE_T)dwBytesa;
                                                                                                                            if ( (int)RtlULongLongAdd(dwBytesa, 4, &v700) >= 0 )
                                                                                                                            {
                                                                                                                              v584 = (int *)v700;
                                                                                                                              if ( !*dwBytesa )
                                                                                                                                v584 = 0;
                                                                                                                              if ( *dwBytesa == 4 && *v584 >= 0 && v331 > 1 )
                                                                                                                              {
                                                                                                                                v585 = (SIZE_T)dwBytesa;
                                                                                                                                v586 = 0;
                                                                                                                                v700 = (SIZE_T)dwBytesa;
                                                                                                                                while ( !v586 )
                                                                                                                                {
                                                                                                                                  if ( (int)RtlULongLongAdd(v585, 4, &v700) < 0 || (int)RtlULongLongAdd(v700, v587, &v700) < 0 )
                                                                                                                                    goto LABEL_460;
                                                                                                                                  v585 = v700;
                                                                                                                                  v586 = v588 + 1;
                                                                                                                                }
                                                                                                                                RtlULongLongAdd(v585, 4, &v700);
                                                                                                                                v299 = v660;
                                                                                                                                v298 = v664;
                                                                                                                                goto LABEL_461;
                                                                                                                              }
                                                                                                                            }
                                                                                                                          }
LABEL_460:
                                                                                                                          v299 = v660;
                                                                                                                          v298 = v664;
LABEL_461:
                                                                                                                          v332 = (void *)v665[1];
                                                                                                                          v665[0] = 0;
                                                                                                                          if ( v665[1] )
                                                                                                                          {
                                                                                                                            v333 = GetProcessHeap();
                                                                                                                            HeapFree(v333, 0, v332);
                                                                                                                            v665[1] = 0;
                                                                                                                          }
                                                                                                                          if ( v304 )
                                                                                                                          {
                                                                                                                            v334 = GetProcessHeap();
                                                                                                                            HeapFree(v334, 0, v304);
                                                                                                                          }
                                                                                                                          if ( v298 )
                                                                                                                          {
                                                                                                                            v335 = GetProcessHeap();
                                                                                                                            HeapFree(v335, 0, v298);
                                                                                                                          }
                                                                                                                          if ( v299 )
                                                                                                                          {
                                                                                                                            v336 = GetProcessHeap();
                                                                                                                            HeapFree(v336, 0, v299);
                                                                                                                          }
LABEL_24:
                                                                                                                          v14 = v685;
                                                                                                                          v4 = (int *)v5;
LABEL_25:
                                                                                                                          if ( v13 >= 0 )
                                                                                                                          {
                                                                                                                            if ( v14 == 4 )
                                                                                                                            {
                                                                                                                              v13 = 0;
                                                                                                                              if ( v4 )
                                                                                                                                v589 = v4;
                                                                                                                              else
                                                                                                                                v589 = 0;
                                                                                                                              v290 = *v589;
LABEL_392:
                                                                                                                              if ( v4 )
                                                                                                                                LocalFree(v4);
                                                                                                                              if ( v13 >= 0 && v290 )
                                                                                                                              {
                                                                                                                                v291 = hSCObject;
                                                                                                                              }
                                                                                                                              else
                                                                                                                              {
                                                                                                                                v291 = hSCObject;
                                                                                                                                v292 = InitializeService(hSCObject, "SSTPSVC", 0x78u, &v680);
                                                                                                                                v1 = v292;
                                                                                                                                if ( v292 )
                                                                                                                                {
                                                                                                                                  if ( g_dwTraceId != -1 )
                                                                                                                                    TracePrintfExA(g_dwTraceId, 0xCu, "SSTP service initialization failed, error = %d", v292);
                                                                                                                                  v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                                                                                    goto LABEL_321;
                                                                                                                                  v295 = 82;
                                                                                                                                  goto LABEL_928;
                                                                                                                                }
                                                                                                                              }
                                                                                                                              v293 = InitializeService(v291, "RASMAN", 0x78u, &v680);
                                                                                                                              v1 = v293;
                                                                                                                              if ( !v293 )
                                                                                                                              {
                                                                                                                                if ( v680 )
                                                                                                                                {
                                                                                                                                  if ( g_dwTraceId != -1 )
                                                                                                                                    TracePrintfExA(g_dwTraceId, 0xCu, "Rasman service was started by RasInitialize");
                                                                                                                                  if ( (unsigned int)IsModemPresent() )
                                                                                                                                  {
                                                                                                                                    v644 = InitializeService(v291, "TAPISRV", 5u, &v680);
                                                                                                                                    v1 = v644;
                                                                                                                                    if ( v644 )
                                                                                                                                    {
                                                                                                                                      if ( g_dwTraceId != -1 )
                                                                                                                                        TracePrintfExA(g_dwTraceId, 0xCu, "TapiSrv service initialization failed, error = %d", v644);
                                                                                                                                      v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                                                                                        goto LABEL_321;
                                                                                                                                      v295 = 84;
                                                                                                                                      goto LABEL_928;
                                                                                                                                    }
                                                                                                                                    if ( v680 )
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
                                                                                                                                  v256 = RasRpcConnect(0, &Binding);
                                                                                                                                  LeaveCriticalSection(&g_RasCriticalSection);
                                                                                                                                  if ( v256 )
                                                                                                                                  {
                                                                                                                                    if ( g_dwTraceId != -1 )
                                                                                                                                      TracePrintfExA(g_dwTraceId, 0xCu, "RasInitialize: Failed to connect to local server. %d\n", v256);
                                                                                                                                    v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                                                                                                    {
                                                                                                                                      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v256);
                                                                                                                                      v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    }
                                                                                                                                    v1 = 711;
                                                                                                                                    if ( v294 == &WPP_GLOBAL_Control || (*((_BYTE *)v294 + 28) & 0x40) == 0 || *((_BYTE *)v294 + 25) < 2u )
                                                                                                                                      goto LABEL_321;
                                                                                                                                    v295 = 86;
                                                                                                                                    goto LABEL_928;
                                                                                                                                  }
                                                                                                                                  v257 = RasReferenceRasman(1);
                                                                                                                                  v1 = v257;
                                                                                                                                  if ( v257 )
                                                                                                                                  {
                                                                                                                                    if ( g_dwTraceId != -1 )
                                                                                                                                      TracePrintfExA(g_dwTraceId, 0xCu, "RasInitialize: failed to reference rasman. %d\n", v257);
                                                                                                                                    v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                                                                                                    {
                                                                                                                                      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
                                                                                                                                      v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                    }
                                                                                                                                    v1 = 711;
                                                                                                                                    if ( v294 == &WPP_GLOBAL_Control || (*((_BYTE *)v294 + 28) & 0x40) == 0 || *((_BYTE *)v294 + 25) < 2u )
                                                                                                                                      goto LABEL_321;
                                                                                                                                    v295 = 88;
                                                                                                                                    goto LABEL_928;
                                                                                                                                  }
                                                                                                                                }
                                                                                                                                g_fRasInitialized = 1;
LABEL_321:
                                                                                                                                CloseServiceHandle(v291);
LABEL_322:
                                                                                                                                v2 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                                goto LABEL_323;
                                                                                                                              }
                                                                                                                              if ( g_dwTraceId != -1 )
                                                                                                                                TracePrintfExA(g_dwTraceId, 0xCu, "RASMAN service initialization failed, error = %d", v293);
                                                                                                                              v294 = (PVOID *)WPP_GLOBAL_Control;
                                                                                                                              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                                                                                                goto LABEL_321;
                                                                                                                              v295 = 83;
LABEL_928:
                                                                                                                              WPP_SF_d(v294[2], v295, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
                                                                                                                              goto LABEL_321;
                                                                                                                            }
                                                                                                                            v13 = -1073418210;
LABEL_391:
                                                                                                                            v290 = v683;
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
                                                                                                                        v310 = GetProcessHeap();
                                                                                                                        HeapFree(v310, 0, v384);
                                                                                                                        goto LABEL_434;
                                                                                                                      }
                                                                                                                      goto LABEL_657;
                                                                                                                    }
                                                                                                                    v530 = GetLastError();
                                                                                                                    v544 = v530 < 0;
                                                                                                                    if ( v530 <= 0 )
                                                                                                                    {
LABEL_656:
                                                                                                                      if ( !v544 )
                                                                                                                      {
                                                                                                                        LODWORD(v701) = -2147467259;
LABEL_764:
                                                                                                                        v646 = v306;
LABEL_765:
                                                                                                                        v309 = v646;
                                                                                                                        goto LABEL_432;
                                                                                                                      }
LABEL_657:
                                                                                                                      v531 = (unsigned int)lpMem;
                                                                                                                      if ( v530 == -805306333 )
                                                                                                                      {
                                                                                                                        LODWORD(v701) = -2147024774;
                                                                                                                        v309 = v306;
                                                                                                                        goto LABEL_432;
                                                                                                                      }
                                                                                                                      if ( v530 >= 0 )
                                                                                                                        goto LABEL_639;
                                                                                                                      LODWORD(v701) = v530;
                                                                                                                      goto LABEL_764;
                                                                                                                    }
                                                                                                                  }
                                                                                                                  else
                                                                                                                  {
                                                                                                                    v530 = GetLastError();
                                                                                                                    v544 = v530 < 0;
                                                                                                                    if ( v530 <= 0 )
                                                                                                                      goto LABEL_656;
                                                                                                                  }
                                                                                                                  v530 = (unsigned __int16)v530 | 0x80070000;
                                                                                                                  v544 = v530 < 0;
                                                                                                                  goto LABEL_656;
                                                                                                                }
                                                                                                              }
                                                                                                            }
                                                                                                            v308 = -1073741811;
                                                                                                          }
                                                                                                        }
LABEL_430:
                                                                                                        v309 = v646;
LABEL_431:
                                                                                                        LODWORD(v701) = v308;
                                                                                                        goto LABEL_432;
                                                                                                      }
                                                                                                    }
                                                                                                  }
                                                                                                }
                                                                                              }
                                                                                            }
                                                                                            v515 = GetProcessHeap();
                                                                                            HeapFree(v515, 0, v306);
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                  v306 = 0;
                                                                                  goto LABEL_428;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                LODWORD(v675) = v630 >> (8 * (8 - v413)) << (8 * (8 - v413));
                                                                              }
                                                                              v414 = v703;
                                                                              goto LABEL_510;
                                                                            }
                                                                            v299 = v660;
                                                                            v298 = v664;
LABEL_424:
                                                                            v304 = 0;
                                                                            goto LABEL_461;
                                                                          }
                                                                          v497 = (v676 + 7) & 0xFFFFFFF8;
                                                                          if ( v497 >= v676 )
                                                                          {
                                                                            v676 = (v676 + 7) & 0xFFFFFFF8;
                                                                            v498 = v497;
                                                                            v499 = GetProcessHeap();
                                                                            v500 = (char *)HeapAlloc(v499, 8u, v498);
                                                                            v501 = v500;
                                                                            if ( v500 )
                                                                            {
                                                                              v659 = v500;
                                                                              *(_DWORD *)v500 = v665[0];
                                                                              LODWORD(lpMem) = RtlULongLongAdd(
                                                                                                 v500,
                                                                                                 4,
                                                                                                 &v659);
                                                                              if ( (int)lpMem >= 0
                                                                                && (v396 = v659,
                                                                                    *(_DWORD *)v659 = HIDWORD(v665[0]),
                                                                                    LODWORD(lpMem) = RtlULongLongAdd(v396, 4, &v659),
                                                                                    (int)lpMem >= 0) )
                                                                              {
                                                                                *(_QWORD *)&v501[v676 - 8] = Size;
                                                                                memcpy_0(
                                                                                  v659,
                                                                                  (const void *)v665[1],
                                                                                  HIDWORD(v665[0]));
                                                                                v398 = v676;
                                                                                v384 = v501;
                                                                                v661 = v676;
                                                                                v655 = v501;
                                                                              }
                                                                              else
                                                                              {
                                                                                v397 = GetProcessHeap();
                                                                                HeapFree(v397, 0, v501);
                                                                                v398 = 0;
                                                                              }
                                                                              v399 = (int)lpMem;
                                                                              v309 = 0;
                                                                              goto LABEL_497;
                                                                            }
                                                                          }
                                                                          v299 = v660;
                                                                        }
                                                                      }
LABEL_423:
                                                                      v298 = v302;
                                                                      goto LABEL_424;
                                                                    }
                                                                  }
LABEL_20:
                                                                  v13 = -1073741675;
LABEL_21:
                                                                  LODWORD(v700) = v13;
                                                                  goto LABEL_79;
                                                                }
                                                                goto LABEL_34;
                                                              }
                                                              v46 = GetProcessHeap();
                                                              v47 = v666;
LABEL_134:
                                                              HeapFree(v46, 0, v47);
                                                              goto LABEL_135;
                                                            }
LABEL_111:
                                                            v49 = GetProcessHeap();
                                                            HeapFree(v49, 0, v648);
                                                            goto LABEL_112;
                                                          }
                                                          v269 = GetProcessHeap();
                                                          v678 = HeapAlloc(v269, 8u, v674);
                                                          v266 = v678;
                                                          if ( v678 )
                                                          {
                                                            v261 = v700;
                                                            v262 = 0;
                                                            v259 = (_DWORD *)v668;
                                                            goto LABEL_348;
                                                          }
                                                          v258 = -1073741801;
LABEL_332:
                                                          v48 = v648;
                                                          v13 = v258 | 0x10000000;
                                                          LODWORD(v700) = v13;
                                                          goto LABEL_110;
                                                        }
                                                        if ( v265 >= (unsigned __int64)v259 )
                                                        {
                                                          v267 = v653;
                                                          v262 = 0;
                                                          v268 = v645;
                                                          while ( 1 )
                                                          {
                                                            v263 = v259;
                                                            if ( (unsigned __int64)v259 >= v265 )
                                                              break;
                                                            if ( v259 + 1 < v259 )
                                                              goto LABEL_331;
                                                            if ( (unsigned __int64)(v259 + 1) > v265 )
                                                              goto LABEL_842;
                                                            if ( *v259 >= 0xFFFFFFFC )
                                                              goto LABEL_331;
                                                            v48 = v648;
                                                            v259 = (_DWORD *)((char *)v259 + (unsigned int)(*v259 + 4));
                                                            if ( v259 < v263 )
                                                              goto LABEL_340;
                                                            v260 = v655;
                                                            v653 = v267;
                                                            v645 = v268;
                                                            if ( (unsigned __int64)v259 > v265 )
                                                            {
                                                              v262 = -1073741811;
                                                              goto LABEL_841;
                                                            }
                                                            LODWORD(v700) = ++v261;
                                                            v262 = 0;
                                                          }
                                                          if ( v259 == (_DWORD *)v265 )
                                                          {
                                                            v259 = (_DWORD *)v668;
                                                            v264 = (unsigned int *)v666;
                                                            goto LABEL_347;
                                                          }
LABEL_842:
                                                          v258 = -1073741811;
                                                          goto LABEL_332;
                                                        }
LABEL_331:
                                                        v258 = -1073741675;
                                                        goto LABEL_332;
                                                      }
                                                    }
                                                    v258 = -1073741762;
                                                    goto LABEL_332;
                                                  }
                                                }
                                                else
                                                {
                                                  v244 = v661;
                                                }
                                                do
                                                  v244 ^= *((_BYTE *)v205 + v246++);
                                                while ( v246 < v203 );
                                                goto LABEL_299;
                                              }
                                              v13 = -805306355;
                                              LODWORD(v700) = -805306355;
                                            }
                                            else
                                            {
                                              v13 = -805306355;
                                              LODWORD(v700) = -805306355;
                                            }
                                          }
                                          else
                                          {
                                            v13 = -805306355;
                                            LODWORD(v700) = -805306355;
                                          }
LABEL_812:
                                          v645 = v656;
                                          goto LABEL_268;
                                        }
                                        v645 = v656;
                                        v48 = Src;
LABEL_216:
                                        v648 = v48;
                                        goto LABEL_110;
                                      }
                                      v188 = v700;
                                      goto LABEL_815;
                                    }
                                    goto LABEL_213;
                                  }
                                  v13 = -805306306;
                                  v645 = v656;
LABEL_313:
                                  v653 = v167;
                                  goto LABEL_267;
                                }
                                v13 = -2147024774;
LABEL_315:
                                v167 = v653;
                                v645 = v656;
                                goto LABEL_313;
                              }
                            }
                            else
                            {
                              LastError = GetLastError();
                              LODWORD(v700) = LastError;
                              v13 = LastError;
                              if ( LastError <= 0 )
                                goto LABEL_245;
                            }
                            v13 = (unsigned __int16)LastError | 0x80070000;
                            LODWORD(v700) = v13;
                            goto LABEL_245;
                          }
                          v13 = -2147418113;
                          v645 = v158;
                          v648 = v156;
                        }
                      }
                      else
                      {
                        v13 = -1073741811;
                        v645 = lpMem;
                      }
LABEL_109:
                      LODWORD(v700) = v13;
                      v48 = v648;
                      goto LABEL_110;
                    }
                  }
LABEL_29:
                  v13 = -805306219;
                  LODWORD(v700) = -805306219;
                  goto LABEL_79;
                }
                goto LABEL_77;
              }
              LODWORD(v703) = 0;
              LODWORD(v700) = RtlUIntAdd(4, 4, &v703);
              v13 = v700;
              if ( (v700 & 0x80000000) == 0LL )
              {
                LODWORD(v700) = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v703, (char *)cchMax + 4);
                v13 = v700;
                if ( (v700 & 0x80000000) == 0LL )
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
            LODWORD(v703) = 0;
            LODWORD(v700) = RtlUIntAdd(4, (unsigned int)v28, &v703);
            v13 = v700;
            if ( (v700 & 0x80000000) != 0LL )
            {
              v30 = 4;
              goto LABEL_72;
            }
            v608 = RtlUIntAdd(HIDWORD(cchMax[0]), (unsigned int)v703, (char *)cchMax + 4);
            v30 = 4;
            v13 = v608;
            LODWORD(v700) = v608;
            if ( v608 < 0 )
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
        LODWORD(v700) = v13;
        goto LABEL_72;
      }
      v684 = -1;
    }
LABEL_34:
    v13 = -1073741675;
LABEL_35:
    LODWORD(v700) = v13;
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
0x18000b010  push    rbp
0x18000b012  push    rbx
0x18000b013  push    rsi
0x18000b014  push    r15
0x18000b016  lea     rbp, [rsp-138h]
0x18000b01e  sub     rsp, 238h
0x18000b025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b02c  lea     rsi, WPP_GLOBAL_Control
0x18000b033  cmp     rcx, rsi
0x18000b036  jnz     short loc_18000B0AD
0x18000b038  xor     r15d, r15d
0x18000b03b  lea     rcx, [rbp+150h+arg_0]
0x18000b042  mov     [rbp+150h+var_120], r15d
0x18000b046  mov     [rbp+150h+Binding], r15
0x18000b04d  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b054  call    GetProcessLowBoxStatus
0x18000b059  cmp     dword ptr [rbp+150h+arg_0], r15d
0x18000b060  jnz     short loc_18000B067
0x18000b062  call    DebugInitEx
0x18000b067  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18000b06e  jnz     loc_18000CF45
0x18000b074  call    RasInitializeNoWait
0x18000b079  mov     ebx, eax
0x18000b07b  test    eax, eax
0x18000b07d  jz      short loc_18000B0D7
0x18000b07f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b086  cmp     rcx, rsi
0x18000b089  jz      loc_18000D036
0x18000b08f  test    byte ptr [rcx+1Ch], 40h
0x18000b093  jz      loc_18000D02F
0x18000b099  cmp     byte ptr [rcx+19h], 2
0x18000b09d  jb      loc_18000D02F
0x18000b0a3  mov     edx, 50h ; 'P'
0x18000b0a8  jmp     loc_18000FF24
0x18000b0ad  test    byte ptr [rcx+1Ch], 40h
0x18000b0b1  jz      short loc_18000B038
0x18000b0b3  cmp     byte ptr [rcx+19h], 6
0x18000b0b7  jb      loc_18000B038
0x18000b0bd  mov     rcx, [rcx+10h]
0x18000b0c1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000b0c8  mov     edx, 4Fh ; 'O'
0x18000b0cd  call    WPP_SF_
0x18000b0d2  jmp     loc_18000B038
0x18000b0d7  xor     edx, edx; lpDatabaseName
0x18000b0d9  xor     ecx, ecx; lpMachineName
0x18000b0db  mov     r8d, 1; dwDesiredAccess
0x18000b0e1  call    cs:__imp_OpenSCManagerA
0x18000b0e7  mov     [rbp+150h+hSCObject], rax
0x18000b0ee  test    rax, rax
0x18000b0f1  jz      loc_18000FF3C
0x18000b0f7  mov     [rsp+250h+var_20], rdi
0x18000b0ff  mov     rbx, r15
0x18000b102  mov     [rsp+250h+var_28], r12
0x18000b10a  mov     edx, 4; uBytes
0x18000b10f  mov     [rsp+250h+var_30], r13
0x18000b117  mov     ecx, 40h ; '@'; uFlags
0x18000b11c  mov     [rsp+250h+var_38], r14
0x18000b124  mov     [rbp+150h+var_108], r15d
0x18000b128  mov     [rbp+150h+var_D8], rbx
0x18000b12c  call    cs:__imp_LocalAlloc
0x18000b132  mov     [rbp+150h+var_110], rax
0x18000b136  mov     r14, rax
0x18000b139  test    rax, rax
0x18000b13c  jz      loc_18000B294
0x18000b142  xorps   xmm0, xmm0
0x18000b145  mov     [rbp+150h+var_EC], r15d
0x18000b149  movups  xmmword ptr [rsp+250h+cchMax], xmm0
0x18000b14e  mov     [rbp+150h+var_F8], r15d
0x18000b152  mov     r13, r15
0x18000b155  mov     [rsp+250h+var_1D8], r15
0x18000b15a  call    cs:__imp_GetProcessHeap
0x18000b160  mov     edx, 8; dwFlags
0x18000b165  mov     r8d, 0A0h; dwBytes
0x18000b16b  mov     rcx, rax; hHeap
0x18000b16e  call    cs:__imp_HeapAlloc
0x18000b174  mov     dword ptr [rbp+150h+arg_8], 0D0000017h
0x18000b17e  mov     rsi, 0C81ECB17B1B54A58h
0x18000b188  mov     [rbp+150h+var_138], rax
0x18000b18c  mov     r12, rax
0x18000b18f  mov     rdi, 7F1137FAB69605Eh
0x18000b199  test    rax, rax
0x18000b19c  jz      loc_18000FF72
0x18000b1a2  movups  xmm0, cs:?DecryptionCipher@?1??WarbirdUmGetDecryptionCipher@@9@4PAEA; uchar near * `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher
0x18000b1a9  movups  xmmword ptr [rax], xmm0
0x18000b1ac  movups  xmm1, cs:xmmword_1800301A0
0x18000b1b3  movups  xmmword ptr [rax+10h], xmm1
0x18000b1b7  movups  xmm0, cs:xmmword_1800301B0
0x18000b1be  movups  xmmword ptr [rax+20h], xmm0
0x18000b1c2  movups  xmm1, cs:xmmword_1800301C0
0x18000b1c9  movups  xmmword ptr [rax+30h], xmm1
0x18000b1cd  movups  xmm0, cs:xmmword_1800301D0
0x18000b1d4  movups  xmmword ptr [rax+40h], xmm0
0x18000b1d8  movups  xmm1, cs:xmmword_1800301E0
0x18000b1df  movups  xmmword ptr [rax+50h], xmm1
0x18000b1e3  movups  xmm0, cs:xmmword_1800301F0
0x18000b1ea  movups  xmmword ptr [rax+60h], xmm0
0x18000b1ee  movups  xmm1, cs:xmmword_180030200
0x18000b1f5  movups  xmmword ptr [rax+70h], xmm1
0x18000b1f9  movups  xmm0, cs:xmmword_180030210
0x18000b200  movups  xmmword ptr [rax+80h], xmm0
0x18000b207  movups  xmm1, cs:xmmword_180030220
0x18000b20e  movups  xmmword ptr [rax+90h], xmm1
0x18000b215  call    cs:__imp_GetProcessHeap
0x18000b21b  mov     edx, 8; dwFlags
0x18000b220  mov     rcx, rax; hHeap
0x18000b223  mov     r8d, edx; dwBytes
0x18000b226  call    cs:__imp_HeapAlloc
0x18000b22c  mov     rcx, rax; psz
0x18000b22f  test    rax, rax
0x18000b232  jz      loc_18000FF80
0x18000b238  mov     rax, cs:?nDecryptionKey@?1??WarbirdUmGetDecryptionKey@@9@4_KA; unsigned __int64 `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey
0x18000b23f  mov     r13, rcx
0x18000b242  mov     [rcx], rax
0x18000b245  mov     [rbp+150h+var_118], rcx
0x18000b249  rdtsc
0x18000b24b  shl     rdx, 20h; cchMax
0x18000b24f  or      rax, rdx
0x18000b252  mov     [rbp+150h+var_160], rax
0x18000b256  lea     r8, [rbp+150h+pcchLength]; pcchLength
0x18000b25a  mov     [rbp+150h+pcchLength], r15
0x18000b25e  call    StringLengthWorkerW
0x18000b263  test    eax, eax
0x18000b265  js      loc_18000FF8B
0x18000b26b  mov     rax, [rbp+150h+pcchLength]
0x18000b26f  inc     rax
0x18000b272  mov     [rbp+150h+pcchLength], rax
0x18000b276  lea     eax, ds:4[rax*2]
0x18000b27d  cmp     eax, 4
0x18000b280  jnb     short loc_18000B2CC
0x18000b282  mov     r15d, 0C0000095h
0x18000b288  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b28f  jmp     loc_18000B612
0x18000b294  mov     eax, r15d
0x18000b297  mov     r15d, 8007000Eh
0x18000b29d  jmp     short loc_18000B2AF
0x18000b29f  cmp     [rbp+150h+var_EC], 0
0x18000b2a3  jnz     loc_18000D58B
0x18000b2a9  mov     eax, [rbp+150h+var_F8]
0x18000b2ac  mov     rbx, r14
0x18000b2af  test    r15d, r15d
0x18000b2b2  js      loc_18000B68D
0x18000b2b8  cmp     eax, 4
0x18000b2bb  jz      loc_18000FAC2
0x18000b2c1  mov     r15d, 0C004F01Eh
0x18000b2c7  jmp     loc_18000D3D3
0x18000b2cc  add     eax, 0C4h
0x18000b2d1  cmp     eax, 0C4h
0x18000b2d6  jnb     short loc_18000B2EA
0x18000b2d8  mov     r15d, 0D0000095h
0x18000b2de  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b2e5  jmp     loc_18000B612
0x18000b2ea  lea     ecx, [rax+8]
0x18000b2ed  cmp     ecx, eax
0x18000b2ef  jb      short loc_18000B2D8
0x18000b2f1  lea     eax, [rcx+8]
0x18000b2f4  cmp     eax, ecx
0x18000b2f6  jb      short loc_18000B2D8
0x18000b2f8  mov     dword ptr [rsp+250h+cchMax+4], eax
0x18000b2fc  mov     r15d, eax
0x18000b2ff  call    cs:__imp_GetProcessHeap
0x18000b305  mov     r8d, r15d; dwBytes
0x18000b308  mov     edx, 8; dwFlags
0x18000b30d  mov     rcx, rax; hHeap
0x18000b310  call    cs:__imp_HeapAlloc
0x18000b316  mov     rdx, rax
0x18000b319  test    rax, rax
0x18000b31c  jz      loc_18000FF9A
0x18000b322  xor     r9d, r9d
0x18000b325  mov     dword ptr [rbp+150h+lpMem], ebx
0x18000b32b  mov     [rsp+250h+cchMax+8], rax
0x18000b330  mov     dword ptr [rsp+250h+cchMax], r9d
0x18000b335  test    rax, rax
0x18000b338  jz      loc_18000E495
0x18000b33e  xor     r8d, r8d
0x18000b341  cmp     r8d, r9d
0x18000b344  jnb     short loc_18000B366
0x18000b346  mov     eax, [rdx]
0x18000b348  add     eax, 4
0x18000b34b  cmp     eax, 4
0x18000b34e  jnb     loc_18000C20F
0x18000b354  mov     r15d, 0C0000095h
0x18000b35a  mov     dword ptr [rbp+150h+arg_0], r15d
0x18000b361  jmp     loc_18000B609
0x18000b366  lea     r8, [rdx+4]
0x18000b36a  cmp     r8, rdx
0x18000b36d  jb      short loc_18000B354
0x18000b36f  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b373  lea     rax, [rdx+8]
0x18000b377  add     rcx, [rsp+250h+cchMax+8]
0x18000b37c  cmp     rax, rcx
0x18000b37f  ja      loc_18000FFA5
0x18000b385  mov     dword ptr [rdx], 4
0x18000b38b  mov     [r8], ebx
0x18000b38e  mov     r8d, dword ptr [rsp+250h+cchMax]
0x18000b393  mov     rdx, [rsp+250h+cchMax+8]
0x18000b398  inc     r8d
0x18000b39b  mov     dword ptr [rsp+250h+cchMax], r8d
0x18000b3a0  test    rdx, rdx
0x18000b3a3  jz      loc_18000E4E9
0x18000b3a9  cmp     r9d, r8d
0x18000b3ac  jnb     short loc_18000B3CA
0x18000b3ae  mov     eax, [rdx]
0x18000b3b0  add     eax, 4
0x18000b3b3  cmp     eax, 4
0x18000b3b6  jb      short loc_18000B354
0x18000b3b8  mov     ecx, eax
0x18000b3ba  add     rcx, rdx
0x18000b3bd  cmp     rcx, rdx
0x18000b3c0  jb      short loc_18000B354
0x18000b3c2  mov     rdx, rcx
0x18000b3c5  inc     r9d
0x18000b3c8  jmp     short loc_18000B3A9
0x18000b3ca  lea     r8, [rdx+4]
0x18000b3ce  cmp     r8, rdx
0x18000b3d1  jb      short loc_18000B354
0x18000b3d3  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b3d7  lea     rax, [rdx+0A4h]
0x18000b3de  add     rcx, [rsp+250h+cchMax+8]
0x18000b3e3  cmp     rax, rcx
0x18000b3e6  ja      loc_18000FFB0
0x18000b3ec  mov     dword ptr [rdx], 0A0h
0x18000b3f2  movups  xmm0, xmmword ptr [r12]
0x18000b3f7  movups  xmmword ptr [r8], xmm0
0x18000b3fb  movups  xmm1, xmmword ptr [r12+10h]
0x18000b401  movups  xmmword ptr [r8+10h], xmm1
0x18000b406  movups  xmm0, xmmword ptr [r12+20h]
0x18000b40c  movups  xmmword ptr [r8+20h], xmm0
0x18000b411  movups  xmm1, xmmword ptr [r12+30h]
0x18000b417  movups  xmmword ptr [r8+30h], xmm1
0x18000b41c  movups  xmm0, xmmword ptr [r12+40h]
0x18000b422  movups  xmmword ptr [r8+40h], xmm0
0x18000b427  movups  xmm1, xmmword ptr [r12+50h]
0x18000b42d  movups  xmmword ptr [r8+50h], xmm1
0x18000b432  movups  xmm0, xmmword ptr [r12+60h]
0x18000b438  movups  xmmword ptr [r8+60h], xmm0
0x18000b43d  movups  xmm1, xmmword ptr [r12+70h]
0x18000b443  movups  xmmword ptr [r8+70h], xmm1
0x18000b448  movups  xmm0, xmmword ptr [r12+80h]
0x18000b451  movups  xmmword ptr [r8+80h], xmm0
0x18000b459  movups  xmm1, xmmword ptr [r12+90h]
0x18000b462  movups  xmmword ptr [r8+90h], xmm1
0x18000b46a  mov     r8d, dword ptr [rsp+250h+cchMax]
0x18000b46f  mov     rdx, [rsp+250h+cchMax+8]
0x18000b474  inc     r8d
0x18000b477  mov     dword ptr [rsp+250h+cchMax], r8d
0x18000b47c  test    rdx, rdx
0x18000b47f  jz      loc_18000E540
0x18000b485  xor     r9d, r9d
0x18000b488  cmp     r9d, r8d
0x18000b48b  jnb     short loc_18000B4B1
0x18000b48d  mov     eax, [rdx]
0x18000b48f  add     eax, 4
0x18000b492  cmp     eax, 4
0x18000b495  jb      loc_18000B354
0x18000b49b  mov     ecx, eax
0x18000b49d  add     rcx, rdx
0x18000b4a0  cmp     rcx, rdx
0x18000b4a3  jb      loc_18000B354
0x18000b4a9  mov     rdx, rcx
0x18000b4ac  inc     r9d
0x18000b4af  jmp     short loc_18000B488
0x18000b4b1  lea     r8, [rdx+4]
0x18000b4b5  cmp     r8, rdx
0x18000b4b8  jb      loc_18000B354
0x18000b4be  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b4c2  lea     rax, [rdx+0Ch]
0x18000b4c6  add     rcx, [rsp+250h+cchMax+8]
0x18000b4cb  cmp     rax, rcx
0x18000b4ce  ja      loc_18000FFBB
0x18000b4d4  mov     dword ptr [rdx], 8
0x18000b4da  movsd   xmm0, qword ptr [r13+0]
0x18000b4e0  movsd   qword ptr [r8], xmm0
0x18000b4e5  mov     r8d, dword ptr [rsp+250h+cchMax]
0x18000b4ea  mov     rdx, [rsp+250h+cchMax+8]; cchMax
0x18000b4ef  inc     r8d
0x18000b4f2  mov     dword ptr [rsp+250h+cchMax], r8d
0x18000b4f7  test    rdx, rdx
0x18000b4fa  jz      loc_18000E597
0x18000b500  xor     r9d, r9d
0x18000b503  cmp     r9d, r8d
0x18000b506  jnb     short loc_18000B52C
0x18000b508  mov     eax, [rdx]
0x18000b50a  add     eax, 4
0x18000b50d  cmp     eax, 4
0x18000b510  jb      loc_18000B354
0x18000b516  mov     ecx, eax
0x18000b518  add     rcx, rdx
0x18000b51b  cmp     rcx, rdx
0x18000b51e  jb      loc_18000B354
0x18000b524  mov     rdx, rcx
0x18000b527  inc     r9d
0x18000b52a  jmp     short loc_18000B503
0x18000b52c  lea     r8, [rdx+4]
0x18000b530  cmp     r8, rdx
0x18000b533  jb      loc_18000B354
0x18000b539  mov     ecx, dword ptr [rsp+250h+cchMax+4]
0x18000b53d  lea     rax, [rdx+0Ch]
0x18000b541  add     rcx, [rsp+250h+cchMax+8]; psz
0x18000b546  cmp     rax, rcx
0x18000b549  ja      loc_18000FFC6
  ... truncated ...
```
