# SLGetWindowsInformationDWORD

- ea: `0x180067160`
- end: `0x180073448`
- name: `SLGetWindowsInformationDWORD`
- size: `49896`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010b80`
- `0x180010c50`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x180017b20`
- `0x180066f10`
- `0x180066f50`
- `0x180066f90`
- `0x180066fd0`
- `0x180067020`
- `0x180067060`
- `0x1800670a0`
- `0x180067160`
- `0x180073450`
- `0x1800886fc`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006783d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067855`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006786d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067885`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab65`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b4d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b4ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b505`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b51d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d2ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d2d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d2f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d30e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fdba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fdd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fdf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fe0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800707c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800707e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800707ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007081b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070b98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070bb4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070bd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070bec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180073078`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180073094`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800730b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800730cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006783d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067855`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006786d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067885`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab65`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ab7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b4d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b4ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b505`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b51d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d2ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d2d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d2f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d30e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fdba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fdd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fdf2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006fe0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800707c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800707e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800707ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007081b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070b98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070bb4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070bd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070bec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180073078`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180073094`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800730b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800730cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006774c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006905d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006aa35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b3d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800706cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180071d5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006774c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006905d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006aa35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b3d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800706cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180071d5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180067671`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180069006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006a943`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006b2e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800705c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180071d06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180067671`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180069006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006a943`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006b2e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800705c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180071d06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006a3af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006a3af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800677a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800677d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800677fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006781f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067d8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067e94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068bc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068bfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068c34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068ca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068cdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068d15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068d4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068d75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800693b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800693f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069451`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800694e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069580`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069d58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069d85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069dbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069e13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069e67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069e94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069eb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069edd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069f02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069f38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069f9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069fbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180069fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a03c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a2f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a319`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a342`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a367`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006aa9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006aac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006aaf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ab17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b43d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b469`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b495`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b4b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c19e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cfa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fc68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006fcd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070754`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800707a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800718d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071939`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071986`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800719c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800719ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072153`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007218f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800721cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800721f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007229b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800722d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072313`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007233b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072c62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072c99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072cd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072d0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072d2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072d58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072d81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072dbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072df7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072e4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072e79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072ee4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072f32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072f5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072fc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800677a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800677d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800677fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006781f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067d8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067e94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067eb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068bc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068bfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068c34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068ca4`

## string_xrefs

- `0x180068fbc`: `ntdll.dll`
- `0x180071cbc`: `ntdll.dll`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformationDWORD(PCWSTR pwszValueName, DWORD *pdwValue)
{
  HRESULT v2; // edi
  char *v3; // rax
  WCHAR *v4; // r13
  int v5; // r14d
  __int64 *v6; // rbx
  int v7; // r9d
  int v8; // r15d
  int v9; // edx
  char *v10; // rdi
  __int64 v11; // rsi
  int v12; // eax
  int v13; // r11d
  int v14; // r10d
  int v15; // r11d
  int v16; // ecx
  int v17; // r10d
  unsigned int v18; // edx
  int v19; // r8d
  unsigned int v20; // ecx
  int v21; // r9d
  int v22; // edx
  unsigned int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // edx
  unsigned int v27; // r8d
  int v28; // ecx
  int v29; // edx
  unsigned int v30; // r9d
  unsigned int v31; // edx
  int v32; // r8d
  int v33; // ecx
  unsigned int v34; // edx
  int v35; // r8d
  int v36; // ecx
  int v37; // edx
  unsigned int v38; // r8d
  int v39; // r9d
  int v40; // eax
  unsigned __int64 v41; // rax
  __m128 v42; // xmm2
  __m128 v43; // xmm1
  __m128 v44; // xmm0
  __m128 v45; // xmm1
  __m128 v46; // xmm1
  __m128 v47; // xmm1
  __m128 v48; // xmm1
  char i; // cl
  __int64 v50; // rax
  __int64 v51; // r14
  int v52; // r15d
  const WCHAR *j; // rdi
  __int64 v54; // rbx
  bool v55; // zf
  __int64 v56; // rsi
  HMODULE *v57; // r12
  const WCHAR *v58; // rdi
  __int64 v59; // rax
  char *v60; // rdx
  unsigned int v61; // r13d
  unsigned int v62; // esi
  __int64 v63; // rbx
  void **ProcAddress; // rax
  HANDLE v65; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v67; // rax
  HANDLE v68; // rax
  void *v69; // rsi
  _WORD *v70; // rdi
  int v71; // r12d
  __int64 v72; // r15
  void *v73; // rbx
  __int64 v74; // r9
  signed int LastError; // eax
  signed int v76; // r14d
  unsigned int v77; // ebx
  HANDLE v78; // rax
  HANDLE v79; // rax
  unsigned int (__fastcall *v80)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v82; // r15
  signed int v83; // eax
  _WORD *v84; // rbx
  __int64 i10; // r9
  signed int v86; // eax
  unsigned int v87; // ebx
  HANDLE v88; // rax
  HANDLE v89; // rax
  __int64 v90; // rcx
  __int16 v91; // ax
  __int64 v92; // rcx
  __int16 v93; // ax
  HANDLE CurrentProcess; // rax
  signed int v95; // eax
  HANDLE v96; // rax
  HANDLE v97; // rax
  HLOCAL v98; // rax
  void *v99; // rbx
  HANDLE v100; // rax
  _OWORD *v101; // rax
  void *v102; // r15
  unsigned int *v103; // r12
  HANDLE v104; // rax
  _QWORD *v105; // rax
  unsigned int v106; // r11d
  unsigned int v107; // eax
  unsigned int v108; // eax
  __int64 v109; // rdi
  HANDLE v110; // rax
  _DWORD *v111; // rax
  _DWORD *v112; // r8
  _DWORD *v113; // rax
  unsigned int v114; // ebx
  int v115; // ecx
  char *v116; // r15
  unsigned int v117; // eax
  unsigned __int64 v118; // rdx
  void *v119; // r9
  size_t v120; // rdx
  unsigned int v121; // r11d
  void *v122; // rdi
  void *v123; // r10
  _DWORD *v124; // rdx
  unsigned int k; // ecx
  unsigned int v126; // eax
  unsigned __int64 v127; // r8
  unsigned int v128; // ecx
  unsigned int v129; // eax
  size_t v130; // r8
  SIZE_T *v131; // r8
  SIZE_T v132; // rax
  STRSAFE_PCNZWCH v133; // rdi
  unsigned int v134; // r11d
  __int64 v135; // r9
  unsigned int v136; // r9d
  size_t v137; // r15
  int v138; // r13d
  unsigned int v139; // ecx
  _DWORD *v140; // rdx
  unsigned int v141; // eax
  _DWORD *v142; // r9
  unsigned int v143; // eax
  unsigned int v144; // ebx
  unsigned int v145; // ecx
  _DWORD *v146; // rdx
  unsigned int v147; // eax
  int v148; // eax
  unsigned int v149; // ecx
  _DWORD *v150; // rdx
  unsigned int v151; // ebx
  unsigned int v152; // eax
  SIZE_T v153; // rax
  void *v154; // r13
  HANDLE v155; // rax
  char *v156; // rax
  char *v157; // rdi
  char *v158; // rax
  size_t v159; // r8
  _QWORD *v160; // r15
  __int64 v161; // rbx
  int v162; // ecx
  size_t v163; // r8
  unsigned __int64 v164; // rax
  __m128 v165; // xmm2
  __m128 v166; // xmm1
  __m128 v167; // xmm0
  __m128 v168; // xmm1
  __m128 v169; // xmm1
  __m128 v170; // xmm1
  __m128 v171; // xmm1
  int v172; // edx
  unsigned __int8 *v173; // r14
  int v174; // edi
  int v175; // r13d
  int v176; // r12d
  unsigned int v177; // r15d
  int v178; // r8d
  int v179; // eax
  int v180; // r11d
  int v181; // r10d
  int v182; // r11d
  int v183; // r10d
  int v184; // r9d
  int v185; // edx
  int v186; // r9d
  int v187; // r8d
  int v188; // edx
  unsigned int v189; // ecx
  int v190; // r8d
  int v191; // eax
  int v192; // ecx
  int v193; // edx
  int v194; // r8d
  int v195; // ecx
  unsigned int v196; // edx
  unsigned int v197; // r8d
  int v198; // ecx
  int v199; // edx
  int v200; // r8d
  int v201; // ecx
  int v202; // edx
  int v203; // r9d
  int v204; // ecx
  int v205; // r8d
  unsigned int v206; // edx
  int v207; // r9d
  int v208; // ecx
  int v209; // r8d
  int v210; // r8d
  _BYTE *v211; // rcx
  HANDLE v212; // rax
  LPVOID v213; // rbx
  HANDLE v214; // rax
  void *v215; // rax
  const void *v216; // rdx
  HANDLE v217; // rax
  _OWORD *v218; // rax
  HANDLE v219; // rax
  _QWORD *v220; // rax
  HANDLE v221; // rax
  HANDLE v222; // rax
  HANDLE v223; // rax
  HANDLE v224; // rax
  HANDLE v225; // rax
  unsigned int v226; // ecx
  unsigned int v227; // edx
  unsigned int v228; // ecx
  unsigned int v229; // eax
  unsigned int v230; // ebx
  HANDLE v231; // rax
  char *v232; // rax
  char *v233; // rbx
  char *v234; // rcx
  unsigned __int16 *v235; // rdx
  unsigned __int16 *v236; // rcx
  unsigned int *v237; // r8
  unsigned int *v238; // rdx
  unsigned int *v239; // rax
  __int64 v240; // r8
  _DWORD *v241; // rcx
  unsigned int v242; // edx
  unsigned int v243; // eax
  unsigned int v244; // ebx
  HANDLE v245; // rax
  void *v246; // rbx
  signed int v247; // eax
  int v248; // r8d
  FARPROC v249; // rax
  int v250; // eax
  unsigned int v251; // edx
  SIZE_T v252; // r10
  unsigned int *v253; // rcx
  int *v254; // r8
  SIZE_T v255; // r9
  unsigned int *v256; // r11
  unsigned int v257; // r8d
  unsigned int *v258; // r11
  unsigned int v259; // ecx
  unsigned int v260; // r8d
  unsigned int v261; // ecx
  HANDLE v262; // rax
  _QWORD *v263; // r13
  unsigned int *v264; // rax
  HANDLE v265; // rax
  void *v266; // rax
  SIZE_T v267; // r8
  HANDLE v268; // rax
  void *v269; // rax
  SIZE_T v270; // r8
  const void *v271; // rdx
  SIZE_T v272; // rax
  HANDLE v273; // rax
  void *v274; // rax
  _QWORD *v275; // rbx
  unsigned __int16 *v276; // rax
  HANDLE v277; // rax
  HANDLE v278; // rax
  HANDLE v279; // rax
  HANDLE v280; // rax
  unsigned int *v281; // rax
  SIZE_T v282; // r8
  void *v283; // rdx
  int v284; // r8d
  unsigned int *v285; // rcx
  _QWORD *v286; // rbx
  HANDLE v287; // rax
  HANDLE v288; // rax
  HANDLE v289; // rax
  HANDLE v290; // rax
  __int64 v291; // rax
  unsigned __int64 v292; // rbx
  void *v293; // rax
  unsigned __int8 *v294; // r9
  _BYTE *v295; // r11
  unsigned int v296; // r8d
  unsigned int v297; // edx
  int v298; // esi
  int v299; // eax
  char v300; // r10
  int v301; // ecx
  int v302; // eax
  int v303; // ecx
  int v304; // eax
  int v305; // edx
  char v306; // r10
  int v307; // r8d
  char v308; // cl
  int v309; // r10d
  SIZE_T v310; // rsi
  unsigned int v311; // r12d
  int v312; // r13d
  SIZE_T v313; // r15
  int v314; // edi
  int v315; // ebx
  int v316; // r11d
  unsigned int v317; // edx
  int v318; // r8d
  unsigned int v319; // ecx
  int v320; // edx
  int v321; // r8d
  unsigned int v322; // ecx
  int v323; // edx
  int v324; // r9d
  int v325; // r10d
  unsigned int v326; // r8d
  int v327; // ecx
  int v328; // edx
  unsigned int v329; // r8d
  int v330; // ecx
  int v331; // edx
  int v332; // r8d
  int v333; // ecx
  unsigned int v334; // r8d
  int v335; // edx
  int v336; // ecx
  int v337; // r8d
  unsigned int v338; // edx
  int v339; // ecx
  int v340; // r10d
  unsigned __int64 v341; // rax
  __m128 v342; // xmm2
  __m128 v343; // xmm1
  __m128 v344; // xmm0
  __m128 v345; // xmm1
  __m128 v346; // xmm1
  __m128 v347; // xmm1
  __m128 v348; // xmm1
  unsigned __int8 m; // dl
  _DWORD *v350; // rdx
  unsigned int *v351; // rcx
  char *v352; // r9
  __int64 v353; // r10
  unsigned __int64 v354; // r8
  SIZE_T v355; // r11
  int v356; // ebx
  char *v357; // rcx
  unsigned int v358; // eax
  char *v359; // rdx
  int v360; // r8d
  void *v361; // rax
  HANDLE v362; // rax
  HANDLE v363; // rax
  HANDLE v364; // rax
  void *v365; // rbx
  HANDLE v366; // rax
  HANDLE v367; // rax
  void *v368; // rbx
  HANDLE v369; // rax
  void *v370; // rbx
  HANDLE v371; // rax
  HANDLE v372; // rax
  HANDLE v373; // rax
  HANDLE v374; // rax
  _QWORD *v375; // rdi
  void *v376; // rbx
  HANDLE v377; // rax
  void *v378; // rbx
  HANDLE v379; // rax
  void *v380; // rbx
  HANDLE v381; // rax
  HANDLE v382; // rax
  wchar_t *v383; // rbx
  HANDLE v384; // rax
  int v385; // ebx
  HANDLE v386; // rax
  int *v387; // rcx
  int v388; // ecx
  int v389; // edi
  unsigned int *v390; // rdx
  unsigned int *v391; // rax
  _QWORD *v392; // rcx
  unsigned int v393; // eax
  _QWORD *v394; // rbx
  __int64 v395; // rax
  unsigned __int64 v396; // rcx
  int *v397; // rax
  unsigned int *v398; // rcx
  int v399; // eax
  unsigned int *v400; // r11
  unsigned int *v401; // rcx
  __int64 v402; // rax
  unsigned int *v403; // rdx
  unsigned int *v404; // rcx
  unsigned int *v405; // rdx
  size_t v406; // r8
  const void *v407; // r10
  int *v408; // rax
  _DWORD *v409; // rcx
  int v410; // eax
  _DWORD *v411; // r9
  unsigned __int64 v412; // rcx
  int *v413; // rax
  _DWORD *v414; // rdx
  int v415; // eax
  _DWORD *v416; // rcx
  bool v417; // cc
  void *v418; // rbx
  HANDLE v419; // rax
  HANDLE v420; // rax
  HANDLE v421; // rax
  HANDLE v422; // rax
  DWORD ModuleFileNameW; // eax
  __int64 v424; // rax
  unsigned int v425; // edi
  char *v426; // rax
  int v427; // r13d
  __int64 *v428; // rbx
  int v429; // r8d
  char *v430; // r15
  int v431; // edx
  int v432; // r14d
  __int64 v433; // r12
  int v434; // eax
  int v435; // r11d
  int v436; // r10d
  int v437; // r11d
  int v438; // ecx
  int v439; // r10d
  unsigned int v440; // edx
  int v441; // r8d
  unsigned int v442; // r9d
  int v443; // ecx
  int v444; // edx
  unsigned int v445; // r8d
  int v446; // r9d
  int v447; // ecx
  int v448; // edx
  unsigned int v449; // r8d
  int v450; // ecx
  int v451; // edx
  unsigned int v452; // r9d
  unsigned int v453; // edx
  int v454; // r8d
  int v455; // ecx
  unsigned int v456; // edx
  int v457; // r8d
  int v458; // ecx
  int v459; // edx
  unsigned int v460; // r8d
  int v461; // ecx
  int v462; // edx
  WCHAR *v463; // rbx
  unsigned __int64 v464; // rax
  __m128 v465; // xmm2
  __m128 v466; // xmm1
  __m128 v467; // xmm0
  __m128 v468; // xmm1
  __m128 v469; // xmm1
  __m128 v470; // xmm1
  __m128 v471; // xmm1
  char n; // cl
  __int64 v473; // rax
  int v474; // r13d
  const WCHAR *v475; // r15
  __int64 v476; // rbx
  __int64 v477; // r12
  HMODULE *v478; // rcx
  const WCHAR *v479; // r15
  __int64 v480; // rax
  unsigned __int64 v481; // rdx
  unsigned int v482; // eax
  unsigned int v483; // r12d
  int v484; // eax
  __int64 v485; // rbx
  void **v486; // rax
  HANDLE v487; // rax
  HANDLE v488; // rax
  HANDLE v489; // rax
  char *v490; // rax
  int v491; // r13d
  __int64 *v492; // rbx
  int v493; // r9d
  char *v494; // r15
  int v495; // edx
  int v496; // esi
  __int64 v497; // r12
  int v498; // eax
  int v499; // r11d
  int v500; // r10d
  int v501; // r11d
  int v502; // ecx
  int v503; // r10d
  unsigned int v504; // edx
  int v505; // r8d
  unsigned int v506; // ecx
  int v507; // r9d
  int v508; // edx
  unsigned int v509; // r8d
  int v510; // r9d
  int v511; // ecx
  int v512; // edx
  unsigned int v513; // r8d
  int v514; // ecx
  int v515; // edx
  unsigned int v516; // r9d
  unsigned int v517; // edx
  int v518; // r8d
  int v519; // ecx
  unsigned int v520; // edx
  int v521; // r8d
  int v522; // ecx
  int v523; // edx
  unsigned int v524; // r8d
  int v525; // r9d
  int v526; // eax
  WCHAR *v527; // rbx
  unsigned __int64 v528; // rax
  __m128 v529; // xmm1
  __m128 v530; // xmm2
  __m128 v531; // xmm0
  __m128 v532; // xmm0
  __m128 v533; // xmm1
  __m128 v534; // xmm1
  __m128 v535; // xmm1
  __m128 v536; // xmm1
  char ii; // cl
  __int64 v538; // rax
  int v539; // r13d
  const WCHAR *v540; // r15
  __int64 v541; // rbx
  __int64 v542; // r12
  HMODULE *v543; // rcx
  const WCHAR *v544; // r15
  __int64 v545; // rax
  unsigned __int64 v546; // rdx
  unsigned int v547; // eax
  unsigned int v548; // r12d
  int v549; // eax
  __int64 v550; // rbx
  void **v551; // rax
  HANDLE v552; // rax
  HANDLE v553; // rax
  HANDLE v554; // rax
  signed int v555; // eax
  signed int v556; // ebx
  __int64 v557; // r12
  signed int v558; // eax
  signed int v559; // edx
  __int64 v560; // rax
  WARBIRD_DELAY_LOAD *v561; // rbx
  __int64 v562; // rax
  SIZE_T v563; // r15
  unsigned int v564; // r13d
  _DWORD *jj; // r12
  __int64 v566; // rax
  unsigned int v567; // ebx
  unsigned int v568; // r9d
  unsigned int v569; // r8d
  unsigned int v570; // ebx
  unsigned int kk; // ecx
  __int64 v572; // rbx
  __int64 v573; // rax
  wchar_t *v574; // rcx
  __int64 v575; // rax
  wchar_t *v576; // rcx
  wchar_t *v577; // rcx
  __int64 v578; // rax
  wchar_t *v579; // rcx
  wchar_t *v580; // rdx
  __int64 v581; // rax
  wchar_t *v582; // rcx
  __int64 v583; // rax
  wchar_t *v584; // rdx
  __int64 v585; // rax
  wchar_t *v586; // rcx
  __int64 v587; // rax
  wchar_t *v588; // rdx
  __int64 v589; // rax
  __int64 v590; // rcx
  __int64 v591; // rax
  __int64 v592; // rdx
  __int64 v593; // rax
  __int64 v594; // rcx
  __int64 v595; // rax
  __int64 v596; // rdx
  __int64 v597; // rax
  __int64 v598; // rcx
  __int64 v599; // rax
  __int64 v600; // rdx
  __int64 v601; // rax
  __int64 v602; // rcx
  __int64 v603; // rax
  __int64 v604; // rdx
  __int64 v605; // rax
  __int64 v606; // rcx
  __int64 v607; // rax
  __int64 v608; // rdx
  __int64 v609; // rax
  __int64 v610; // rax
  SIZE_T v611; // r12
  __int64 v612; // rax
  __int64 v613; // rax
  _BYTE *v614; // rbx
  LPVOID *v615; // r13
  int v616; // r14d
  __int64 *v617; // r15
  int v618; // r8d
  __int64 v619; // r12
  int v620; // edx
  int v621; // esi
  __int64 v622; // r13
  int v623; // eax
  int v624; // r11d
  int v625; // r10d
  int v626; // r11d
  int v627; // ecx
  int v628; // r10d
  unsigned int v629; // edx
  int v630; // r8d
  unsigned int v631; // r9d
  int v632; // ecx
  int v633; // edx
  unsigned int v634; // r8d
  int v635; // r9d
  int v636; // ecx
  int v637; // edx
  unsigned int v638; // r8d
  int v639; // ecx
  int v640; // edx
  unsigned int v641; // r9d
  unsigned int v642; // edx
  int v643; // r8d
  int v644; // ecx
  unsigned int v645; // edx
  int v646; // r8d
  int v647; // ecx
  int v648; // edx
  unsigned int v649; // r8d
  int v650; // ecx
  int v651; // edx
  unsigned __int64 v652; // rax
  __m128 v653; // xmm2
  __m128 v654; // xmm1
  __m128 v655; // xmm0
  __m128 v656; // xmm1
  __m128 v657; // xmm1
  __m128 v658; // xmm1
  __m128 v659; // xmm1
  char mm; // cl
  HANDLE v661; // rax
  __int64 v662; // r9
  __int64 v663; // rax
  __int64 v664; // rdx
  char *v665; // rcx
  __int64 v666; // rdx
  __int64 v667; // rax
  __int64 v668; // rcx
  __int64 v669; // rax
  __int64 v670; // rdx
  __int64 v671; // rax
  __int64 v672; // rdx
  __int64 v673; // rcx
  __int64 v674; // rax
  __int64 v675; // rcx
  __int64 v676; // rax
  __int64 v677; // rcx
  __int64 v678; // rdx
  __int64 v679; // rax
  __int64 v680; // rcx
  __int64 v681; // rax
  __int64 v682; // rcx
  __int64 v683; // rax
  __int64 v684; // rdx
  __int64 v685; // rax
  __int64 v686; // rcx
  __int64 v687; // rax
  __int64 v688; // rdx
  __int64 v689; // rax
  __int64 v690; // rcx
  __int64 v691; // rax
  __int64 v692; // rdx
  __int64 v693; // rax
  __int64 v694; // rcx
  __int64 v695; // rax
  __int64 v696; // rdx
  __int64 v697; // rax
  __int64 v698; // rcx
  __int64 v699; // rax
  __int64 v700; // rdx
  __int64 v701; // rax
  __int64 v702; // rcx
  __int64 v703; // rax
  __int64 v704; // rdx
  __int64 v705; // rax
  __int64 v706; // rcx
  __int64 v707; // rax
  __int64 v708; // rdx
  __int64 v709; // rax
  __int64 v710; // rcx
  __int64 v711; // rax
  __int64 v712; // rdx
  __int64 v713; // rax
  __int64 v714; // rcx
  __int64 v715; // rax
  __int64 v716; // rdx
  __int64 v717; // rax
  __int64 v718; // rcx
  __int64 v719; // rax
  __int64 v720; // rdx
  __int64 v721; // rax
  __int64 v722; // rcx
  __int64 v723; // rax
  __int64 v724; // rdx
  __int64 v725; // rax
  __int64 v726; // rcx
  __int64 v727; // rax
  __int64 v728; // rdx
  __int64 v729; // rax
  __int64 v730; // rcx
  __int64 v731; // rax
  __int64 v732; // rdx
  __int64 v733; // rax
  __int64 v734; // rcx
  __int64 v735; // rax
  __int64 v736; // rdx
  __int64 v737; // rax
  __int64 v738; // rcx
  __int64 v739; // rax
  __int64 v740; // rdx
  __int64 v741; // rax
  __int64 v742; // rax
  __int64 *v743; // r8
  __int64 v744; // rdx
  __int64 v745; // rax
  __int64 v746; // rdx
  __int64 v747; // rcx
  __int64 v748; // rcx
  __int64 v749; // rcx
  __int64 v750; // rax
  __int64 v751; // rax
  __int64 v752; // rax
  __int64 v753; // rax
  __int64 v754; // rax
  __int64 v755; // rax
  __int64 v756; // rax
  __int64 v757; // rax
  __int64 v758; // rax
  __int64 v759; // rax
  __int64 v760; // rax
  __int64 v761; // rax
  __int64 v762; // rax
  __int64 v763; // rax
  __int64 v764; // rax
  __int64 v765; // rax
  __int64 v766; // rax
  __int64 v767; // rax
  __int64 v768; // rax
  __int64 v769; // rax
  __int64 v770; // rax
  __int64 v771; // rax
  __int64 v772; // rax
  __int64 v773; // rax
  __int64 v774; // rax
  __int64 v775; // rax
  __int64 v776; // rax
  __int64 v777; // rax
  __int64 v778; // rax
  __int64 v779; // rax
  __int64 v780; // rax
  __int64 v781; // rax
  __int64 v782; // rax
  __int64 v783; // r12
  __int64 v784; // rcx
  __int64 v785; // rbx
  __int64 v786; // r9
  int v787; // eax
  int v788; // r15d
  __int64 v789; // rax
  __int64 v790; // r9
  signed int v791; // eax
  __int64 nn; // r15
  _BYTE *v793; // rax
  __int64 v794; // rcx
  __int64 i1; // rcx
  void *v796; // rbx
  HANDLE v797; // rax
  _BYTE *v798; // rax
  signed int v799; // eax
  int v800; // r15d
  unsigned int v801; // ebx
  unsigned int v802; // r13d
  signed int v803; // r12d
  size_t v804; // rax
  signed int v805; // eax
  int v806; // eax
  unsigned int v807; // ebx
  __int64 v808; // rax
  int v809; // r13d
  int v810; // edi
  int v811; // r12d
  int v812; // eax
  __int64 v813; // rax
  signed int v814; // eax
  void *v815; // rax
  __int64 v816; // rbx
  signed int v817; // eax
  int v818; // eax
  __int64 v819; // rax
  signed int v820; // eax
  signed int v821; // edx
  unsigned int v822; // eax
  int v823; // eax
  unsigned int v824; // r12d
  LPVOID v825; // rbx
  int v826; // ebx
  int v827; // edx
  LPVOID v828; // rbx
  int v829; // ebx
  int v830; // edx
  __int64 v831; // rdx
  __int64 v832; // rbx
  int v833; // eax
  __int64 v834; // rax
  signed int v835; // eax
  signed int v836; // edx
  LPVOID v837; // rbx
  WARBIRD_DELAY_LOAD *v838; // r12
  __int64 v839; // r15
  int v840; // ebx
  int v841; // edx
  int v842; // eax
  int v843; // ebx
  int v844; // r15d
  int v845; // r15d
  __int64 v846; // rax
  int v847; // r15d
  __int64 v848; // rax
  int v849; // edx
  __int64 v850; // rcx
  LPVOID v851; // rbx
  int v852; // eax
  unsigned __int16 *v853; // rbx
  LPVOID v854; // r15
  __int64 v855; // rax
  size_t v856; // rax
  WARBIRD_DELAY_LOAD *v857; // r13
  signed int v858; // r15d
  SIZE_T v859; // rax
  signed int v860; // eax
  size_t v861; // rax
  unsigned int (__fastcall *v862)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v863; // rax
  unsigned int v864; // r13d
  int v865; // r8d
  int v866; // r10d
  int v867; // ecx
  int v868; // r11d
  __int64 v869; // rdx
  int v870; // edi
  int v871; // r9d
  SIZE_T v872; // r8
  char *v873; // r9
  unsigned __int8 *v874; // r11
  _BYTE *v875; // r10
  int i2; // ebx
  int v877; // r9d
  unsigned int v878; // ebx
  LPVOID v879; // rbx
  __int64 v880; // rax
  int v881; // r15d
  int v882; // r13d
  WARBIRD_DELAY_LOAD *v883; // rbx
  SIZE_T v884; // rax
  signed int v885; // eax
  signed int v886; // edi
  size_t v887; // rax
  unsigned int (__fastcall *v888)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v889; // rax
  unsigned int v890; // r12d
  int v891; // r8d
  int v892; // r10d
  int v893; // ecx
  int v894; // r11d
  int v895; // eax
  int v896; // r15d
  int v897; // r13d
  int v898; // r9d
  __int64 v899; // r9
  unsigned int v900; // r12d
  unsigned int v901; // r13d
  SIZE_T v902; // rdx
  char *v903; // r8
  unsigned __int8 *v904; // r11
  char v905; // r14
  _BYTE *v906; // r10
  int i3; // ebx
  int v908; // r9d
  unsigned int v909; // ebx
  LPVOID v910; // r15
  unsigned int *v911; // rbx
  void *v912; // rdi
  char v913; // al
  int v914; // r15d
  int v915; // ebx
  int v916; // edi
  int v917; // r8d
  int v918; // edi
  int v919; // r13d
  __int64 v920; // rax
  __int64 v921; // rax
  int v922; // eax
  SIZE_T v923; // rax
  signed int v924; // eax
  signed int v925; // edi
  LPVOID v926; // r13
  size_t v927; // rax
  unsigned int (__fastcall *v928)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v929; // rax
  unsigned int v930; // r13d
  int v931; // edx
  int v932; // r8d
  int v933; // r9d
  int v934; // ecx
  __int64 v935; // r11
  int v936; // r15d
  int v937; // r10d
  SIZE_T v938; // r8
  char *v939; // r9
  unsigned __int8 *v940; // r11
  _BYTE *v941; // r10
  int i8; // ebx
  int v943; // r9d
  unsigned int v944; // ebx
  LPVOID v945; // rbx
  __int64 v946; // rax
  int v947; // r15d
  size_t v948; // rax
  WARBIRD_DELAY_LOAD *v949; // rbx
  int v950; // r13d
  SIZE_T v951; // rax
  signed int v952; // eax
  signed int v953; // edi
  size_t v954; // rax
  unsigned int (__fastcall *v955)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v956; // rax
  unsigned int v957; // r11d
  int v958; // edx
  int v959; // r9d
  int v960; // ecx
  int v961; // eax
  int v962; // r15d
  int v963; // r8d
  SIZE_T v964; // r8
  __int64 v965; // rcx
  unsigned int v966; // r13d
  char *v967; // r9
  unsigned int v968; // r14d
  unsigned __int8 *v969; // r11
  _BYTE *v970; // r10
  int i9; // ebx
  int v972; // r9d
  unsigned int v973; // r15d
  _BYTE *v974; // rax
  __int64 v975; // rcx
  __int64 i4; // rcx
  void *v977; // rbx
  HANDLE v978; // rax
  _BYTE *v979; // rax
  __int64 v980; // rcx
  __int64 i5; // rcx
  void *v982; // rbx
  HANDLE v983; // rax
  _BYTE *v984; // rbx
  __int64 v985; // rax
  __int64 v986; // rax
  HANDLE v987; // rax
  int v988; // eax
  int v989; // ebx
  int v990; // eax
  size_t v991; // rax
  WCHAR *v992; // r15
  int v993; // edi
  __int64 *v994; // rsi
  int v995; // r9d
  size_t v996; // rbx
  int v997; // r8d
  int v998; // r12d
  __int64 v999; // r14
  int v1000; // eax
  int v1001; // r11d
  int v1002; // r10d
  int v1003; // r11d
  int v1004; // r10d
  unsigned int v1005; // edx
  int v1006; // r8d
  unsigned int v1007; // r9d
  int v1008; // ecx
  int v1009; // edx
  unsigned int v1010; // r8d
  int v1011; // r9d
  int v1012; // ecx
  int v1013; // edx
  unsigned int v1014; // r8d
  int v1015; // ecx
  int v1016; // edx
  unsigned int v1017; // r9d
  unsigned int v1018; // edx
  int v1019; // r8d
  int v1020; // ecx
  unsigned int v1021; // r8d
  int v1022; // edx
  int v1023; // ecx
  int v1024; // r8d
  unsigned int v1025; // edx
  int v1026; // r9d
  int v1027; // ecx
  int v1028; // r8d
  unsigned __int64 v1029; // rax
  __m128 v1030; // xmm2
  __m128 v1031; // xmm1
  __m128 v1032; // xmm0
  __m128 v1033; // xmm1
  __m128 v1034; // xmm1
  __m128 v1035; // xmm1
  __m128 v1036; // xmm1
  char i6; // cl
  __int64 v1038; // rax
  __int64 v1039; // r12
  int v1040; // r13d
  const WCHAR *v1041; // rdi
  __int64 v1042; // rbx
  HMODULE *v1043; // r15
  const WCHAR *v1044; // rdi
  __int64 v1045; // rax
  char *v1046; // rdx
  unsigned int v1047; // eax
  unsigned int v1048; // r15d
  __int64 v1049; // rbx
  void **v1050; // rax
  HANDLE v1051; // rax
  HANDLE v1052; // rax
  HANDLE v1053; // rax
  HANDLE v1054; // rax
  int v1055; // eax
  HANDLE v1056; // rax
  _OWORD *v1057; // rax
  void *v1058; // r15
  HANDLE v1059; // rax
  _QWORD *v1060; // rax
  void *v1061; // r13
  unsigned __int64 v1062; // r12
  unsigned int v1063; // ebx
  HANDLE v1064; // rax
  unsigned int *v1065; // rax
  unsigned int *v1066; // r8
  unsigned int *v1067; // rax
  unsigned int *v1068; // rdi
  int v1069; // ecx
  unsigned int v1070; // eax
  unsigned __int64 v1071; // rdx
  unsigned int *v1072; // rcx
  unsigned int v1073; // edx
  unsigned int v1074; // eax
  unsigned __int64 v1075; // r8
  int v1076; // r13d
  unsigned __int64 *v1077; // rdx
  unsigned int v1078; // ecx
  unsigned int v1079; // eax
  char *v1080; // r8
  unsigned __int64 *v1081; // r8
  _QWORD *v1082; // r12
  HANDLE v1083; // rax
  _DWORD *v1084; // rax
  char *v1085; // r15
  int *v1086; // rax
  unsigned int *v1087; // r13
  size_t v1088; // r8
  SIZE_T v1089; // rbx
  STRSAFE_PCNZWCH v1090; // r8
  unsigned __int8 v1091; // dl
  unsigned __int64 v1092; // rax
  __m128 v1093; // xmm2
  __m128 v1094; // xmm1
  __m128 v1095; // xmm0
  __m128 v1096; // xmm1
  __m128 v1097; // xmm1
  __m128 v1098; // xmm1
  __m128 v1099; // xmm1
  int v1100; // edx
  STRSAFE_PCNZWCH v1101; // rbx
  unsigned __int8 *v1102; // r14
  int v1103; // edi
  unsigned int v1104; // r8d
  int v1105; // r15d
  int v1106; // r13d
  int v1107; // eax
  int v1108; // r11d
  int v1109; // r10d
  int v1110; // r11d
  int v1111; // r10d
  int v1112; // r9d
  int v1113; // edx
  int v1114; // r9d
  int v1115; // r8d
  int v1116; // edx
  unsigned int v1117; // ecx
  int v1118; // eax
  int v1119; // ecx
  int v1120; // edx
  unsigned int v1121; // r8d
  int v1122; // ecx
  unsigned int v1123; // edx
  unsigned int v1124; // r8d
  int v1125; // ecx
  int v1126; // edx
  int v1127; // r8d
  int v1128; // ecx
  int v1129; // edx
  int v1130; // r8d
  int v1131; // r9d
  int v1132; // edx
  unsigned int v1133; // ecx
  int v1134; // edx
  int v1135; // r8d
  unsigned int v1136; // edx
  HANDLE v1137; // rax
  LPVOID v1138; // rbx
  int v1139; // esi
  unsigned int v1140; // esi
  HANDLE v1141; // rax
  void *v1142; // rax
  STRSAFE_PCNZWCH v1143; // rdx
  HANDLE v1144; // rax
  _OWORD *v1145; // rax
  HANDLE v1146; // rax
  _QWORD *v1147; // rax
  HANDLE v1148; // rax
  HANDLE v1149; // rax
  HANDLE v1150; // rax
  HANDLE v1151; // rax
  HANDLE v1152; // rax
  int v1153; // esi
  unsigned int v1154; // ecx
  unsigned int v1155; // edx
  unsigned int v1156; // ecx
  unsigned int v1157; // eax
  unsigned int v1158; // ebx
  HANDLE v1159; // rax
  _DWORD *v1160; // rbx
  _DWORD *v1161; // rsi
  _DWORD *v1162; // rcx
  _DWORD *v1163; // rsi
  _DWORD *v1164; // rcx
  _DWORD *v1165; // rsi
  int v1166; // eax
  unsigned int *v1167; // rdx
  unsigned int *v1168; // rcx
  unsigned int *v1169; // rax
  int v1170; // r14d
  void *v1171; // rsi
  __int64 v1172; // r8
  _DWORD *v1173; // rcx
  unsigned int v1174; // eax
  unsigned int v1175; // r8d
  unsigned int v1176; // eax
  unsigned int v1177; // ebx
  HANDLE v1178; // rax
  void *v1179; // rbx
  int v1180; // eax
  bool v1181; // sf
  FARPROC v1182; // rax
  unsigned int v1183; // edx
  SIZE_T v1184; // r9
  unsigned int *v1185; // rcx
  _DWORD *v1186; // r11
  SIZE_T v1187; // r8
  _DWORD *v1188; // rcx
  unsigned int v1189; // r11d
  unsigned __int64 v1190; // r10
  unsigned int v1191; // ecx
  unsigned int v1192; // r10d
  unsigned int v1193; // ecx
  HANDLE v1194; // rax
  size_t v1195; // rsi
  HANDLE v1196; // rax
  void *v1197; // rax
  SIZE_T v1198; // r8
  HANDLE v1199; // rax
  void *v1200; // rax
  SIZE_T v1201; // r8
  const void *v1202; // rdx
  SIZE_T v1203; // rax
  HANDLE v1204; // rax
  void *v1205; // rax
  _QWORD *v1206; // rbx
  unsigned __int16 *v1207; // rax
  HANDLE v1208; // rax
  HANDLE v1209; // rax
  HANDLE v1210; // rax
  HANDLE v1211; // rax
  SIZE_T *v1212; // rax
  SIZE_T v1213; // r8
  void *v1214; // rdx
  int v1215; // ecx
  wchar_t *v1216; // rbx
  HANDLE v1217; // rax
  HANDLE v1218; // rax
  HANDLE v1219; // rax
  HANDLE v1220; // rax
  int v1221; // ecx
  __int64 v1222; // rcx
  SIZE_T v1223; // rbx
  const wchar_t *v1224; // rax
  unsigned __int8 *v1225; // rdx
  unsigned int v1226; // r10d
  unsigned int v1227; // r9d
  int v1228; // eax
  char v1229; // r11
  char v1230; // cl
  int v1231; // r11d
  int v1232; // ecx
  int v1233; // eax
  _BYTE *v1234; // r8
  int v1235; // ecx
  int v1236; // r9d
  char v1237; // r11
  size_t v1238; // r14
  int v1239; // r8d
  int v1240; // r15d
  size_t v1241; // rsi
  unsigned int v1242; // r13d
  int v1243; // r9d
  int v1244; // r12d
  int v1245; // r10d
  int v1246; // edi
  int v1247; // ebx
  int v1248; // r11d
  int v1249; // edx
  int v1250; // r8d
  unsigned int v1251; // ecx
  int v1252; // edx
  int v1253; // r8d
  unsigned int v1254; // ecx
  int v1255; // edx
  int v1256; // r9d
  int v1257; // r10d
  unsigned int v1258; // r8d
  int v1259; // ecx
  int v1260; // edx
  unsigned int v1261; // r8d
  int v1262; // ecx
  int v1263; // edx
  int v1264; // r8d
  int v1265; // ecx
  int v1266; // edx
  int v1267; // r8d
  int v1268; // ecx
  int v1269; // edx
  unsigned int v1270; // r8d
  int v1271; // ecx
  int v1272; // edx
  int v1273; // edx
  int v1274; // r8d
  wchar_t *v1275; // r14
  unsigned __int64 v1276; // rax
  __m128 v1277; // xmm1
  __m128 v1278; // xmm2
  __m128 v1279; // xmm0
  __m128 v1280; // xmm0
  __m128 v1281; // xmm1
  __m128 v1282; // xmm1
  __m128 v1283; // xmm1
  __m128 v1284; // xmm1
  unsigned __int8 i7; // cl
  _DWORD *v1286; // rdx
  STRSAFE_PCNZWCH v1287; // r14
  __int64 v1288; // r9
  unsigned __int64 v1289; // r8
  SIZE_T v1290; // r10
  int v1291; // ebx
  STRSAFE_PCNZWCH v1292; // rcx
  unsigned int v1293; // eax
  char *v1294; // rdx
  void *v1295; // rax
  HANDLE v1296; // rax
  int v1297; // r14d
  HANDLE v1298; // rax
  HANDLE v1299; // rax
  HANDLE v1300; // rax
  void *v1301; // rbx
  HANDLE v1302; // rax
  void *v1303; // rbx
  HANDLE v1304; // rax
  void *v1305; // rbx
  HANDLE v1306; // rax
  HANDLE v1307; // rax
  HANDLE v1308; // rax
  HANDLE v1309; // rax
  _QWORD *v1310; // rbx
  void *v1311; // rsi
  HANDLE v1312; // rax
  void *v1313; // rsi
  HANDLE v1314; // rax
  void *v1315; // rsi
  HANDLE v1316; // rax
  HANDLE v1317; // rax
  void *v1318; // rbx
  HANDLE v1319; // rax
  HANDLE v1320; // rax
  HANDLE v1321; // rax
  void *v1322; // rbx
  HANDLE v1323; // rax
  HANDLE v1324; // rax
  HANDLE v1325; // rax
  unsigned int v1326; // ebx
  int v1327; // eax
  unsigned int v1329; // [rsp+60h] [rbp-A0h]
  int v1330; // [rsp+68h] [rbp-98h]
  unsigned int v1331; // [rsp+68h] [rbp-98h]
  int v1332; // [rsp+68h] [rbp-98h]
  int v1333; // [rsp+68h] [rbp-98h]
  unsigned int v1334; // [rsp+70h] [rbp-90h]
  int v1335; // [rsp+70h] [rbp-90h]
  signed int v1336; // [rsp+70h] [rbp-90h]
  signed int v1337; // [rsp+70h] [rbp-90h]
  int v1338; // [rsp+70h] [rbp-90h]
  signed int v1339; // [rsp+70h] [rbp-90h]
  int v1340; // [rsp+70h] [rbp-90h]
  int v1341; // [rsp+70h] [rbp-90h]
  int v1342; // [rsp+70h] [rbp-90h]
  int v1343; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v1344; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1345; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1346; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1347; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1348; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1349; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1350; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1351; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1352; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1353; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1354; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1355; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1356; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1357; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1358; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1359; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1360; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1361; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1362; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1363; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1364; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1365; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1366; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1367; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1368; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1369; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1370; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1371; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1372; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1373; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1374; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1375; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1376; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1377; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1378; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1379; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1380; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1381; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v1382; // [rsp+78h] [rbp-88h]
  unsigned int v1383; // [rsp+7Ch] [rbp-84h]
  int v1384; // [rsp+80h] [rbp-80h]
  int v1385; // [rsp+80h] [rbp-80h]
  int v1386; // [rsp+80h] [rbp-80h]
  int v1387; // [rsp+80h] [rbp-80h]
  unsigned int v1388; // [rsp+80h] [rbp-80h]
  unsigned int v1389; // [rsp+80h] [rbp-80h]
  int v1390; // [rsp+80h] [rbp-80h]
  int v1391; // [rsp+80h] [rbp-80h]
  int v1392; // [rsp+80h] [rbp-80h]
  signed int v1393; // [rsp+80h] [rbp-80h]
  int v1394; // [rsp+80h] [rbp-80h]
  unsigned int v1395; // [rsp+80h] [rbp-80h]
  unsigned __int8 v1396; // [rsp+80h] [rbp-80h]
  size_t Size; // [rsp+88h] [rbp-78h]
  unsigned int v1398; // [rsp+90h] [rbp-70h]
  unsigned int v1399; // [rsp+94h] [rbp-6Ch]
  unsigned int v1400; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  SIZE_T v1402; // [rsp+A8h] [rbp-58h]
  void *v1403; // [rsp+B0h] [rbp-50h]
  SIZE_T v1404; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v1406; // [rsp+C8h] [rbp-38h]
  int v1407; // [rsp+D0h] [rbp-30h]
  size_t pcchLength; // [rsp+D8h] [rbp-28h] BYREF
  void *v1409; // [rsp+E0h] [rbp-20h]
  SIZE_T v1410; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int *v1411; // [rsp+F0h] [rbp-10h] BYREF
  void *v1412; // [rsp+F8h] [rbp-8h]
  LPVOID v1413; // [rsp+100h] [rbp+0h]
  LPVOID v1414; // [rsp+108h] [rbp+8h] BYREF
  _DWORD *v1415; // [rsp+110h] [rbp+10h]
  unsigned __int64 v1416; // [rsp+118h] [rbp+18h]
  size_t v1417; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v1418; // [rsp+128h] [rbp+28h]
  int v1419; // [rsp+130h] [rbp+30h]
  int v1420; // [rsp+134h] [rbp+34h]
  STRSAFE_PCNZWCH psz; // [rsp+138h] [rbp+38h]
  unsigned int *v1422; // [rsp+140h] [rbp+40h]
  int v1423; // [rsp+148h] [rbp+48h]
  unsigned int v1424; // [rsp+14Ch] [rbp+4Ch] BYREF
  __int128 v1425; // [rsp+150h] [rbp+50h]
  SIZE_T dwBytes; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v1427; // [rsp+168h] [rbp+68h]
  __int64 v1428; // [rsp+170h] [rbp+70h]
  LPVOID v1429; // [rsp+178h] [rbp+78h]
  unsigned int v1430; // [rsp+180h] [rbp+80h] BYREF
  _DWORD v1431[3]; // [rsp+184h] [rbp+84h] BYREF
  _OWORD v1432[3]; // [rsp+190h] [rbp+90h] BYREF
  int v1433; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD *v1434; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE *v1435; // [rsp+1D0h] [rbp+D0h] BYREF
  HMODULE phModule; // [rsp+1D8h] [rbp+D8h] BYREF
  HMODULE hModule; // [rsp+1E0h] [rbp+E0h] BYREF
  void *v1438; // [rsp+1E8h] [rbp+E8h]
  _QWORD v1439[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v1440; // [rsp+200h] [rbp+100h]
  unsigned int v1441; // [rsp+204h] [rbp+104h]
  __int64 v1442; // [rsp+208h] [rbp+108h]
  _QWORD v1443[2]; // [rsp+210h] [rbp+110h] BYREF
  int v1444; // [rsp+220h] [rbp+120h]
  unsigned int v1445; // [rsp+224h] [rbp+124h]
  __int64 v1446; // [rsp+228h] [rbp+128h]
  __int64 v1447; // [rsp+230h] [rbp+130h] BYREF
  __int64 v1448; // [rsp+238h] [rbp+138h] BYREF
  DWORD *v1449; // [rsp+240h] [rbp+140h]
  __int128 v1450; // [rsp+250h] [rbp+150h] BYREF
  __int64 v1451; // [rsp+260h] [rbp+160h] BYREF
  __int64 v1452; // [rsp+268h] [rbp+168h] BYREF
  __int64 v1453; // [rsp+270h] [rbp+170h] BYREF
  _QWORD v1454[32]; // [rsp+280h] [rbp+180h]
  LPVOID v1455[2]; // [rsp+380h] [rbp+280h]
  LPVOID v1456[2]; // [rsp+390h] [rbp+290h]
  __int128 v1457; // [rsp+3A0h] [rbp+2A0h]
  __int128 v1458; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int128 v1459; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v1460; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int128 v1461; // [rsp+3E0h] [rbp+2E0h]
  int v1462; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int128 v1463; // [rsp+3F4h] [rbp+2F4h]
  __int128 v1464; // [rsp+404h] [rbp+304h]
  __int128 v1465; // [rsp+414h] [rbp+314h]
  __int128 v1466; // [rsp+424h] [rbp+324h]
  __int128 v1467; // [rsp+434h] [rbp+334h]
  __int128 v1468; // [rsp+444h] [rbp+344h]
  int v1469; // [rsp+454h] [rbp+354h]
  int v1470; // [rsp+460h] [rbp+360h] BYREF
  __int128 v1471; // [rsp+464h] [rbp+364h]
  __int128 v1472; // [rsp+474h] [rbp+374h]
  __int128 v1473; // [rsp+484h] [rbp+384h]
  __int128 v1474; // [rsp+494h] [rbp+394h]
  __int128 v1475; // [rsp+4A4h] [rbp+3A4h]
  __int128 v1476; // [rsp+4B4h] [rbp+3B4h]
  int v1477; // [rsp+4C4h] [rbp+3C4h]
  int v1478; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int128 v1479; // [rsp+4D4h] [rbp+3D4h]
  __int128 v1480; // [rsp+4E4h] [rbp+3E4h]
  __int128 v1481; // [rsp+4F4h] [rbp+3F4h]
  __int128 v1482; // [rsp+504h] [rbp+404h]
  __int128 v1483; // [rsp+514h] [rbp+414h]
  __int128 v1484; // [rsp+524h] [rbp+424h]
  int v1485; // [rsp+534h] [rbp+434h]
  int v1486; // [rsp+540h] [rbp+440h] BYREF
  __int128 v1487; // [rsp+544h] [rbp+444h]
  __int128 v1488; // [rsp+554h] [rbp+454h]
  __int128 v1489; // [rsp+564h] [rbp+464h]
  __int128 v1490; // [rsp+574h] [rbp+474h]
  __int128 v1491; // [rsp+584h] [rbp+484h]
  __int128 v1492; // [rsp+594h] [rbp+494h]
  int v1493; // [rsp+5A4h] [rbp+4A4h]
  int v1494; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int128 v1495; // [rsp+5B4h] [rbp+4B4h]
  __int128 v1496; // [rsp+5C4h] [rbp+4C4h]
  __int128 v1497; // [rsp+5D4h] [rbp+4D4h]
  __int128 v1498; // [rsp+5E4h] [rbp+4E4h]
  __int128 v1499; // [rsp+5F4h] [rbp+4F4h]
  __int128 v1500; // [rsp+604h] [rbp+504h]
  int v1501; // [rsp+614h] [rbp+514h]
  int v1502; // [rsp+620h] [rbp+520h] BYREF
  __int128 v1503; // [rsp+624h] [rbp+524h]
  __int128 v1504; // [rsp+634h] [rbp+534h]
  __int128 v1505; // [rsp+644h] [rbp+544h]
  __int128 v1506; // [rsp+654h] [rbp+554h]
  __int128 v1507; // [rsp+664h] [rbp+564h]
  __int128 v1508; // [rsp+674h] [rbp+574h]
  int v1509; // [rsp+684h] [rbp+584h]
  int v1510; // [rsp+690h] [rbp+590h] BYREF
  __int128 v1511; // [rsp+694h] [rbp+594h]
  __int128 v1512; // [rsp+6A4h] [rbp+5A4h]
  __int128 v1513; // [rsp+6B4h] [rbp+5B4h]
  __int128 v1514; // [rsp+6C4h] [rbp+5C4h]
  __int128 v1515; // [rsp+6D4h] [rbp+5D4h]
  __int128 v1516; // [rsp+6E4h] [rbp+5E4h]
  int v1517; // [rsp+6F4h] [rbp+5F4h]
  int v1518; // [rsp+700h] [rbp+600h] BYREF
  __int128 v1519; // [rsp+704h] [rbp+604h]
  __int128 v1520; // [rsp+714h] [rbp+614h]
  __int128 v1521; // [rsp+724h] [rbp+624h]
  __int128 v1522; // [rsp+734h] [rbp+634h]
  __int128 v1523; // [rsp+744h] [rbp+644h]
  __int128 v1524; // [rsp+754h] [rbp+654h]
  int v1525; // [rsp+764h] [rbp+664h]
  int v1526; // [rsp+770h] [rbp+670h] BYREF
  __int128 v1527; // [rsp+774h] [rbp+674h]
  __int128 v1528; // [rsp+784h] [rbp+684h]
  __int128 v1529; // [rsp+794h] [rbp+694h]
  __int128 v1530; // [rsp+7A4h] [rbp+6A4h]
  __int128 v1531; // [rsp+7B4h] [rbp+6B4h]
  __int128 v1532; // [rsp+7C4h] [rbp+6C4h]
  int v1533; // [rsp+7D4h] [rbp+6D4h]
  __int128 v1534; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int128 v1535; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int128 v1536; // [rsp+800h] [rbp+700h] BYREF
  __int128 v1537; // [rsp+810h] [rbp+710h] BYREF
  __int64 v1538; // [rsp+820h] [rbp+720h] BYREF
  int v1539; // [rsp+828h] [rbp+728h]
  int v1540; // [rsp+82Ch] [rbp+72Ch]
  _DWORD v1541[12]; // [rsp+830h] [rbp+730h] BYREF
  __int128 v1542; // [rsp+860h] [rbp+760h] BYREF
  __int128 v1543; // [rsp+870h] [rbp+770h] BYREF
  __int64 v1544; // [rsp+880h] [rbp+780h]
  __int128 v1545; // [rsp+888h] [rbp+788h] BYREF
  _OWORD v1546[2]; // [rsp+898h] [rbp+798h] BYREF
  __int128 v1547; // [rsp+8B8h] [rbp+7B8h] BYREF
  _OWORD v1548[2]; // [rsp+8C8h] [rbp+7C8h] BYREF
  __int128 v1549; // [rsp+8E8h] [rbp+7E8h] BYREF
  _OWORD v1550[2]; // [rsp+8F8h] [rbp+7F8h] BYREF
  __int128 v1551; // [rsp+918h] [rbp+818h] BYREF
  _OWORD v1552[2]; // [rsp+928h] [rbp+828h] BYREF
  __int128 v1553; // [rsp+948h] [rbp+848h] BYREF
  __int128 v1554; // [rsp+958h] [rbp+858h] BYREF
  __int64 v1555; // [rsp+968h] [rbp+868h]
  _OWORD v1556[2]; // [rsp+970h] [rbp+870h] BYREF
  __int128 v1557; // [rsp+990h] [rbp+890h] BYREF
  unsigned __int16 v1558[8]; // [rsp+9A0h] [rbp+8A0h] BYREF
  __int128 v1559; // [rsp+9B0h] [rbp+8B0h]
  __int128 v1560; // [rsp+9C0h] [rbp+8C0h]
  _OWORD v1561[2]; // [rsp+9D0h] [rbp+8D0h]
  __int128 v1562; // [rsp+9F0h] [rbp+8F0h] BYREF
  unsigned __int16 v1563[8]; // [rsp+A00h] [rbp+900h] BYREF
  __int128 v1564; // [rsp+A10h] [rbp+910h]
  __int128 v1565; // [rsp+A20h] [rbp+920h]
  _OWORD v1566[2]; // [rsp+A30h] [rbp+930h]
  __int128 v1567; // [rsp+A50h] [rbp+950h] BYREF
  unsigned __int16 v1568[8]; // [rsp+A60h] [rbp+960h] BYREF
  __int128 v1569; // [rsp+A70h] [rbp+970h]
  __int128 v1570; // [rsp+A80h] [rbp+980h]
  _BYTE v1571[28]; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v1572[68]; // [rsp+AB0h] [rbp+9B0h] BYREF
  __int16 v1573; // [rsp+AF4h] [rbp+9F4h]
  unsigned __int16 v1574; // [rsp+B56h] [rbp+A56h]
  int v1575; // [rsp+B5Ch] [rbp+A5Ch]
  unsigned int v1576; // [rsp+B60h] [rbp+A60h]
  int v1577; // [rsp+B90h] [rbp+A90h] BYREF
  __int128 v1578; // [rsp+B98h] [rbp+A98h]
  __int128 v1579; // [rsp+BA8h] [rbp+AA8h]
  __int128 v1580; // [rsp+BB8h] [rbp+AB8h]
  __int64 v1581; // [rsp+BC8h] [rbp+AC8h]
  _BYTE v1582[176]; // [rsp+BD0h] [rbp+AD0h] BYREF
  WCHAR Filename; // [rsp+C80h] [rbp+B80h] BYREF

  v1449 = pdwValue;
  psz = pwszValueName;
  v1434 = 0;
  if ( pwszValueName && pdwValue )
  {
    v1399 = 0;
    *(_QWORD *)&v1431[1] = 0;
    while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
      ;
    v1423 = -1;
    if ( g_WarbirdSecureFunctionsRefCount )
    {
LABEL_53:
      ++g_WarbirdSecureFunctionsRefCount;
    }
    else
    {
      v3 = (char *)MemoryAllocT<unsigned long>(824);
      lpMem = v3;
      v4 = (WCHAR *)v3;
      if ( v3 )
      {
        v5 = 0;
        v6 = qword_18009D240;
        v7 = 0;
        v8 = -1;
        v9 = 0;
        v10 = v3;
        v11 = 103;
        do
        {
          v12 = *((unsigned __int8 *)v6 + 1);
          v13 = *(unsigned __int8 *)v6;
          v14 = *((unsigned __int8 *)v6++ + 4);
          v15 = *((unsigned __int8 *)v6 - 5) | ((*((unsigned __int8 *)v6 - 6) | ((v12 | (v13 << 8)) << 8)) << 8);
          v16 = v9 ^ v15;
          v17 = *((unsigned __int8 *)v6 - 1)
              | ((*((unsigned __int8 *)v6 - 2) | ((*((unsigned __int8 *)v6 - 3) | (v14 << 8)) << 8)) << 8);
          v18 = v7 ^ v17 ^ v9 ^ v15 ^ 0xAC987321;
          v19 = v16 ^ (__ROR4__(v18, 22) + 4991 * __ROR4__(v18 + 1419157410, 27));
          v20 = v18 ^ (43881 * __ROR4__(v19 + 133239679, 9) - __ROR4__(v19, 30));
          v21 = v19 ^ (24670 * v20 - (v20 >> 13) - 123127970);
          v22 = v20 ^ (2033 * __ROR4__(v21 ^ 0xAB69, 26) - __ROR4__(v21, 30));
          v23 = v21 ^ (133239679 - (v22 ^ 0xAB69605E));
          v24 = v22 ^ (43881 * (v23 ^ 0x137F)) ^ __ROR4__(v23, 6);
          v25 = v23 ^ (__ROR4__(v24, 30) + 24670 * __ROR4__(v24 + 133239679, 15));
          v26 = v24 ^ (2033 * __ROR4__(v25 + 1419157410, 14) - __ROR4__(v25, 24));
          v27 = v25 ^ __ROR4__(v26, 10) ^ (4991 * __ROR4__(v26 ^ 0xAB69605E, 12));
          v28 = v26 ^ (v27 >> 10) ^ (43881 * (v27 ^ 0x7F1));
          v29 = v27 ^ (2033 * (__ROR4__(~v28, 5) + 24670));
          v30 = v29 ^ (((v28 ^ (v29 - 2033) ^ 0xAB69605E) >> 2) + 4991 * __ROR4__(v28 ^ (v29 - 2033) ^ 0xAB6967AF, 30));
          v31 = v28 ^ (v29 - 2033) ^ 0xAB69605E ^ (__ROR4__(v30, 25) + 43881 * __ROR4__(v30 - 133239679, 6));
          v32 = v30 ^ (24670 * (v31 ^ 0x137F) + __ROR4__(v31, 9));
          v33 = v31 ^ (__ROR4__(v32, 25) + 2033 * __ROR4__(v32 ^ 0xAB69, 27));
          v34 = v32 ^ v33 ^ 0xAC987321;
          v35 = v33 ^ (4991 * __ROR4__(v34, 3) - 219010071);
          v36 = v34 ^ (24670 * __ROR4__(v35 - 133239679, 1) - __ROR4__(v35, 6));
          v37 = v35 ^ (__ROR4__(v36, 18) + 2033 * __ROR4__(v36 - 1419157410, 29));
          v10 += 8;
          v38 = v36 ^ (4991 * __ROR4__(v37 - 1419157410, 17) - __ROR4__(v37, 14));
          v39 = v37 ^ (v38 >> 3) ^ (43881 * (v38 ^ 0x605E));
          v40 = __ROR4__(v39, 30);
          v7 = v8 ^ v39;
          v8 = v17;
          v9 = v5 ^ v38 ^ v40 ^ (24670 * __ROR4__(v37 ^ (v38 >> 3) ^ (43881 * (v38 ^ 0x605E)) ^ 0x7F1137F, 28));
          v5 = v15;
          *(v10 - 5) = v9;
          *(v10 - 1) = v7;
          *(v10 - 6) = __ROR4__(v9, 8);
          *(v10 - 2) = __ROR4__(v7, 8);
          *(v10 - 7) = __ROR4__(v9, 16);
          *(v10 - 3) = __ROR4__(v7, 16);
          *(v10 - 8) = __ROR4__(v9, 24);
          *(v10 - 4) = __ROR4__(v7, 24);
          --v11;
        }
        while ( v11 );
        v41 = 0;
        v42 = 0;
        v43 = 0;
        do
        {
          v42 = _mm_xor_ps(v42, (__m128)_mm_loadu_si128((const __m128i *)((char *)v4 + v41)));
          v44 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v4 + v41 + 16));
          v41 += 32LL;
          v43 = _mm_xor_ps(v43, v44);
        }
        while ( v41 < 0x320 );
        v45 = _mm_xor_ps(v43, v42);
        v46 = _mm_xor_ps(v45, (__m128)_mm_srli_si128((__m128i)v45, 8));
        v47 = _mm_xor_ps(v46, (__m128)_mm_srli_si128((__m128i)v46, 4));
        v48 = _mm_xor_ps(v47, (__m128)_mm_srli_si128((__m128i)v47, 2));
        for ( i = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v48, (__m128)_mm_srli_si128((__m128i)v48, 1))); v41 < 0x338; ++v41 )
          i ^= *((_BYTE *)v4 + v41);
        if ( i == 64 )
        {
          v50 = 0;
          *((_BYTE *)v4 + 823) = 0;
          v51 = 0;
          v52 = 0;
          v1384 = 0;
          *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
          j = v4;
          xmmword_1800AD870 = 0;
          xmmword_1800AD880 = 0;
          *(_OWORD *)&hLibModule = 0;
          xmmword_1800AD8A0 = 0;
          xmmword_1800AD8B0 = 0;
          if ( *(_BYTE *)v4 )
          {
            while ( 1 )
            {
              v54 = -1;
              do
                v55 = j[++v54] == 0;
              while ( !v55 );
              v56 = 24 * v50;
              v57 = &WARBIRD::g_arModuleInfo + 3 * v50;
              if ( !GetModuleHandleExW(0, j, v57) )
                break;
              v58 = &j[v54];
              if ( *(_WORD *)*v57 == 23117 )
              {
                v59 = *((int *)*v57 + 15);
                if ( (unsigned int)v59 < 0x10000000 )
                {
                  v60 = (char *)*v57 + v59;
                  if ( v60 >= (char *)*v57 )
                  {
                    if ( *(_DWORD *)v60 == 17744 )
                    {
                      if ( ((*((_WORD *)v60 + 12) - 267) & 0xFEFF) != 0 )
                      {
                        v52 = -1073741811;
                      }
                      else
                      {
                        v52 = 0;
                        *(HMODULE *)((char *)&WARBIRD::g_arModuleInfo + v56 + 12) = (HMODULE)*((_QWORD *)v60 + 17);
                        *(_DWORD *)((char *)&WARBIRD::g_arModuleInfo + v56 + 8) = *((_DWORD *)v60 + 20);
                      }
                    }
                    else
                    {
                      v52 = -1073741701;
                    }
                  }
                  else
                  {
                    v52 = -1073741701;
                  }
                }
                else
                {
                  v52 = -1073741701;
                }
              }
              else
              {
                v52 = -1073741701;
              }
              v61 = *(_DWORD *)(v58 + 1);
              v62 = 0;
              for ( j = v58 + 3; v62 < v61; ++v62 )
              {
                v63 = -1;
                do
                  ++v63;
                while ( *((_BYTE *)j + v63) );
                if ( v52 >= 0 )
                {
                  ProcAddress = (void **)GetProcAddress(*v57, (LPCSTR)j);
                  if ( !ProcAddress )
                  {
                    ProcessHeap = GetProcessHeap();
                    HeapFree(ProcessHeap, 0, lpMem);
                    goto LABEL_53;
                  }
                  (&WARBIRD::g_FuncAddress)[v51] = ProcAddress;
                }
                v51 = (unsigned int)(v51 + 1);
                j = (const WCHAR *)((char *)j + v63 + 1);
              }
              v50 = (unsigned int)++v1384;
              if ( !*(_BYTE *)j )
              {
                v4 = (WCHAR *)lpMem;
                goto LABEL_39;
              }
            }
            v67 = GetProcessHeap();
            HeapFree(v67, 0, lpMem);
          }
          else
          {
LABEL_39:
            v65 = GetProcessHeap();
            HeapFree(v65, 0, v4);
            if ( v52 >= 0 )
              goto LABEL_53;
          }
        }
        else
        {
          v68 = GetProcessHeap();
          HeapFree(v68, 0, v4);
        }
      }
      if ( WARBIRD::g_arModuleInfo )
        FreeLibrary(WARBIRD::g_arModuleInfo);
      if ( *((_QWORD *)&xmmword_1800AD870 + 1) )
        FreeLibrary(*((HMODULE *)&xmmword_1800AD870 + 1));
      if ( hLibModule )
        FreeLibrary(hLibModule);
      if ( *((_QWORD *)&xmmword_1800AD8A0 + 1) )
        FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0 + 1));
      qword_1800AC100 = 0;
      WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC070[0] = CIVIAudioFilter::IsDirty;
      off_1800AC078 = CIVIAudioFilter::IsDirty;
      off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0B0 = CIVIAudioFilter::IsDirty;
      off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
      off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC108 = CIVIAudioFilter::IsDirty;
      off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC138 = CIVIAudioFilter::IsDirty;
      off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
      xmmword_1800AD870 = 0;
      xmmword_1800AD880 = 0;
      *(_OWORD *)&hLibModule = 0;
      xmmword_1800AD8A0 = 0;
      xmmword_1800AD8B0 = 0;
      off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC170[0] = CIVIAudioFilter::IsDirty;
      off_1800AC178[0] = CIVIAudioFilter::IsDirty;
      off_1800AC180 = CIVIAudioFilter::IsDirty;
      off_1800AC188 = CIVIAudioFilter::IsDirty;
      off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
      off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
    }
    v69 = 0;
    _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
    v70 = 0;
    v71 = 0;
    if ( NtCurrentPeb()->SessionId )
    {
      v72 = ((__int64 (*)(void))off_1800AC140[0])();
      if ( !v72 )
      {
        GetLastError();
        goto LABEL_119;
      }
      v73 = 0;
      LODWORD(v1406) = 0;
      v74 = 0;
      LODWORD(dwBytes) = 0;
      while ( 1 )
      {
        if ( ((unsigned int (__fastcall *)(__int64, __int64, void *, __int64, SIZE_T *))off_1800AC160[0])(
               v72,
               2,
               v73,
               v74,
               &dwBytes) )
        {
          v69 = v73;
          goto LABEL_73;
        }
        LastError = GetLastError();
        v76 = LastError;
        if ( LastError != 122 )
          break;
        if ( v73 )
        {
          v76 = -2147467259;
          goto LABEL_69;
        }
        v77 = dwBytes;
        v78 = GetProcessHeap();
        v73 = HeapAlloc(v78, 0, v77);
        if ( !v73 )
        {
LABEL_85:
          v76 = -2147024882;
          goto LABEL_116;
        }
        v74 = (unsigned int)dwBytes;
      }
      if ( LastError )
      {
        if ( LastError > 0 )
          v76 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v76 = -2147467259;
      }
      if ( v73 )
      {
LABEL_69:
        v79 = GetProcessHeap();
        HeapFree(v79, 0, v73);
      }
      if ( v76 < 0 )
      {
LABEL_116:
        if ( v69 )
        {
          v97 = GetProcessHeap();
          HeapFree(v97, 0, v69);
        }
        if ( v76 < 0 )
LABEL_119:
          LODWORD(v1406) = 0;
        v98 = LocalAlloc(0x40u, 4u);
        SP_HLOCAL<unsigned char>::operator=(&v1431[1], v98);
        v1438 = *(void **)&v1431[1];
        if ( !*(_QWORD *)&v1431[1] )
        {
          v2 = -2147024882;
          goto LABEL_1743;
        }
        v99 = 0;
        v1329 = 0;
        v100 = GetProcessHeap();
        v101 = HeapAlloc(v100, 8u, 0xA0u);
        Src = v101;
        v102 = v101;
        if ( !v101 )
        {
          v102 = 0;
          v1330 = -1073741801;
          goto LABEL_517;
        }
        v103 = 0;
        *v101 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
        v101[1] = xmmword_1800AD470;
        v101[2] = xmmword_1800AD480;
        v101[3] = xmmword_1800AD490;
        v101[4] = xmmword_1800AD4A0;
        v101[5] = xmmword_1800AD4B0;
        v101[6] = xmmword_1800AD4C0;
        v101[7] = xmmword_1800AD4D0;
        v101[8] = xmmword_1800AD4E0;
        v101[9] = xmmword_1800AD4F0;
        v104 = GetProcessHeap();
        v105 = HeapAlloc(v104, 8u, 8u);
        if ( !v105 )
        {
          v1330 = -1073741801;
          goto LABEL_518;
        }
        v99 = v105;
        *v105 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
        v1403 = v105;
        v1404 = __rdtsc();
        pcchLength = 0;
        if ( StringCchLengthW(psz, (unsigned __int64)HIDWORD(v1404) << 32, &pcchLength) < 0 )
        {
          v1330 = -1073741762;
          goto LABEL_518;
        }
        v107 = 2 * pcchLength + 6;
        if ( v107 < 4 )
        {
          v1330 = -1073741675;
          goto LABEL_518;
        }
        v108 = v106 + v107;
        if ( v108 < v106 || v108 + 8 < v108 || (v109 = v108 + 16, (unsigned int)v109 < v108 + 8) )
        {
          v1330 = -805306219;
          goto LABEL_518;
        }
        v1409 = 0;
        pcchLength = 0;
        v110 = GetProcessHeap();
        v111 = HeapAlloc(v110, 8u, (unsigned int)v109);
        v112 = v111;
        if ( !v111 )
        {
          v1330 = -1073741801;
          goto LABEL_512;
        }
        v113 = v111 + 1;
        if ( v113 < v112 )
        {
          v1330 = -1073741675;
LABEL_504:
          v1409 = v112;
          goto LABEL_505;
        }
        if ( v112 + 2 > (_DWORD *)((char *)v112 + v109) )
        {
          v1330 = -1073741789;
          goto LABEL_504;
        }
        v114 = 4;
        *v112 = 4;
        *v113 = 0;
        v115 = 0;
        v1409 = v112;
        v116 = (char *)v112;
        do
        {
          v117 = *v112 + 4;
          if ( v117 < 4 )
            goto LABEL_146;
          v118 = (unsigned __int64)v112 + v117;
          if ( v118 < (unsigned __int64)v112 )
            goto LABEL_146;
          ++v115;
          v112 = (_DWORD *)((char *)v112 + v117);
        }
        while ( !v115 );
        v119 = (void *)(v118 + 4);
        if ( v118 + 4 < v118 )
          goto LABEL_146;
        v120 = 160;
        v121 = v109;
        Size = (unsigned int)v109;
        if ( v112 + 41 > (_DWORD *)&v116[v109] )
        {
          v1330 = -1073741789;
          goto LABEL_505;
        }
        v122 = Src;
        *v112 = 160;
        if ( v122 )
        {
          memcpy_0(v119, v122, 0xA0u);
          v121 = Size;
        }
        v123 = v1403;
        if ( !v1403 )
        {
          v1330 = -1073741811;
          v1409 = v116;
          v1403 = 0;
          Src = v122;
          goto LABEL_505;
        }
        v1409 = v116;
        Src = v122;
        if ( v116 )
        {
          v124 = v116;
          for ( k = 0; k < 2; ++k )
          {
            v126 = *v124 + 4;
            if ( v126 < 4 )
              goto LABEL_146;
            v127 = (unsigned __int64)v124 + v126;
            if ( v127 < (unsigned __int64)v124 )
              goto LABEL_146;
            v124 = (_DWORD *)((char *)v124 + v126);
          }
          if ( v127 + 4 < v127 )
          {
            v1330 = -1073741675;
            v1409 = v116;
            Src = v122;
            goto LABEL_505;
          }
          if ( v124 + 3 > (_DWORD *)&v116[v121] )
          {
            v1330 = -1073741789;
            v1409 = v116;
            Src = v122;
            goto LABEL_505;
          }
          *v124 = 8;
          if ( v123 )
          {
            memcpy_0((void *)(v127 + 4), v123, 8u);
            v121 = Size;
            v123 = v1403;
          }
          v120 = (size_t)v116;
          v1409 = v116;
          v128 = 0;
          v1403 = v123;
          Src = v122;
          do
          {
            v129 = *(_DWORD *)v120 + 4;
            if ( *(_DWORD *)v120 >= 0xFFFFFFFC )
              goto LABEL_146;
            v130 = v120 + v129;
            if ( v130 < v120 )
              goto LABEL_146;
            ++v128;
            v120 += v129;
          }
          while ( v128 < 3 );
          v131 = (SIZE_T *)(v130 + 4);
          v1409 = v116;
          v1403 = v123;
          Src = v122;
          if ( (unsigned __int64)v131 >= v120 )
          {
            if ( v120 + 12 <= (unsigned __int64)&v116[v121] )
            {
              v132 = v1404;
              v114 = 4;
              *(_DWORD *)v120 = 8;
              *v131 = v132;
              goto LABEL_164;
            }
            v1330 = -1073741789;
            goto LABEL_505;
          }
LABEL_146:
          v1330 = -1073741675;
          goto LABEL_505;
        }
        if ( v121 + 12 < v121 )
          goto LABEL_146;
        Size = v121 + 24;
        if ( (unsigned int)Size < v121 + 12 )
          goto LABEL_146;
LABEL_164:
        v133 = psz;
        v1417 = 0;
        if ( StringCchLengthW(psz, v120, &v1417) < 0 )
        {
          v1330 = -1073741762;
          goto LABEL_505;
        }
        if ( v1417 + 1 < v1417 )
          goto LABEL_146;
        v135 = (unsigned int)(2 * (v1417 + 1));
        if ( (_DWORD)v135 )
        {
          if ( v116 )
          {
            v139 = 0;
            v140 = v116;
            do
            {
              v141 = *v140 + 4;
              if ( *v140 >= 0xFFFFFFFC || (_DWORD *)((char *)v140 + v141) < v140 )
                goto LABEL_173;
              ++v139;
              v140 = (_DWORD *)((char *)v140 + v141);
            }
            while ( v139 < 4 );
            if ( v140 + 1 < v140 )
              goto LABEL_173;
            if ( (char *)v140 + v135 + 4 <= &v116[v134] )
            {
              *v140 = v135;
              v138 = 0;
              v1330 = 0;
              memcpy_0(v140 + 1, v133, (unsigned int)v135);
              v137 = Size;
              v114 = 5;
              goto LABEL_185;
            }
            v138 = -1073741789;
          }
          else
          {
            v136 = v135 + 4;
            if ( v136 >= 4 )
            {
              v137 = v134 + v136;
              if ( (unsigned int)v137 < v134 )
              {
                v137 = 0xFFFFFFFFLL;
                v138 = -1073741675;
                Size = 0xFFFFFFFFLL;
              }
              else
              {
                v114 = 5;
                Size = v134 + v136;
                v138 = 0;
              }
LABEL_184:
              v1330 = v138;
LABEL_185:
              if ( v138 < 0 )
                goto LABEL_505;
              v142 = v1409;
              if ( !v1409 )
              {
                v143 = v137 + 8;
                if ( (int)v137 + 8 < (unsigned int)v137 )
                  goto LABEL_146;
                v137 = (unsigned int)(v137 + 16);
                Size = v137;
                if ( (unsigned int)v137 < v143 )
                  goto LABEL_146;
                v144 = v114 + 2;
LABEL_207:
                v1334 = v144;
                v1410 = __rdtsc();
                if ( (unsigned int)v137 >= 0xFFFFFFF8
                  || (v153 = ((_DWORD)v137 + 15) & 0xFFFFFFF8, v1402 = v153, (unsigned int)v153 < (int)v137 + 8) )
                {
                  v1330 = -805306219;
                  goto LABEL_511;
                }
                v154 = 0;
                v1419 = 0;
                v1412 = (void *)(unsigned int)v153;
                v155 = GetProcessHeap();
                v156 = (char *)HeapAlloc(v155, 8u, ((_DWORD)v137 + 15) & 0xFFFFFFF8);
                v157 = v156;
                if ( v156 )
                {
                  *(_DWORD *)v156 = v144;
                  v158 = v156 + 4;
                  if ( v158 < v157 || (*(_DWORD *)v158 = v137, v158 + 4 < v158) )
                  {
                    v386 = GetProcessHeap();
                    HeapFree(v386, 0, v157);
                    v385 = -805306219;
                    v1330 = -805306219;
                  }
                  else
                  {
                    v159 = (unsigned int)Size;
                    v160 = 0;
                    v1427 = 0;
                    v1414 = 0;
                    psz = 0;
                    *(_QWORD *)((char *)v1412 + (_QWORD)v157 - 8) = v1410;
                    memcpy_0(v158 + 4, v1409, v159);
                    v161 = (unsigned int)v1402;
                    if ( !(_DWORD)v1402 )
                      goto LABEL_416;
                    v1331 = v1402 + 8;
                    v1417 = MemoryAllocT<unsigned long>((unsigned int)v1402 + 8LL);
                    v163 = v1417;
                    if ( !v1417 )
                      goto LABEL_416;
                    LOBYTE(v162) = 0;
                    v1398 = v162;
                    lpMem = v157;
                    v164 = 0;
                    if ( (unsigned int)v1402 < 0x20uLL )
                      goto LABEL_1772;
                    lpMem = v157;
                    v165 = 0;
                    v166 = 0;
                    do
                    {
                      v165 = _mm_xor_ps(v165, (__m128)_mm_loadu_si128((const __m128i *)&v157[v164]));
                      v167 = (__m128)_mm_loadu_si128((const __m128i *)&v157[v164 + 16]);
                      v164 += 32LL;
                      v166 = _mm_xor_ps(v166, v167);
                    }
                    while ( v164 < (v1402 & 0xFFFFFFE0) );
                    v168 = _mm_xor_ps(v166, v165);
                    v169 = _mm_xor_ps(v168, (__m128)_mm_srli_si128((__m128i)v168, 8));
                    v170 = _mm_xor_ps(v169, (__m128)_mm_srli_si128((__m128i)v169, 4));
                    v171 = _mm_xor_ps(v170, (__m128)_mm_srli_si128((__m128i)v170, 2));
                    v162 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v171, (__m128)_mm_srli_si128((__m128i)v171, 1)));
                    v1398 = v162;
                    if ( v164 < (unsigned int)v1402 )
                    {
LABEL_1772:
                      do
                        LOBYTE(v162) = v157[v164++] ^ v162;
                      while ( v164 < (unsigned int)v1402 );
                      v1398 = v162;
                    }
                    Size = 0xC81ECB17B1B54A58uLL;
                    v1344 = (unsigned __int16 *)((unsigned __int64)(unsigned int)v1402 >> 3);
                    if ( v1344 )
                    {
                      v172 = HIDWORD(Size);
                      v173 = (unsigned __int8 *)lpMem;
                      v1407 = WORD2(Size);
                      v174 = WORD2(Size);
                      v1400 = 19032;
                      v175 = HIWORD(HIDWORD(Size));
                      v176 = HIWORD(HIDWORD(Size));
                      v1412 = (void *)v1417;
                      v177 = HIDWORD(Size) ^ 0xB1B54A58;
                      v1410 = 0;
                      LODWORD(v1422) = 0;
                      v178 = -1;
                      LODWORD(v1413) = 0;
                      v1385 = 0;
                      v1418 = lpMem;
                      do
                      {
                        v179 = *v173;
                        v180 = v173[1];
                        v181 = v173[4];
                        v173 += 8;
                        v182 = *(v173 - 5) | ((*(v173 - 6) | (((v179 << 8) | v180) << 8)) << 8);
                        v183 = *(v173 - 1) | ((*(v173 - 2) | ((*(v173 - 3) | (v181 << 8)) << 8)) << 8);
                        v184 = v1385 ^ v182 ^ ((v178 ^ v183) - v1400);
                        v185 = v184 ^ v172;
                        v186 = v178 ^ v183 ^ (__ROR4__(v185, 7) + WORD1(Size) * __ROR4__(v184, 15));
                        v187 = v185 ^ (v174 * __ROR4__(v186 - 1313519016, 9) - __ROR4__(v186, 10));
                        v188 = v186 ^ (__ROR4__(v187, 27) + v176 * __ROR4__(v187 ^ v174, 28));
                        v189 = v187 ^ (HIDWORD(Size) - (v188 ^ 0xB1B54A58));
                        v190 = v188 ^ (WORD1(Size) * (v189 - v1400) - (v189 >> 6));
                        v191 = v189 ^ (v1400 * (v174 ^ __ROR4__(v190, 15)));
                        v192 = v190 ^ (v174 * (v176 + __ROR4__(~v191, 3)));
                        v193 = v191 ^ (v192 - v1400 - HIDWORD(Size));
                        v194 = v192 ^ (WORD1(Size) * (v193 ^ v175)) ^ __ROR4__(v193, 10);
                        v195 = v193 ^ __ROR4__(v194, 3) ^ (v174 * __ROR4__(v194 ^ v1400, 26));
                        v196 = v194 ^ (v1400 * (__ROR4__(v195, 15) - v176));
                        v197 = v195
                             ^ (v1400 * (v196 ^ v175))
                             ^ ((v196 ^ (v196 >> 14)) >> 1)
                             ^ (v1400 * (((v196 - v174) >> 29) | (8 * (v196 - v174))));
                        v198 = v196 ^ (WORD1(Size) * (v197 - v174) - (v197 >> 13));
                        v199 = v197 ^ __ROR4__(v198, 11) ^ (v174 * __ROR4__(-1313519016 - v198, 9));
                        v200 = v198 ^ (v199 - v176 + 1313519016);
                        v201 = v199 ^ (v1400 * (v200 ^ WORD1(Size)) - __ROR4__(v200, 7));
                        v202 = v200 ^ (WORD1(Size) * __ROR4__(v201 ^ v175, 28) - __ROR4__(v201, 16));
                        v203 = v201 ^ (__ROR4__(v202, 4) + v174 * __ROR4__(-1313519016 - v202, 10));
                        v204 = v202 ^ __ROR4__(v203, 9) ^ (v176 * __ROR4__(v203 + 1313519016, 4));
                        v205 = v203 ^ (v1400 * __ROR4__(v204 ^ HIDWORD(Size), 24) - __ROR4__(v204, 30));
                        v206 = v204 ^ (WORD1(Size) * __ROR4__(HIDWORD(Size) - v205, 11) - __ROR4__(v205, 12));
                        v207 = (int)v1422;
                        LODWORD(v1422) = v182;
                        v208 = v205 ^ (v206 >> 8) ^ (v174 * (v206 ^ WORD1(Size)));
                        v209 = (int)v1413;
                        LODWORD(v1413) = v183;
                        v210 = v208 ^ v209;
                        v1385 = v208 ^ v207;
                        v211 = v1412;
                        v178 = v206 ^ v177 ^ v210;
                        v172 = HIDWORD(Size);
                        *((_BYTE *)v1412 + 3) = v1385;
                        v211[7] = v178;
                        v211[2] = __ROR4__(v1385, 8);
                        v211[6] = __ROR4__(v178, 8);
                        v211[1] = __ROR4__(v1385, 16);
                        v211[5] = __ROR4__(v178, 16);
                        *v211 = __ROR4__(v1385, 24);
                        v211[4] = __ROR4__(v178, 24);
                        v1412 = v211 + 8;
                        ++v1410;
                      }
                      while ( v1410 < (unsigned __int64)v1344 );
                      v160 = v1427;
                      v157 = (char *)v1418;
                      v103 = (unsigned int *)v1427;
                      v161 = (unsigned int)v1402;
                      v154 = v1427;
                      v163 = v1417;
                    }
                    *(_QWORD *)(v163 + v161) = (unsigned __int8)v1398;
                    v212 = GetProcessHeap();
                    v213 = HeapAlloc(v212, 8u, 0x30u);
                    if ( v213 )
                    {
                      *(_DWORD *)v213 = v1331;
                      v214 = GetProcessHeap();
                      v215 = HeapAlloc(v214, 8u, v1331);
                      if ( !v215 )
                        goto LABEL_229;
                      v216 = (const void *)v1417;
                      *((_QWORD *)v213 + 1) = v215;
                      memcpy_0(v215, v216, v1331);
                      *((_DWORD *)v213 + 4) = 160;
                      v217 = GetProcessHeap();
                      v218 = HeapAlloc(v217, 8u, 0xA0u);
                      if ( !v218 )
                        goto LABEL_229;
                      *((_QWORD *)v213 + 3) = v218;
                      *v218 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                      v218[1] = xmmword_1800AD3C0;
                      v218[2] = xmmword_1800AD3D0;
                      v218[3] = xmmword_1800AD3E0;
                      v218[4] = xmmword_1800AD3F0;
                      v218[5] = xmmword_1800AD400;
                      v218[6] = xmmword_1800AD410;
                      v218[7] = xmmword_1800AD420;
                      v218[8] = xmmword_1800AD430;
                      v218[9] = xmmword_1800AD440;
                      *((_DWORD *)v213 + 8) = 8;
                      v219 = GetProcessHeap();
                      v220 = HeapAlloc(v219, 8u, 8u);
                      if ( v220 )
                      {
                        *((_QWORD *)v213 + 5) = v220;
                        *v220 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                        v1332 = 0;
                        v160 = v213;
                      }
                      else
                      {
LABEL_229:
                        v1332 = -1073741801;
                        v1345 = (unsigned __int16 *)*((_QWORD *)v213 + 1);
                        if ( v1345 )
                        {
                          v221 = GetProcessHeap();
                          HeapFree(v221, 0, v1345);
                          *((_QWORD *)v213 + 1) = 0;
                        }
                        v1346 = (unsigned __int16 *)*((_QWORD *)v213 + 3);
                        if ( v1346 )
                        {
                          v222 = GetProcessHeap();
                          HeapFree(v222, 0, v1346);
                          *((_QWORD *)v213 + 3) = 0;
                        }
                        v1347 = (unsigned __int16 *)*((_QWORD *)v213 + 5);
                        if ( v1347 )
                        {
                          v223 = GetProcessHeap();
                          HeapFree(v223, 0, v1347);
                          *((_QWORD *)v213 + 5) = 0;
                        }
                        v224 = GetProcessHeap();
                        HeapFree(v224, 0, v213);
                      }
                    }
                    else
                    {
                      v1332 = -1073741801;
                    }
                    v225 = GetProcessHeap();
                    HeapFree(v225, 0, (LPVOID)v1417);
                    v1181 = v1332 < 0;
                    v1330 = v1332 | 0x10000000;
                    if ( v1181 )
                      goto LABEL_417;
                    if ( *(_DWORD *)v160 >= 0xFFFFFFFC )
                      goto LABEL_422;
                    v226 = *(_DWORD *)v160 + 8;
                    if ( v226 < *(_DWORD *)v160 + 4 )
                      goto LABEL_422;
                    v227 = v226 + *((_DWORD *)v160 + 4);
                    if ( v227 < v226 )
                      goto LABEL_422;
                    v228 = v227 + 4;
                    if ( v227 + 4 < v227 )
                      goto LABEL_422;
                    v229 = v228 + *((_DWORD *)v160 + 8);
                    LODWORD(v1416) = v229;
                    if ( v229 < v228 )
                      goto LABEL_422;
                    v230 = v229;
                    v231 = GetProcessHeap();
                    v232 = (char *)HeapAlloc(v231, 8u, v230);
                    v233 = v232;
                    if ( !v232 )
                    {
                      v1330 = -805306345;
                      goto LABEL_417;
                    }
                    *(_DWORD *)v232 = *(_DWORD *)v160;
                    if ( v232 + 4 < v232 )
                      goto LABEL_425;
                    memcpy_0(v232 + 4, (const void *)v160[1], *(unsigned int *)v160);
                    v234 = &v233[*(unsigned int *)v160 + 4];
                    if ( v234 < v233 + 4 )
                      goto LABEL_425;
                    *(_DWORD *)v234 = *((_DWORD *)v160 + 4);
                    v1348 = (unsigned __int16 *)(v234 + 4);
                    if ( v234 + 4 < v234
                      || (memcpy_0(v234 + 4, (const void *)v160[3], *((unsigned int *)v160 + 4)),
                          v235 = v1348,
                          v236 = (unsigned __int16 *)((char *)v1348 + *((unsigned int *)v160 + 4)),
                          v1349 = v236,
                          v236 < v235)
                      || (*(_DWORD *)v236 = *((_DWORD *)v160 + 8), v236 + 2 < v236)
                      || (memcpy_0(v236 + 2, (const void *)v160[5], *((unsigned int *)v160 + 8)),
                          (unsigned __int16 *)((char *)v1349 + *((unsigned int *)v160 + 8) + 4) < v1349 + 2) )
                    {
LABEL_425:
                      v367 = GetProcessHeap();
                      HeapFree(v367, 0, v233);
                      v1330 = -805306219;
                      goto LABEL_417;
                    }
                    if ( !v1409 )
                    {
                      v1330 = -1073741811;
                      v154 = v233;
                      goto LABEL_417;
                    }
                    if ( v1334 <= 1 )
                    {
                      v1330 = -1073741811;
                      v154 = v233;
                      goto LABEL_417;
                    }
                    v237 = (unsigned int *)((char *)v1409 + 4);
                    if ( (char *)v1409 + 4 < v1409
                      || (v238 = (unsigned int *)((char *)v237 + *(unsigned int *)v1409), v238 < v237)
                      || (v239 = v238 + 1, v238 + 1 < v238) )
                    {
                      v1330 = -1073741675;
                      v154 = v233;
                      goto LABEL_417;
                    }
                    v154 = v233;
                    if ( v1334 <= 2 )
                    {
                      v1330 = -1073741811;
                      goto LABEL_417;
                    }
                    v240 = *v238;
                    v241 = (unsigned int *)((char *)v239 + v240);
                    if ( (unsigned int *)((char *)v239 + v240) < v239
                      || v241 + 1 < v241
                      || (unsigned int)v240 >= 0xFFFFFFB0
                      || (v242 = v240 + 84, (int)v240 + 84 < (unsigned int)(v240 + 80))
                      || (v243 = v242 + *v241, LODWORD(v1413) = v243, v243 < v242) )
                    {
                      v1330 = -1073741675;
                      goto LABEL_417;
                    }
                    if ( v243 > 0x400000 )
                    {
                      v1330 = -2147418113;
                      goto LABEL_417;
                    }
                    v244 = v243;
                    v245 = GetProcessHeap();
                    v103 = (unsigned int *)HeapAlloc(v245, 8u, v244);
                    if ( !v103 )
                    {
                      v103 = 0;
                      v1330 = -805306345;
                      goto LABEL_417;
                    }
                    phModule = 0;
                    v1440 = v1416;
                    v246 = v154;
                    v1442 = 0;
                    v1441 = (unsigned int)v1413;
                    v1439[0] = v154;
                    v1439[1] = v103;
                    if ( !GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                      || (v249 = GetProcAddress(phModule, "NtQuerySystemInformation")) == 0 )
                    {
                      v247 = GetLastError();
                      v1330 = v247;
                      v248 = v247;
                      if ( v247 > 0 )
                      {
                        v248 = (unsigned __int16)v247 | 0x80070000;
                        v1330 = v248;
                      }
                      if ( v248 < 0 )
                        goto LABEL_276;
                      v1330 = -2147467259;
                      goto LABEL_417;
                    }
                    v250 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, _QWORD))v249)(134, v1439, 32, 0);
                    v248 = v250 | 0x10000000;
                    v1330 = v250 | 0x10000000;
                    if ( v250 >= 0 )
                    {
                      v251 = v1441;
                      goto LABEL_279;
                    }
LABEL_276:
                    v251 = (unsigned int)v1413;
                    if ( v248 == -805306333 )
                    {
                      v1330 = -2147024774;
                      goto LABEL_417;
                    }
                    if ( v248 >= 0 )
                    {
LABEL_279:
                      if ( v251 < 4 )
                      {
                        v1330 = -805306306;
                        goto LABEL_417;
                      }
                      v252 = *v103;
                      v253 = v103 + 1;
                      LODWORD(v1416) = *v103;
                      if ( v103 + 1 >= v103 )
                      {
                        if ( v251 - 4 < (unsigned int)v252 )
                        {
                          v1330 = -805306306;
                          goto LABEL_417;
                        }
                        v254 = (int *)((char *)v253 + v252);
                        v1402 = v252;
                        if ( (unsigned int *)((char *)v253 + v252) >= v253 && (unsigned int)v252 < 0xFFFFFFFC )
                        {
                          if ( v251 - ((_DWORD)v252 + 4) < 4 )
                          {
                            v1330 = -805306306;
                            goto LABEL_417;
                          }
                          v255 = (unsigned int)*v254;
                          v256 = (unsigned int *)(v254 + 1);
                          v1407 = *v254;
                          v1417 = (size_t)(v254 + 1);
                          if ( v254 + 1 >= v254 )
                          {
                            v257 = v252 + 8;
                            if ( (int)v252 + 8 >= (unsigned int)(v252 + 4) )
                            {
                              if ( v251 - v257 < (unsigned int)v255 )
                              {
                                v1330 = -805306306;
                                goto LABEL_417;
                              }
                              v258 = (unsigned int *)((char *)v256 + v255);
                              v1410 = v255;
                              if ( (unsigned __int64)v258 >= v1417 )
                              {
                                v259 = v257 + v255;
                                if ( v257 + (unsigned int)v255 >= v257 )
                                {
                                  if ( v251 - v259 < 4 )
                                  {
                                    v1330 = -805306306;
                                    goto LABEL_417;
                                  }
                                  v1412 = v258 + 1;
                                  if ( v258 + 1 >= v258 )
                                  {
                                    v260 = v259 + 4;
                                    if ( v259 + 4 >= v259 )
                                    {
                                      v261 = *v258;
                                      LODWORD(v1415) = v261;
                                      if ( v251 - v260 < v261 )
                                      {
                                        v1330 = -805306306;
                                        goto LABEL_417;
                                      }
                                      if ( v260 + v261 >= v260 )
                                      {
                                        if ( v251 != v260 + v261 )
                                        {
                                          v1330 = -805306306;
                                          goto LABEL_417;
                                        }
                                        if ( (unsigned int)v252 + (_DWORD)v255 + v261 + 12LL != v251 )
                                        {
                                          v1330 = -805306306;
                                          goto LABEL_417;
                                        }
                                        v262 = GetProcessHeap();
                                        lpMem = HeapAlloc(v262, 8u, 0x30u);
                                        v263 = lpMem;
                                        if ( !lpMem )
                                        {
                                          v154 = v246;
                                          v1330 = -805306345;
                                          goto LABEL_417;
                                        }
                                        v264 = v103 + 1;
                                        if ( v103 != (unsigned int *)-4LL )
                                        {
                                          *(_DWORD *)lpMem = v1416;
                                          v265 = GetProcessHeap();
                                          v266 = HeapAlloc(v265, 8u, v1402);
                                          if ( v266 )
                                          {
                                            v267 = v1402;
                                            v263[1] = v266;
                                            v1333 = 0;
                                            memcpy_0(v266, v103 + 1, v267);
                                            v264 = 0;
                                            goto LABEL_311;
                                          }
LABEL_318:
                                          v154 = v246;
                                          v1415 = v246;
                                          v275 = lpMem;
                                          v1333 = -1073741801;
                                          v1411 = v103;
                                          v1427 = v160;
                                          v276 = (unsigned __int16 *)*((_QWORD *)lpMem + 1);
                                          v1418 = v157;
                                          v1417 = 0;
                                          v1350 = v276;
                                          if ( v276 )
                                          {
                                            v277 = GetProcessHeap();
                                            HeapFree(v277, 0, v1350);
                                            *((_QWORD *)lpMem + 1) = 0;
                                          }
                                          v1351 = (unsigned __int16 *)v275[3];
                                          if ( v1351 )
                                          {
                                            v278 = GetProcessHeap();
                                            HeapFree(v278, 0, v1351);
                                            v275[3] = 0;
                                          }
                                          v1352 = (unsigned __int16 *)v275[5];
                                          if ( v1352 )
                                          {
                                            v279 = GetProcessHeap();
                                            HeapFree(v279, 0, v1352);
                                            v275[5] = 0;
                                          }
                                          v280 = GetProcessHeap();
                                          HeapFree(v280, 0, v275);
                                          v281 = (unsigned int *)v1417;
LABEL_328:
                                          v284 = v1333;
                                          if ( v1333 < 0 )
                                          {
                                            v286 = (_QWORD *)v1417;
                                            if ( v1417 )
                                            {
                                              v1353 = *(unsigned __int16 **)(v1417 + 8);
                                              if ( v1353 )
                                              {
                                                v287 = GetProcessHeap();
                                                HeapFree(v287, 0, v1353);
                                                v286[1] = 0;
                                              }
                                              v1354 = (unsigned __int16 *)v286[3];
                                              if ( v1354 )
                                              {
                                                v288 = GetProcessHeap();
                                                HeapFree(v288, 0, v1354);
                                                v286[3] = 0;
                                              }
                                              v1355 = (unsigned __int16 *)v286[5];
                                              if ( v1355 )
                                              {
                                                v289 = GetProcessHeap();
                                                HeapFree(v289, 0, v1355);
                                                v286[5] = 0;
                                              }
                                              v290 = GetProcessHeap();
                                              HeapFree(v290, 0, v286);
                                              v284 = v1333;
                                            }
                                            v285 = (unsigned int *)v1414;
                                          }
                                          else
                                          {
                                            v285 = v281;
                                            v1414 = v281;
                                          }
                                          v1330 = v284 | 0x10000000;
                                          if ( v284 < 0 )
                                            goto LABEL_417;
                                          if ( !v285 )
                                          {
                                            v1330 = -805306355;
                                            goto LABEL_417;
                                          }
                                          v1412 = (void *)*((_QWORD *)v285 + 1);
                                          if ( !v1412 )
                                          {
                                            v1330 = -805306355;
                                            goto LABEL_417;
                                          }
                                          v291 = *v285;
                                          if ( !(_DWORD)v291 )
                                          {
                                            v1330 = -805306355;
                                            goto LABEL_417;
                                          }
                                          v292 = v291 - 8;
                                          v1416 = v291 - 8;
                                          v293 = (void *)MemoryAllocT<unsigned long>(v291 - 8);
                                          lpMem = v293;
                                          if ( v293 )
                                          {
                                            v294 = (unsigned __int8 *)v1412;
                                            LOBYTE(v1422) = 0;
                                            v295 = v293;
                                            v1417 = 0x7F1137FAB69605ELL;
                                            v1402 = (SIZE_T)v293;
                                            v296 = v292 & 7;
                                            if ( (v292 & 7) != 0 )
                                            {
                                              v297 = 0;
                                              v1400 = 0;
                                              v298 = 0;
                                              do
                                              {
                                                v299 = *v294;
                                                v300 = 8 * v297;
                                                ++v294;
                                                if ( v297 >= 4 )
                                                {
                                                  v301 = v1400;
                                                  v298 |= v299 << (56 - v300);
                                                }
                                                else
                                                {
                                                  v301 = (v299 << (24 - v300)) | v1400;
                                                  v1400 = v301;
                                                }
                                                ++v297;
                                              }
                                              while ( (int)v297 < (int)v296 );
                                              v302 = v301;
                                              LODWORD(v1413) = v298;
                                              v303 = v298 ^ 0x699A899C;
                                              v1411 = v103;
                                              v304 = v302 ^ 0x92F65A5;
                                              v305 = 0;
                                              v1398 = v304;
                                              v1415 = v154;
                                              v1427 = v160;
                                              v1418 = v157;
                                              do
                                              {
                                                v1356 = (unsigned __int16 *)(v295 + 1);
                                                if ( v305 >= 4 )
                                                {
                                                  v303 = __ROR4__(v303, 24);
                                                  v306 = v303;
                                                }
                                                else
                                                {
                                                  v304 = __ROR4__(v304, 24);
                                                  v306 = v304;
                                                }
                                                *v295 = v306;
                                                ++v305;
                                                ++v295;
                                              }
                                              while ( v305 < (int)v296 );
                                              v1402 = (SIZE_T)v1356;
                                              if ( v296 > 4 )
                                              {
                                                v307 = (v298 ^ 0x699A899Cu) >> (8 * (8 - v296)) << (8 * (8 - v296));
                                                goto LABEL_364;
                                              }
                                              if ( v296 >= 4 )
                                              {
                                                v307 = 0;
LABEL_364:
                                                v309 = v1398;
                                              }
                                              else
                                              {
                                                v308 = 4 - v296;
                                                v307 = 0;
                                                v309 = v1398 >> (8 * v308) << (8 * v308);
                                              }
                                            }
                                            else
                                            {
                                              v307 = 0;
                                              v1400 = 0;
                                              v309 = 0;
                                              LODWORD(v1413) = -1;
                                            }
                                            if ( v292 >> 3 )
                                            {
                                              v310 = v1402;
                                              v311 = v1400;
                                              v312 = (int)v1413;
                                              v313 = v292 >> 3;
                                              v1335 = WORD2(v1417);
                                              v314 = HIWORD(HIDWORD(v1417));
                                              v1410 = 0;
                                              v1398 = 43881;
                                              do
                                              {
                                                v315 = v294[3] | ((v294[2] | ((v294[1] | (*v294 << 8)) << 8)) << 8);
                                                v316 = v294[7] | ((v294[6] | ((v294[5] | (v294[4] << 8)) << 8)) << 8);
                                                v1357 = (unsigned __int16 *)(v294 + 8);
                                                v317 = v309 ^ v315 ^ v307 ^ v316 ^ HIDWORD(v1417) ^ 0xAB69605E;
                                                v318 = v309
                                                     ^ v315
                                                     ^ (__ROR4__(v317, 22) + v1335 * __ROR4__(v317 + 1419157410, 27));
                                                v319 = v317
                                                     ^ (v1398 * __ROR4__(v318 + HIDWORD(v1417), 9) - __ROR4__(v318, 30));
                                                v320 = v318 ^ (24670 * (v319 - v1335) - (v319 >> 13));
                                                v321 = v319 ^ (v314 * __ROR4__(v320 ^ 0xAB69, 26) - __ROR4__(v320, 30));
                                                v322 = v320 ^ (HIDWORD(v1417) - (v321 ^ 0xAB69605E));
                                                v323 = v321 ^ (v1398 * (v322 ^ v1335)) ^ __ROR4__(v322, 6);
                                                v324 = v322
                                                     ^ (__ROR4__(v323, 30) + 24670 * __ROR4__(v323 + HIDWORD(v1417), 15));
                                                v325 = v323
                                                     ^ (v314 * __ROR4__(v324 + 1419157410, 14) - __ROR4__(v324, 24));
                                                v326 = v324
                                                     ^ __ROR4__(v325, 10)
                                                     ^ (v1335 * __ROR4__(v325 ^ 0xAB69605E, 12));
                                                v327 = v325 ^ (v326 >> 10) ^ (v1398 * (v326 ^ v314));
                                                v328 = v326 ^ (v314 * (__ROR4__(~v327, 5) + 24670));
                                                v329 = v327 ^ (v328 - v314) ^ 0xAB69605E;
                                                v330 = v328 ^ ((v329 >> 2) + v1335 * __ROR4__(v329 ^ v314, 30));
                                                v331 = v329
                                                     ^ (__ROR4__(v330, 25) + v1398 * __ROR4__(v330 - HIDWORD(v1417), 6));
                                                v332 = v330 ^ (24670 * (v1335 ^ v331) + __ROR4__(v331, 9));
                                                v333 = v331 ^ (__ROR4__(v332, 25) + v314 * __ROR4__(v332 ^ 0xAB69, 27));
                                                v334 = v333 ^ HIDWORD(v1417) ^ v332 ^ 0xAB69605E;
                                                v335 = v333 ^ (v1335 * (__ROR4__(v334, 3) - v1398));
                                                v336 = v334
                                                     ^ (24670 * __ROR4__(v335 - HIDWORD(v1417), 1) - __ROR4__(v335, 6));
                                                v310 += 8LL;
                                                v337 = v335
                                                     ^ (__ROR4__(v336, 18) + v314 * __ROR4__(v336 - 1419157410, 29));
                                                v338 = v336
                                                     ^ (v1335 * __ROR4__(v337 - 1419157410, 17) - __ROR4__(v337, 14));
                                                v294 = (unsigned __int8 *)v1357;
                                                v339 = v337 ^ (v338 >> 3) ^ (v1398 * (v338 ^ 0x605E));
                                                v307 = v339 ^ v312;
                                                v312 = v316;
                                                v340 = v311
                                                     ^ __ROR4__(v339, 30)
                                                     ^ (24670 * __ROR4__(v339 ^ HIDWORD(v1417), 28));
                                                v311 = v315;
                                                v309 = v338 ^ v340;
                                                *(_BYTE *)(v310 - 5) = v309;
                                                *(_BYTE *)(v310 - 1) = v307;
                                                *(_BYTE *)(v310 - 6) = __ROR4__(v309, 8);
                                                *(_BYTE *)(v310 - 2) = __ROR4__(v307, 8);
                                                *(_BYTE *)(v310 - 7) = __ROR4__(v309, 16);
                                                *(_BYTE *)(v310 - 3) = __ROR4__(v307, 16);
                                                *(_BYTE *)(v310 - 8) = __ROR4__(v309, 24);
                                                *(_BYTE *)(v310 - 4) = __ROR4__(v307, 24);
                                                ++v1410;
                                              }
                                              while ( v1410 < v313 );
                                              v157 = (char *)v1418;
                                              v160 = v1427;
                                              v103 = v1411;
                                              v154 = v1415;
                                              v292 = v1416;
                                            }
                                            if ( v292 )
                                            {
                                              v341 = 0;
                                              if ( v292 < 0x20 )
                                              {
                                                m = (unsigned __int8)v1422;
                                                goto LABEL_376;
                                              }
                                              v342 = 0;
                                              v343 = 0;
                                              do
                                              {
                                                v342 = _mm_xor_ps(
                                                         v342,
                                                         (__m128)_mm_loadu_si128((const __m128i *)((char *)lpMem + v341)));
                                                v344 = (__m128)_mm_loadu_si128((const __m128i *)((char *)lpMem
                                                                                               + v341
                                                                                               + 16));
                                                v341 += 32LL;
                                                v343 = _mm_xor_ps(v343, v344);
                                              }
                                              while ( v341 < (v292 & 0xFFFFFFFFFFFFFFE0uLL) );
                                              v345 = _mm_xor_ps(v343, v342);
                                              v346 = _mm_xor_ps(v345, (__m128)_mm_srli_si128((__m128i)v345, 8));
                                              v347 = _mm_xor_ps(v346, (__m128)_mm_srli_si128((__m128i)v346, 4));
                                              v348 = _mm_xor_ps(v347, (__m128)_mm_srli_si128((__m128i)v347, 2));
                                              for ( m = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                     v348,
                                                                                     (__m128)_mm_srli_si128(
                                                                                               (__m128i)v348,
                                                                                               1))); v341 < v292; ++v341 )
LABEL_376:
                                                m ^= *((_BYTE *)lpMem + v341);
                                            }
                                            else
                                            {
                                              m = (unsigned __int8)v1422;
                                            }
                                            if ( m == *(_QWORD *)((char *)v1412 + v292) )
                                            {
                                              psz = (STRSAFE_PCNZWCH)lpMem;
                                              v350 = lpMem;
                                              if ( (unsigned int)v292 < 4 )
                                                goto LABEL_381;
                                              v351 = (unsigned int *)((char *)lpMem + 4);
                                              if ( (char *)lpMem + 4 < lpMem )
                                                goto LABEL_413;
                                              if ( (unsigned int)(v292 - 4) < 4 )
                                              {
                                                v1330 = -805306306;
                                                goto LABEL_417;
                                              }
                                              v352 = (char *)lpMem + 8;
                                              if ( (char *)lpMem + 8 < (char *)lpMem + 4 )
                                                goto LABEL_413;
                                              v353 = *v351;
                                              if ( (int)v292 - 8 < (unsigned int)v353 )
                                              {
                                                v1330 = -805306306;
                                                goto LABEL_417;
                                              }
                                              if ( (unsigned int)v353 >= 0xFFFFFFF8 )
                                                goto LABEL_413;
                                              v354 = (unsigned __int64)&v352[v353];
                                              v355 = *v351;
                                              v1402 = v355;
                                              if ( (char *)lpMem + (unsigned int)v292 < &v352[v353]
                                                || (unsigned __int64)(unsigned int)v292 + -v353 - 8 >= 8 )
                                              {
LABEL_381:
                                                v1330 = -805306306;
                                                goto LABEL_417;
                                              }
                                              v356 = 0;
                                              if ( lpMem == (LPVOID)-8LL )
                                              {
                                                v360 = 0;
                                                goto LABEL_405;
                                              }
                                              if ( v354 < (unsigned __int64)v352 )
                                              {
LABEL_413:
                                                v360 = -1073741675;
                                              }
                                              else
                                              {
                                                v357 = (char *)lpMem + 8;
                                                if ( v354 > (unsigned __int64)v352 )
                                                {
                                                  do
                                                  {
                                                    if ( v357 + 4 < v357 )
                                                      goto LABEL_413;
                                                    if ( (unsigned __int64)(v357 + 4) > v354 )
                                                      goto LABEL_402;
                                                    v358 = *(_DWORD *)v357 + 4;
                                                    if ( *(_DWORD *)v357 >= 0xFFFFFFFC )
                                                      goto LABEL_413;
                                                    v359 = &v357[v358];
                                                    if ( v359 < v357 )
                                                      goto LABEL_413;
                                                    if ( (unsigned __int64)v359 > v354 )
                                                      goto LABEL_402;
                                                    ++v356;
                                                    v357 += v358;
                                                  }
                                                  while ( (unsigned __int64)v359 < v354 );
                                                  v350 = psz;
                                                }
                                                if ( v357 != (char *)v354 )
                                                {
LABEL_402:
                                                  v1330 = -805306355;
                                                  goto LABEL_417;
                                                }
                                                v360 = 0;
LABEL_405:
                                                LODWORD(v1416) = *v350;
                                                v361 = 0;
                                                v1410 = 0;
                                                if ( (_DWORD)v353 )
                                                {
                                                  v362 = GetProcessHeap();
                                                  v361 = HeapAlloc(v362, 8u, v1402);
                                                  v1410 = (SIZE_T)v361;
                                                  if ( v361 )
                                                  {
                                                    v352 = (char *)lpMem + 8;
                                                    v360 = 0;
                                                    v355 = v1402;
                                                    goto LABEL_408;
                                                  }
                                                  v1330 = -805306345;
                                                  goto LABEL_417;
                                                }
LABEL_408:
                                                if ( v352 )
                                                {
                                                  memcpy_0(v361, v352, v355);
                                                  v360 = 0;
                                                }
                                                pcchLength = v1410;
                                                v1419 = v356;
                                                if ( (_DWORD)v1416 != v356 )
                                                {
                                                  v1330 = -805306306;
                                                  goto LABEL_417;
                                                }
                                              }
                                              v1330 = v360 | 0x10000000;
                                              goto LABEL_417;
                                            }
                                            v363 = GetProcessHeap();
                                            HeapFree(v363, 0, lpMem);
                                          }
LABEL_416:
                                          v1330 = -805306367;
                                          goto LABEL_417;
                                        }
                                        *(_DWORD *)lpMem = (_DWORD)v264;
                                        v263[1] = v264;
                                        v1333 = 0;
LABEL_311:
                                        if ( v1417 )
                                        {
                                          *((_DWORD *)v263 + 4) = v1407;
                                          v268 = GetProcessHeap();
                                          v269 = HeapAlloc(v268, 8u, v1410);
                                          if ( v269 )
                                          {
                                            v270 = v1410;
                                            v271 = (const void *)v1417;
                                            v1333 = 0;
                                            v263[3] = v269;
                                            memcpy_0(v269, v271, v270);
                                            v264 = 0;
                                            goto LABEL_315;
                                          }
LABEL_317:
                                          lpMem = v263;
                                          goto LABEL_318;
                                        }
                                        *((_DWORD *)v263 + 4) = (_DWORD)v264;
                                        v263[3] = v264;
LABEL_315:
                                        if ( v1412 )
                                        {
                                          v272 = (unsigned int)v1415;
                                          *((_DWORD *)v263 + 8) = (_DWORD)v1415;
                                          v1402 = v272;
                                          v273 = GetProcessHeap();
                                          v274 = HeapAlloc(v273, 8u, v1402);
                                          if ( !v274 )
                                            goto LABEL_317;
                                          v282 = v1402;
                                          v283 = v1412;
                                          v1333 = 0;
                                          v263[5] = v274;
                                          memcpy_0(v274, v283, v282);
                                        }
                                        else
                                        {
                                          *((_DWORD *)v263 + 8) = (_DWORD)v264;
                                          v263[5] = v264;
                                        }
                                        v281 = (unsigned int *)v263;
                                        v1411 = v103;
                                        v1417 = (size_t)v263;
                                        v154 = v246;
                                        v1415 = v246;
                                        v1427 = v160;
                                        v1418 = v157;
                                        goto LABEL_328;
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
LABEL_422:
                      v1330 = -805306219;
                    }
LABEL_417:
                    if ( v157 )
                    {
                      v364 = GetProcessHeap();
                      HeapFree(v364, 0, v157);
                    }
                    if ( v160 )
                    {
                      v365 = (void *)v160[1];
                      if ( v365 )
                      {
                        v366 = GetProcessHeap();
                        HeapFree(v366, 0, v365);
                        v160[1] = 0;
                      }
                      v368 = (void *)v160[3];
                      if ( v368 )
                      {
                        v369 = GetProcessHeap();
                        HeapFree(v369, 0, v368);
                        v160[3] = 0;
                      }
                      v370 = (void *)v160[5];
                      if ( v370 )
                      {
                        v371 = GetProcessHeap();
                        HeapFree(v371, 0, v370);
                        v160[5] = 0;
                      }
                      v372 = GetProcessHeap();
                      HeapFree(v372, 0, v160);
                    }
                    if ( v154 )
                    {
                      v373 = GetProcessHeap();
                      HeapFree(v373, 0, v154);
                    }
                    if ( v103 )
                    {
                      v374 = GetProcessHeap();
                      HeapFree(v374, 0, v103);
                    }
                    v375 = v1414;
                    if ( v1414 )
                    {
                      v376 = (void *)*((_QWORD *)v1414 + 1);
                      if ( v376 )
                      {
                        v377 = GetProcessHeap();
                        HeapFree(v377, 0, v376);
                        v375[1] = 0;
                      }
                      v378 = (void *)v375[3];
                      if ( v378 )
                      {
                        v379 = GetProcessHeap();
                        HeapFree(v379, 0, v378);
                        v375[3] = 0;
                      }
                      v380 = (void *)v375[5];
                      if ( v380 )
                      {
                        v381 = GetProcessHeap();
                        HeapFree(v381, 0, v380);
                        v375[5] = 0;
                      }
                      v382 = GetProcessHeap();
                      HeapFree(v382, 0, v375);
                    }
                    v383 = (wchar_t *)psz;
                    if ( psz )
                    {
                      v384 = GetProcessHeap();
                      HeapFree(v384, 0, v383);
                    }
                    v385 = v1330;
                    LODWORD(v154) = v1419;
                    v103 = (unsigned int *)pcchLength;
                  }
                }
                else
                {
                  v385 = -805306345;
                  v1330 = -805306345;
                }
                if ( v385 < 0 )
                  goto LABEL_511;
                if ( !(_DWORD)v154 )
                  goto LABEL_510;
                if ( !v103 )
                {
                  v1330 = -1073741811;
                  goto LABEL_511;
                }
                if ( v103 + 1 < v103 )
                  goto LABEL_498;
                v387 = 0;
                if ( *v103 )
                  v387 = (int *)(v103 + 1);
                if ( *v103 != 4 )
                {
                  v1330 = -1073741789;
                  goto LABEL_511;
                }
                v388 = *v387;
                v1330 = v388;
                if ( v388 == -805306333 )
                {
                  v1420 = -2147024774;
                  v389 = -2147024774;
                  goto LABEL_463;
                }
                if ( v388 != -2147024774 && v388 < 0 )
                  goto LABEL_511;
                v389 = v388;
LABEL_463:
                if ( (_DWORD)v154 != 6 )
                  goto LABEL_510;
                v390 = v103 + 1;
                v391 = (unsigned int *)((char *)v103 + *v103 + 4);
                if ( v391 < v103 + 1 )
                  goto LABEL_498;
                v392 = v391 + 1;
                if ( v391 + 1 < v391 )
                  goto LABEL_498;
                v393 = *v391;
                v394 = 0;
                if ( v393 )
                  v394 = v392;
                if ( v393 != 8 )
                {
                  v1330 = -1073741789;
                  goto LABEL_511;
                }
                v395 = *v103;
                v396 = (unsigned __int64)v390 + v395 + 4;
                v397 = (int *)(v396 + *(unsigned int *)((char *)v390 + v395));
                if ( (unsigned __int64)v397 < v396 )
                  goto LABEL_498;
                v398 = (unsigned int *)(v397 + 1);
                if ( v397 + 1 < v397 )
                  goto LABEL_498;
                v399 = *v397;
                v400 = 0;
                if ( v399 )
                  v400 = v398;
                if ( v399 != 4 )
                {
                  v1330 = -1073741789;
                  goto LABEL_511;
                }
                v401 = (unsigned int *)((char *)v390 + *v103);
                v402 = *v401;
                v403 = (unsigned int *)((char *)v401 + v402 + 8);
                v404 = (unsigned int *)((char *)v403 + *(unsigned int *)((char *)v401 + v402 + 4));
                if ( v404 >= v403 )
                {
                  v405 = v404 + 1;
                  if ( v404 + 1 >= v404 )
                  {
                    v406 = *v404;
                    v407 = 0;
                    if ( (_DWORD)v406 )
                      v407 = v404 + 1;
                    v408 = (int *)((char *)v405 + v406);
                    if ( (unsigned int *)((char *)v405 + v406) >= v405 )
                    {
                      v409 = v408 + 1;
                      if ( v408 + 1 >= v408 )
                      {
                        v410 = *v408;
                        v411 = 0;
                        if ( v410 )
                          v411 = v409;
                        if ( v410 != 4 )
                        {
                          v1330 = -1073741789;
                          goto LABEL_511;
                        }
                        v412 = (unsigned __int64)v405 + v406 + 4;
                        v413 = (int *)(v412 + *(unsigned int *)((char *)v405 + v406));
                        if ( (unsigned __int64)v413 >= v412 )
                        {
                          v414 = v413 + 1;
                          if ( v413 + 1 >= v413 )
                          {
                            v415 = *v413;
                            v416 = 0;
                            if ( v415 )
                              v416 = v414;
                            if ( v415 != 4 )
                            {
                              v1330 = -1073741789;
                              goto LABEL_511;
                            }
                            if ( v1404 == *v394 )
                            {
                              v417 = *v411 <= 4u;
                              LODWORD(v1406) = *v416;
                              v1329 = *v400;
                              if ( !v417 )
                              {
                                v1330 = -2147024774;
                                goto LABEL_511;
                              }
                              if ( (unsigned int)v406 > 4 )
                              {
                                v1330 = -2147024774;
                                goto LABEL_511;
                              }
                              memcpy_0(v1438, v407, v406);
                              v1330 = 0;
LABEL_507:
                              v102 = Src;
                              if ( v389 )
                                v1330 = v389;
LABEL_512:
                              v418 = v1409;
                              if ( v1409 )
                              {
                                v419 = GetProcessHeap();
                                HeapFree(v419, 0, v418);
                              }
                              if ( v103 )
                              {
                                v420 = GetProcessHeap();
                                HeapFree(v420, 0, v103);
                              }
                              v99 = v1403;
LABEL_517:
                              if ( v102 )
                              {
LABEL_518:
                                v421 = GetProcessHeap();
                                HeapFree(v421, 0, v102);
                              }
                              if ( v99 )
                              {
                                v422 = GetProcessHeap();
                                HeapFree(v422, 0, v99);
                              }
                              v2 = v1330;
                              if ( v1330 >= 0 )
                              {
                                if ( !(_DWORD)v1406 )
                                  goto LABEL_1741;
                                *(_QWORD *)&v1431[1] = 0;
                                g_WarbirdNotificationInformation = v1406;
                                ModuleFileNameW = GetModuleFileNameW(&_ImageBase, &Filename, 0x104u);
                                if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
                                  goto LABEL_1447;
                                v1418 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC128[0])(
                                                  0,
                                                  0,
                                                  1027);
                                if ( !v1418 )
                                {
                                  GetLastError();
                                  goto LABEL_1447;
                                }
                                v424 = ((__int64 (*)(void))off_1800AC0C8[0])();
                                v425 = g_WarbirdNotificationInformation;
                                g_WarbirdPaintInitTime = v424;
                                memset(v1541, 0, 44);
                                *(_OWORD *)v1455 = 0;
                                *(_OWORD *)v1456 = 0;
                                v1457 = 0;
                                v1458 = 0;
                                v1459 = 0;
                                v1460 = 0;
                                v1461 = 0;
                                v1425 = 0;
                                while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                                  ;
                                if ( g_WarbirdSecureFunctionsRefCount )
                                {
LABEL_582:
                                  ++g_WarbirdSecureFunctionsRefCount;
                                }
                                else
                                {
                                  v426 = (char *)MemoryAllocT<unsigned long>(824);
                                  lpMem = v426;
                                  if ( v426 )
                                  {
                                    v427 = 0;
                                    v428 = qword_18009D240;
                                    v429 = 0;
                                    v430 = v426;
                                    v431 = 0;
                                    v432 = -1;
                                    v433 = 103;
                                    do
                                    {
                                      v434 = *((unsigned __int8 *)v428 + 1);
                                      v435 = *(unsigned __int8 *)v428;
                                      v436 = *((unsigned __int8 *)v428++ + 4);
                                      v437 = *((unsigned __int8 *)v428 - 5)
                                           | ((*((unsigned __int8 *)v428 - 6) | ((v434 | (v435 << 8)) << 8)) << 8);
                                      v438 = v431 ^ v437;
                                      v439 = *((unsigned __int8 *)v428 - 1)
                                           | ((*((unsigned __int8 *)v428 - 2)
                                             | ((*((unsigned __int8 *)v428 - 3) | (v436 << 8)) << 8)) << 8);
                                      v440 = v429 ^ v439 ^ v431 ^ v437 ^ 0xAC987321;
                                      v441 = v438 ^ (__ROR4__(v440, 22) + 4991 * __ROR4__(v440 + 1419157410, 27));
                                      v442 = v440 ^ (43881 * __ROR4__(v441 + 133239679, 9) - __ROR4__(v441, 30));
                                      v443 = v441 ^ (24670 * v442 - (v442 >> 13) - 123127970);
                                      v444 = v442 ^ (2033 * __ROR4__(v443 ^ 0xAB69, 26) - __ROR4__(v443, 30));
                                      v445 = v443 ^ (133239679 - (v444 ^ 0xAB69605E));
                                      v446 = v444 ^ (43881 * (v445 ^ 0x137F)) ^ __ROR4__(v445, 6);
                                      v447 = v445 ^ (__ROR4__(v446, 30) + 24670 * __ROR4__(v446 + 133239679, 15));
                                      v448 = v446 ^ (2033 * __ROR4__(v447 + 1419157410, 14) - __ROR4__(v447, 24));
                                      v449 = v447 ^ __ROR4__(v448, 10) ^ (4991 * __ROR4__(v448 ^ 0xAB69605E, 12));
                                      v450 = v448 ^ (v449 >> 10) ^ (43881 * (v449 ^ 0x7F1));
                                      v451 = v449 ^ (2033 * (__ROR4__(~v450, 5) + 24670));
                                      v452 = v451
                                           ^ (((v450 ^ (v451 - 2033) ^ 0xAB69605E) >> 2)
                                            + 4991 * __ROR4__(v450 ^ (v451 - 2033) ^ 0xAB6967AF, 30));
                                      v453 = v450
                                           ^ (v451 - 2033)
                                           ^ 0xAB69605E
                                           ^ (__ROR4__(v452, 25) + 43881 * __ROR4__(v452 - 133239679, 6));
                                      v454 = v452 ^ (24670 * (v453 ^ 0x137F) + __ROR4__(v453, 9));
                                      v455 = v453 ^ (__ROR4__(v454, 25) + 2033 * __ROR4__(v454 ^ 0xAB69, 27));
                                      v456 = v454 ^ v455 ^ 0xAC987321;
                                      v457 = v455 ^ (4991 * __ROR4__(v456, 3) - 219010071);
                                      v458 = v456 ^ (24670 * __ROR4__(v457 - 133239679, 1) - __ROR4__(v457, 6));
                                      v459 = v457 ^ (__ROR4__(v458, 18) + 2033 * __ROR4__(v458 - 1419157410, 29));
                                      v430 += 8;
                                      v460 = v458 ^ (4991 * __ROR4__(v459 - 1419157410, 17) - __ROR4__(v459, 14));
                                      v461 = v459 ^ (v460 >> 3) ^ (43881 * (v460 ^ 0x605E));
                                      v462 = v427 ^ __ROR4__(v461, 30) ^ (24670 * __ROR4__(v461 ^ 0x7F1137F, 28));
                                      v427 = v437;
                                      v431 = v460 ^ v462;
                                      *(v430 - 5) = v431;
                                      v429 = v461 ^ v432;
                                      *(v430 - 1) = v461 ^ v432;
                                      v432 = v439;
                                      *(v430 - 6) = __ROR4__(v431, 8);
                                      *(v430 - 2) = __ROR4__(v429, 8);
                                      *(v430 - 7) = __ROR4__(v431, 16);
                                      *(v430 - 3) = __ROR4__(v429, 16);
                                      *(v430 - 8) = __ROR4__(v431, 24);
                                      *(v430 - 4) = __ROR4__(v429, 24);
                                      --v433;
                                    }
                                    while ( v433 );
                                    v463 = (WCHAR *)lpMem;
                                    v464 = 0;
                                    v465 = 0;
                                    v466 = 0;
                                    do
                                    {
                                      v465 = _mm_xor_ps(
                                               v465,
                                               (__m128)_mm_loadu_si128((const __m128i *)((char *)lpMem + v464)));
                                      v467 = (__m128)_mm_loadu_si128((const __m128i *)((char *)lpMem + v464 + 16));
                                      v464 += 32LL;
                                      v466 = _mm_xor_ps(v466, v467);
                                    }
                                    while ( v464 < 0x320 );
                                    v468 = _mm_xor_ps(v466, v465);
                                    v469 = _mm_xor_ps(v468, (__m128)_mm_srli_si128((__m128i)v468, 8));
                                    v470 = _mm_xor_ps(v469, (__m128)_mm_srli_si128((__m128i)v469, 4));
                                    v471 = _mm_xor_ps(v470, (__m128)_mm_srli_si128((__m128i)v470, 2));
                                    for ( n = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                           v471,
                                                                           (__m128)_mm_srli_si128((__m128i)v471, 1)));
                                          v464 < 0x338;
                                          ++v464 )
                                    {
                                      n ^= *((_BYTE *)lpMem + v464);
                                    }
                                    if ( n == 64 )
                                    {
                                      v473 = 0;
                                      *((_BYTE *)lpMem + 823) = 0;
                                      v474 = 0;
                                      LODWORD(v1406) = 0;
                                      *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                      v1386 = 0;
                                      v475 = v463;
                                      xmmword_1800AD870 = 0;
                                      xmmword_1800AD880 = 0;
                                      *(_OWORD *)&hLibModule = 0;
                                      xmmword_1800AD8A0 = 0;
                                      xmmword_1800AD8B0 = 0;
                                      if ( *(_BYTE *)v463 )
                                      {
                                        do
                                        {
                                          v476 = -1;
                                          do
                                            v55 = v475[++v476] == 0;
                                          while ( !v55 );
                                          v477 = 24 * v473;
                                          v1414 = &WARBIRD::g_arModuleInfo + 3 * v473;
                                          if ( !GetModuleHandleExW(0, v475, (HMODULE *)v1414) )
                                            goto LABEL_572;
                                          v478 = (HMODULE *)v1414;
                                          v479 = &v475[v476];
                                          if ( **(_WORD **)v1414 == 23117 )
                                          {
                                            v480 = *(int *)(*(_QWORD *)v1414 + 60LL);
                                            if ( (unsigned int)v480 < 0x10000000 )
                                            {
                                              v481 = *(_QWORD *)v1414 + v480;
                                              if ( v481 >= *(_QWORD *)v1414 )
                                              {
                                                if ( *(_DWORD *)v481 == 17744 )
                                                {
                                                  if ( ((*(_WORD *)(v481 + 24) - 267) & 0xFEFF) != 0 )
                                                  {
                                                    v474 = -1073741811;
                                                  }
                                                  else
                                                  {
                                                    *(HMODULE *)((char *)&WARBIRD::g_arModuleInfo + v477 + 12) = *(HMODULE *)(v481 + 136);
                                                    v474 = 0;
                                                    *(_DWORD *)((char *)&WARBIRD::g_arModuleInfo + v477 + 8) = *(_DWORD *)(v481 + 80);
                                                  }
                                                  v478 = (HMODULE *)v1414;
                                                }
                                                else
                                                {
                                                  v474 = -1073741701;
                                                }
                                              }
                                              else
                                              {
                                                v474 = -1073741701;
                                              }
                                            }
                                            else
                                            {
                                              v474 = -1073741701;
                                            }
                                          }
                                          else
                                          {
                                            v474 = -1073741701;
                                          }
                                          v482 = *(_DWORD *)(v479 + 1);
                                          v483 = 0;
                                          v475 = v479 + 3;
                                          v1399 = v482;
                                          if ( v482 )
                                          {
                                            v484 = v1406;
                                            do
                                            {
                                              v485 = -1;
                                              do
                                                ++v485;
                                              while ( *((_BYTE *)v475 + v485) );
                                              if ( v474 >= 0 )
                                              {
                                                v486 = (void **)GetProcAddress(*v478, (LPCSTR)v475);
                                                if ( !v486 )
                                                {
                                                  v488 = GetProcessHeap();
                                                  HeapFree(v488, 0, lpMem);
                                                  goto LABEL_582;
                                                }
                                                (&WARBIRD::g_FuncAddress)[(unsigned int)v1406] = v486;
                                                v484 = v1406;
                                              }
                                              v478 = (HMODULE *)v1414;
                                              ++v484;
                                              v475 = (const WCHAR *)((char *)v475 + v485 + 1);
                                              ++v483;
                                              LODWORD(v1406) = v484;
                                            }
                                            while ( v483 < v1399 );
                                          }
                                          v473 = (unsigned int)++v1386;
                                        }
                                        while ( *(_BYTE *)v475 );
                                        v463 = (WCHAR *)lpMem;
                                      }
                                      v487 = GetProcessHeap();
                                      HeapFree(v487, 0, v463);
                                      if ( v474 >= 0 )
                                        goto LABEL_582;
                                    }
                                    else
                                    {
LABEL_572:
                                      v489 = GetProcessHeap();
                                      HeapFree(v489, 0, lpMem);
                                    }
                                  }
                                  if ( WARBIRD::g_arModuleInfo )
                                    FreeLibrary(WARBIRD::g_arModuleInfo);
                                  if ( *((_QWORD *)&xmmword_1800AD870 + 1) )
                                    FreeLibrary(*((HMODULE *)&xmmword_1800AD870 + 1));
                                  if ( hLibModule )
                                    FreeLibrary(hLibModule);
                                  if ( *((_QWORD *)&xmmword_1800AD8A0 + 1) )
                                    FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0 + 1));
                                  qword_1800AC100 = 0;
                                  WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                  off_1800AC078 = CIVIAudioFilter::IsDirty;
                                  off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                  off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                  off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC108 = CIVIAudioFilter::IsDirty;
                                  off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC138 = CIVIAudioFilter::IsDirty;
                                  off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                  xmmword_1800AD870 = 0;
                                  xmmword_1800AD880 = 0;
                                  *(_OWORD *)&hLibModule = 0;
                                  xmmword_1800AD8A0 = 0;
                                  xmmword_1800AD8B0 = 0;
                                  off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                  off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                  off_1800AC180 = CIVIAudioFilter::IsDirty;
                                  off_1800AC188 = CIVIAudioFilter::IsDirty;
                                  off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                }
                                _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                                v1409 = 0;
                                v1410 = 0;
                                while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                                  ;
                                if ( g_WarbirdSecureFunctionsRefCount )
                                {
LABEL_633:
                                  ++g_WarbirdSecureFunctionsRefCount;
                                }
                                else
                                {
                                  v490 = (char *)MemoryAllocT<unsigned long>(824);
                                  lpMem = v490;
                                  if ( v490 )
                                  {
                                    v491 = 0;
                                    v492 = qword_18009D240;
                                    v493 = 0;
                                    v494 = v490;
                                    v495 = 0;
                                    v496 = -1;
                                    v497 = 103;
                                    do
                                    {
                                      v498 = *(unsigned __int8 *)v492 << 8;
                                      v499 = *((unsigned __int8 *)v492 + 1);
                                      v500 = *((unsigned __int8 *)v492++ + 4);
                                      v501 = *((unsigned __int8 *)v492 - 5)
                                           | ((*((unsigned __int8 *)v492 - 6) | ((v498 | v499) << 8)) << 8);
                                      v502 = v495 ^ v501;
                                      v503 = *((unsigned __int8 *)v492 - 1)
                                           | ((*((unsigned __int8 *)v492 - 2)
                                             | ((*((unsigned __int8 *)v492 - 3) | (v500 << 8)) << 8)) << 8);
                                      v504 = v495 ^ v501 ^ v493 ^ v503 ^ 0xAC987321;
                                      v505 = v502 ^ (__ROR4__(v504, 22) + 4991 * __ROR4__(v504 + 1419157410, 27));
                                      v506 = v504 ^ (43881 * __ROR4__(v505 + 133239679, 9) - __ROR4__(v505, 30));
                                      v507 = v505 ^ (24670 * v506 - (v506 >> 13) - 123127970);
                                      v508 = v506 ^ (2033 * __ROR4__(v507 ^ 0xAB69, 26) - __ROR4__(v507, 30));
                                      v509 = v507 ^ (133239679 - (v508 ^ 0xAB69605E));
                                      v510 = v508 ^ (43881 * (v509 ^ 0x137F)) ^ __ROR4__(v509, 6);
                                      v511 = v509 ^ (__ROR4__(v510, 30) + 24670 * __ROR4__(v510 + 133239679, 15));
                                      v512 = v510 ^ (2033 * __ROR4__(v511 + 1419157410, 14) - __ROR4__(v511, 24));
                                      v513 = v511 ^ __ROR4__(v512, 10) ^ (4991 * __ROR4__(v512 ^ 0xAB69605E, 12));
                                      v514 = v512 ^ (v513 >> 10) ^ (43881 * (v513 ^ 0x7F1));
                                      v515 = v513 ^ (2033 * (__ROR4__(~v514, 5) + 24670));
                                      v516 = v515
                                           ^ (((v514 ^ (v515 - 2033) ^ 0xAB69605E) >> 2)
                                            + 4991 * __ROR4__(v514 ^ (v515 - 2033) ^ 0xAB6967AF, 30));
                                      v517 = v514
                                           ^ (v515 - 2033)
                                           ^ 0xAB69605E
                                           ^ (__ROR4__(v516, 25) + 43881 * __ROR4__(v516 - 133239679, 6));
                                      v518 = v516 ^ (24670 * (v517 ^ 0x137F) + __ROR4__(v517, 9));
                                      v519 = v517 ^ (__ROR4__(v518, 25) + 2033 * __ROR4__(v518 ^ 0xAB69, 27));
                                      v520 = v518 ^ v519 ^ 0xAC987321;
                                      v521 = v519 ^ (4991 * __ROR4__(v520, 3) - 219010071);
                                      v522 = v520 ^ (24670 * __ROR4__(v521 - 133239679, 1) - __ROR4__(v521, 6));
                                      v523 = v521 ^ (__ROR4__(v522, 18) + 2033 * __ROR4__(v522 - 1419157410, 29));
                                      v494 += 8;
                                      v524 = v522 ^ (4991 * __ROR4__(v523 - 1419157410, 17) - __ROR4__(v523, 14));
                                      v525 = v523 ^ (v524 >> 3) ^ (43881 * (v524 ^ 0x605E));
                                      v526 = __ROR4__(v525, 30);
                                      v493 = v496 ^ v525;
                                      v496 = v503;
                                      v495 = v491
                                           ^ v524
                                           ^ v526
                                           ^ (24670
                                            * __ROR4__(v523 ^ (v524 >> 3) ^ (43881 * (v524 ^ 0x605E)) ^ 0x7F1137F, 28));
                                      v491 = v501;
                                      *(v494 - 5) = v495;
                                      *(v494 - 1) = v493;
                                      *(v494 - 6) = __ROR4__(v495, 8);
                                      *(v494 - 2) = __ROR4__(v493, 8);
                                      *(v494 - 7) = __ROR4__(v495, 16);
                                      *(v494 - 3) = __ROR4__(v493, 16);
                                      *(v494 - 8) = __ROR4__(v495, 24);
                                      *(v494 - 4) = __ROR4__(v493, 24);
                                      --v497;
                                    }
                                    while ( v497 );
                                    v527 = (WCHAR *)lpMem;
                                    v528 = 0;
                                    v529 = 0;
                                    v530 = 0;
                                    do
                                    {
                                      v529 = _mm_xor_ps(
                                               v529,
                                               (__m128)_mm_loadu_si128((const __m128i *)((char *)lpMem + v528)));
                                      v531 = (__m128)_mm_loadu_si128((const __m128i *)((char *)lpMem + v528 + 16));
                                      v528 += 32LL;
                                      v532 = _mm_xor_ps(v531, v530);
                                      v530 = v532;
                                    }
                                    while ( v528 < 0x320 );
                                    v533 = _mm_xor_ps(v529, v532);
                                    v534 = _mm_xor_ps(v533, (__m128)_mm_srli_si128((__m128i)v533, 8));
                                    v535 = _mm_xor_ps(v534, (__m128)_mm_srli_si128((__m128i)v534, 4));
                                    v536 = _mm_xor_ps(v535, (__m128)_mm_srli_si128((__m128i)v535, 2));
                                    for ( ii = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                            v536,
                                                                            (__m128)_mm_srli_si128((__m128i)v536, 1)));
                                          v528 < 0x338;
                                          ++v528 )
                                    {
                                      ii ^= *((_BYTE *)lpMem + v528);
                                    }
                                    if ( ii == 64 )
                                    {
                                      v538 = 0;
                                      *((_BYTE *)lpMem + 823) = 0;
                                      v539 = 0;
                                      LODWORD(v1406) = 0;
                                      *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                      v1387 = 0;
                                      v540 = v527;
                                      xmmword_1800AD870 = 0;
                                      xmmword_1800AD880 = 0;
                                      *(_OWORD *)&hLibModule = 0;
                                      xmmword_1800AD8A0 = 0;
                                      xmmword_1800AD8B0 = 0;
                                      if ( *(_BYTE *)v527 )
                                      {
                                        do
                                        {
                                          v541 = -1;
                                          do
                                            v55 = v540[++v541] == 0;
                                          while ( !v55 );
                                          v542 = 24 * v538;
                                          v1414 = &WARBIRD::g_arModuleInfo + 3 * v538;
                                          if ( !GetModuleHandleExW(0, v540, (HMODULE *)v1414) )
                                            goto LABEL_623;
                                          v543 = (HMODULE *)v1414;
                                          v544 = &v540[v541];
                                          if ( **(_WORD **)v1414 == 23117 )
                                          {
                                            v545 = *(int *)(*(_QWORD *)v1414 + 60LL);
                                            if ( (unsigned int)v545 < 0x10000000 )
                                            {
                                              v546 = *(_QWORD *)v1414 + v545;
                                              if ( v546 >= *(_QWORD *)v1414 )
                                              {
                                                if ( *(_DWORD *)v546 == 17744 )
                                                {
                                                  if ( ((*(_WORD *)(v546 + 24) - 267) & 0xFEFF) != 0 )
                                                  {
                                                    v539 = -1073741811;
                                                  }
                                                  else
                                                  {
                                                    *(HMODULE *)((char *)&WARBIRD::g_arModuleInfo + v542 + 12) = *(HMODULE *)(v546 + 136);
                                                    v539 = 0;
                                                    *(_DWORD *)((char *)&WARBIRD::g_arModuleInfo + v542 + 8) = *(_DWORD *)(v546 + 80);
                                                  }
                                                  v543 = (HMODULE *)v1414;
                                                }
                                                else
                                                {
                                                  v539 = -1073741701;
                                                }
                                              }
                                              else
                                              {
                                                v539 = -1073741701;
                                              }
                                            }
                                            else
                                            {
                                              v539 = -1073741701;
                                            }
                                          }
                                          else
                                          {
                                            v539 = -1073741701;
                                          }
                                          v547 = *(_DWORD *)(v544 + 1);
                                          v548 = 0;
                                          v540 = v544 + 3;
                                          v1399 = v547;
                                          if ( v547 )
                                          {
                                            v549 = v1406;
                                            do
                                            {
                                              v550 = -1;
                                              do
                                                ++v550;
                                              while ( *((_BYTE *)v540 + v550) );
                                              if ( v539 >= 0 )
                                              {
                                                v551 = (void **)GetProcAddress(*v543, (LPCSTR)v540);
                                                if ( !v551 )
                                                {
                                                  v553 = GetProcessHeap();
                                                  HeapFree(v553, 0, lpMem);
                                                  goto LABEL_633;
                                                }
                                                (&WARBIRD::g_FuncAddress)[(unsigned int)v1406] = v551;
                                                v549 = v1406;
                                              }
                                              v543 = (HMODULE *)v1414;
                                              ++v549;
                                              v540 = (const WCHAR *)((char *)v540 + v550 + 1);
                                              ++v548;
                                              LODWORD(v1406) = v549;
                                            }
                                            while ( v548 < v1399 );
                                          }
                                          v538 = (unsigned int)++v1387;
                                        }
                                        while ( *(_BYTE *)v540 );
                                        v527 = (WCHAR *)lpMem;
                                      }
                                      v552 = GetProcessHeap();
                                      HeapFree(v552, 0, v527);
                                      if ( v539 >= 0 )
                                        goto LABEL_633;
                                    }
                                    else
                                    {
LABEL_623:
                                      v554 = GetProcessHeap();
                                      HeapFree(v554, 0, lpMem);
                                    }
                                  }
                                  if ( WARBIRD::g_arModuleInfo )
                                    FreeLibrary(WARBIRD::g_arModuleInfo);
                                  if ( *((_QWORD *)&xmmword_1800AD870 + 1) )
                                    FreeLibrary(*((HMODULE *)&xmmword_1800AD870 + 1));
                                  if ( hLibModule )
                                    FreeLibrary(hLibModule);
                                  if ( *((_QWORD *)&xmmword_1800AD8A0 + 1) )
                                    FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0 + 1));
                                  qword_1800AC100 = 0;
                                  WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                  off_1800AC078 = CIVIAudioFilter::IsDirty;
                                  off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                  off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                  off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC108 = CIVIAudioFilter::IsDirty;
                                  off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC138 = CIVIAudioFilter::IsDirty;
                                  off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                  xmmword_1800AD870 = 0;
                                  xmmword_1800AD880 = 0;
                                  *(_OWORD *)&hLibModule = 0;
                                  xmmword_1800AD8A0 = 0;
                                  xmmword_1800AD8B0 = 0;
                                  off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                  off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                  off_1800AC180 = CIVIAudioFilter::IsDirty;
                                  off_1800AC188 = CIVIAudioFilter::IsDirty;
                                  off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                  off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                }
                                _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                                LOWORD(Size) = (v425 >> 4) & 0xF;
                                WORD1(Size) = (v425 >> 8) & 0xF;
                                WORD2(Size) = (v425 >> 12) & 0xF;
                                *(_OWORD *)v1455 = 0;
                                *(_OWORD *)v1456 = 0;
                                v1457 = 0;
                                v1458 = 0;
                                v1459 = 0;
                                v1460 = 0;
                                v1461 = 0;
                                v1425 = 0;
                                v1403 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC128[0])(
                                                  0,
                                                  0,
                                                  1027);
                                v1400 = 0xFFFFFF;
                                if ( !v1403 )
                                {
                                  v555 = GetLastError();
                                  v556 = v555;
                                  if ( v555 > 0 )
                                    v556 = (unsigned __int16)v555 | 0x80070000;
                                  if ( v556 >= 0 )
                                    v556 = -2147467259;
                                  goto LABEL_1007;
                                }
                                v557 = 0;
                                v1404 = 0;
                                v1435 = 0;
                                v1428 = 0;
                                v1414 = 0;
                                Src = 0;
                                v1424 = 0;
                                memset(v1432, 0, sizeof(v1432));
                                v1411 = 0;
                                v1430 = 0;
                                if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_1800AC0D0[0])(
                                        8,
                                        &v1424,
                                        0,
                                        &v1430) )
                                {
LABEL_641:
                                  v558 = GetLastError();
                                  v559 = v558;
                                  if ( v558 > 0 )
                                    v559 = (unsigned __int16)v558 | 0x80070000;
                                  if ( v559 >= 0 )
                                    v559 = -2147467259;
                                  goto LABEL_985;
                                }
                                v560 = MemoryAllocT<unsigned long>(2LL * v1430);
                                SP_MEM<unsigned long>::operator=(&Src, v560);
                                v561 = (WARBIRD_DELAY_LOAD *)Src;
                                if ( !Src
                                  || (v562 = MemoryAllocT<unsigned long>(4LL * (v1424 + 1)),
                                      SP_MEM<unsigned long>::operator=(&v1411, v562),
                                      (v563 = (SIZE_T)v1411) == 0) )
                                {
                                  v559 = -2147024882;
LABEL_985:
                                  v1337 = v559;
                                  pcchLength = 0;
                                  v1402 = 0;
                                  lpMem = 0;
                                  SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1411);
                                  SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&Src);
                                  v556 = v1337;
                                  v615 = 0;
                                  goto LABEL_974;
                                }
                                if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, WARBIRD_DELAY_LOAD *, unsigned int *))off_1800AC0D0[0])(
                                        8,
                                        &v1424,
                                        v561,
                                        &v1430) )
                                  goto LABEL_641;
                                v564 = 0;
                                for ( jj = (_DWORD *)v563; v564 < v1424; ++v564 )
                                {
                                  *jj = off_1800AC0E0(v561, 0);
                                  v566 = -1;
                                  do
                                    v55 = *((_WORD *)v561 + ++v566) == 0;
                                  while ( !v55 );
                                  ++jj;
                                  v561 = (WARBIRD_DELAY_LOAD *)((char *)v561 + 2 * v566 + 2);
                                }
                                *jj = 1033;
                                v567 = v1424;
                                v1411 = 0;
                                v1404 = v563;
                                SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1411);
                                SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&Src);
                                v1388 = 0;
                                v568 = 0;
                                v569 = 0;
                                v570 = v567 + 1;
                                if ( v570 )
                                {
                                  do
                                  {
                                    for ( kk = 0; kk < 0x26; ++kk )
                                    {
                                      if ( *(_DWORD *)(v563 + 4LL * v569) == `CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::uLanguageArray[kk] )
                                      {
                                        v568 = kk;
                                        v1388 = kk;
                                        goto LABEL_660;
                                      }
                                    }
                                    ++v569;
                                  }
                                  while ( v569 < v570 );
                                }
LABEL_660:
                                v572 = v568;
                                v1398 = 0;
                                memset(v1556, 0, sizeof(v1556));
                                if ( ((unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64, _QWORD))off_1800AC0D8[0])(
                                       (unsigned int)`CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::uLanguageArray[v568],
                                       v1582,
                                       85,
                                       0)
                                  && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_1800AC0C0[0])(
                                       v1582,
                                       88,
                                       v1556,
                                       16) > 0 )
                                {
                                  v1398 = (HIDWORD(v1556[0]) >> 27) & 1;
                                }
                                v573 = -1;
                                v1454[0] = L"Segoe UI Light";
                                do
                                  v55 = `CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::wszFontArray[++v573] == 0;
                                while ( !v55 );
                                v574 = &`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::wszFontArray[v573];
                                v575 = -1;
                                v576 = v574 + 1;
                                v1454[1] = v576;
                                do
                                  v55 = v576[++v575] == 0;
                                while ( !v55 );
                                v577 = &v576[v575];
                                v578 = -1;
                                v579 = v577 + 1;
                                v1454[2] = v579;
                                do
                                  ++v578;
                                while ( v579[v578] );
                                v580 = &v579[v578 + 1];
                                v581 = -1;
                                v1454[3] = v580;
                                do
                                  ++v581;
                                while ( v580[v581] );
                                v582 = &v580[v581 + 1];
                                v583 = -1;
                                v1454[4] = v582;
                                do
                                  ++v583;
                                while ( v582[v583] );
                                v584 = &v582[v583 + 1];
                                v585 = -1;
                                v1454[5] = v584;
                                do
                                  ++v585;
                                while ( v584[v585] );
                                v586 = &v584[v585 + 1];
                                v587 = -1;
                                v1454[6] = v586;
                                do
                                  ++v587;
                                while ( v586[v587] );
                                v588 = (__int64)&v586[v587 + 1];
                                v589 = -1;
                                v1454[7] = v588;
                                do
                                  ++v589;
                                while ( *(_WORD *)(v588 + 2 * v589) );
                                v590 = v588 + 2 * (v589 + 1);
                                v591 = -1;
                                v1454[8] = v590;
                                do
                                  ++v591;
                                while ( *(_WORD *)(v590 + 2 * v591) );
                                v592 = v590 + 2 * (v591 + 1);
                                v593 = -1;
                                v1454[9] = v592;
                                do
                                  ++v593;
                                while ( *(_WORD *)(v592 + 2 * v593) );
                                v594 = v592 + 2 * (v593 + 1);
                                v595 = -1;
                                v1454[10] = v594;
                                do
                                  ++v595;
                                while ( *(_WORD *)(v594 + 2 * v595) );
                                v596 = v594 + 2 * (v595 + 1);
                                v597 = -1;
                                v1454[11] = v596;
                                do
                                  ++v597;
                                while ( *(_WORD *)(v596 + 2 * v597) );
                                v598 = v596 + 2 * (v597 + 1);
                                v599 = -1;
                                v1454[12] = v598;
                                do
                                  ++v599;
                                while ( *(_WORD *)(v598 + 2 * v599) );
                                v600 = v598 + 2 * (v599 + 1);
                                v601 = -1;
                                v1454[13] = v600;
                                do
                                  ++v601;
                                while ( *(_WORD *)(v600 + 2 * v601) );
                                v602 = v600 + 2 * (v601 + 1);
                                v603 = -1;
                                v1454[14] = v602;
                                do
                                  ++v603;
                                while ( *(_WORD *)(v602 + 2 * v603) );
                                v604 = v602 + 2 * (v603 + 1);
                                v605 = -1;
                                v1454[15] = v604;
                                do
                                  ++v605;
                                while ( *(_WORD *)(v604 + 2 * v605) );
                                v606 = v604 + 2 * (v605 + 1);
                                v607 = -1;
                                v1454[16] = v606;
                                do
                                  ++v607;
                                while ( *(_WORD *)(v606 + 2 * v607) );
                                v608 = v606 + 2 * (v607 + 1);
                                v609 = -1;
                                v1454[17] = v608;
                                do
                                  v55 = *(_WORD *)(v608 + 2 * v609++ + 2) == 0;
                                while ( !v55 );
                                v1454[18] = v608 + 2 + 2 * v609;
                                v610 = *((unsigned __int8 *)`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::LangFontIndexMapping
                                       + 3 * v572
                                       + 1);
                                pcchLength = v1454[*((unsigned __int8 *)`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::LangFontIndexMapping
                                                   + 3 * v572)];
                                v611 = v1454[v610];
                                v612 = *((unsigned __int8 *)`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::LangFontIndexMapping
                                       + 3 * v572
                                       + 2);
                                v1402 = v611;
                                lpMem = (LPVOID)v1454[v612];
                                v613 = MemoryAllocT<unsigned long>(7312);
                                v614 = (_BYTE *)v613;
                                if ( !v613 )
                                {
                                  v557 = v1428;
                                  v556 = -2147024882;
                                  v615 = (LPVOID *)v1428;
                                  goto LABEL_974;
                                }
                                v616 = 0;
                                v617 = `CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::bEncryptedStringBuffer;
                                v618 = 0;
                                v619 = v613;
                                v620 = 0;
                                v621 = -1;
                                v622 = 914;
                                do
                                {
                                  v623 = *(unsigned __int8 *)v617 << 8;
                                  v624 = *((unsigned __int8 *)v617 + 1);
                                  v625 = *((unsigned __int8 *)v617++ + 4);
                                  v626 = *((unsigned __int8 *)v617 - 5)
                                       | ((*((unsigned __int8 *)v617 - 6) | ((v623 | v624) << 8)) << 8);
                                  v627 = v620 ^ v626;
                                  v628 = *((unsigned __int8 *)v617 - 1)
                                       | ((*((unsigned __int8 *)v617 - 2)
                                         | ((*((unsigned __int8 *)v617 - 3) | (v625 << 8)) << 8)) << 8);
                                  v629 = v620 ^ v626 ^ v618 ^ v628 ^ 0xAC987321;
                                  v630 = v627 ^ (__ROR4__(v629, 22) + 4991 * __ROR4__(v629 + 1419157410, 27));
                                  v631 = v629 ^ (43881 * __ROR4__(v630 + 133239679, 9) - __ROR4__(v630, 30));
                                  v632 = v630 ^ (24670 * v631 - (v631 >> 13) - 123127970);
                                  v633 = v631 ^ (2033 * __ROR4__(v632 ^ 0xAB69, 26) - __ROR4__(v632, 30));
                                  v634 = v632 ^ (133239679 - (v633 ^ 0xAB69605E));
                                  v635 = v633 ^ (43881 * (v634 ^ 0x137F)) ^ __ROR4__(v634, 6);
                                  v636 = v634 ^ (__ROR4__(v635, 30) + 24670 * __ROR4__(v635 + 133239679, 15));
                                  v637 = v635 ^ (2033 * __ROR4__(v636 + 1419157410, 14) - __ROR4__(v636, 24));
                                  v638 = v636 ^ __ROR4__(v637, 10) ^ (4991 * __ROR4__(v637 ^ 0xAB69605E, 12));
                                  v639 = v637 ^ (v638 >> 10) ^ (43881 * (v638 ^ 0x7F1));
                                  v640 = v638 ^ (2033 * (__ROR4__(~v639, 5) + 24670));
                                  v641 = v640
                                       ^ (((v639 ^ (v640 - 2033) ^ 0xAB69605E) >> 2)
                                        + 4991 * __ROR4__(v639 ^ (v640 - 2033) ^ 0xAB6967AF, 30));
                                  v642 = v639
                                       ^ (v640 - 2033)
                                       ^ 0xAB69605E
                                       ^ (__ROR4__(v641, 25) + 43881 * __ROR4__(v641 - 133239679, 6));
                                  v643 = v641 ^ (24670 * (v642 ^ 0x137F) + __ROR4__(v642, 9));
                                  v644 = v642 ^ (__ROR4__(v643, 25) + 2033 * __ROR4__(v643 ^ 0xAB69, 27));
                                  v645 = v643 ^ v644 ^ 0xAC987321;
                                  v646 = v644 ^ (4991 * __ROR4__(v645, 3) - 219010071);
                                  v647 = v645 ^ (24670 * __ROR4__(v646 - 133239679, 1) - __ROR4__(v646, 6));
                                  v648 = v646 ^ (__ROR4__(v647, 18) + 2033 * __ROR4__(v647 - 1419157410, 29));
                                  v619 += 8;
                                  v649 = v647 ^ (4991 * __ROR4__(v648 - 1419157410, 17) - __ROR4__(v648, 14));
                                  v650 = v648 ^ (v649 >> 3) ^ (43881 * (v649 ^ 0x605E));
                                  v651 = v616 ^ __ROR4__(v650, 30) ^ (24670 * __ROR4__(v650 ^ 0x7F1137F, 28));
                                  v616 = v626;
                                  v620 = v649 ^ v651;
                                  *(_BYTE *)(v619 - 5) = v620;
                                  v618 = v650 ^ v621;
                                  *(_BYTE *)(v619 - 1) = v650 ^ v621;
                                  v621 = v628;
                                  *(_BYTE *)(v619 - 6) = __ROR4__(v620, 8);
                                  *(_BYTE *)(v619 - 2) = __ROR4__(v618, 8);
                                  *(_BYTE *)(v619 - 7) = __ROR4__(v620, 16);
                                  *(_BYTE *)(v619 - 3) = __ROR4__(v618, 16);
                                  *(_BYTE *)(v619 - 8) = __ROR4__(v620, 24);
                                  *(_BYTE *)(v619 - 4) = __ROR4__(v618, 24);
                                  --v622;
                                }
                                while ( v622 );
                                v652 = 0;
                                v653 = 0;
                                v654 = 0;
                                do
                                {
                                  v653 = _mm_xor_ps(v653, (__m128)_mm_loadu_si128((const __m128i *)&v614[v652]));
                                  v655 = (__m128)_mm_loadu_si128((const __m128i *)&v614[v652 + 16]);
                                  v652 += 32LL;
                                  v654 = _mm_xor_ps(v654, v655);
                                }
                                while ( v652 < 0x1C80 );
                                v656 = _mm_xor_ps(v654, v653);
                                v657 = _mm_xor_ps(v656, (__m128)_mm_srli_si128((__m128i)v656, 8));
                                v658 = _mm_xor_ps(v657, (__m128)_mm_srli_si128((__m128i)v657, 4));
                                v659 = _mm_xor_ps(v658, (__m128)_mm_srli_si128((__m128i)v658, 2));
                                for ( mm = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                        v659,
                                                                        (__m128)_mm_srli_si128((__m128i)v659, 1)));
                                      v652 < 0x1C90;
                                      ++v652 )
                                {
                                  mm ^= v614[v652];
                                }
                                if ( mm != 127 )
                                {
                                  v661 = GetProcessHeap();
                                  HeapFree(v661, 0, v614);
                                  v557 = v1428;
                                  v556 = -1073425151;
                                  v615 = (LPVOID *)v1428;
                                  goto LABEL_974;
                                }
                                v557 = 7312;
                                v1428 = 7312;
                                v662 = 0;
                                v1435 = v614;
                                while ( 2 )
                                {
                                  v663 = -1;
                                  if ( !v1388 )
                                  {
                                    *((_QWORD *)v1432 + v662) = v614;
                                    do
                                      ++v663;
                                    while ( v614[v663] );
                                    v664 = v662;
                                    v665 = &v614[v663 + 1];
                                    goto LABEL_714;
                                  }
                                  v664 = v662;
                                  do
                                    v55 = v614[++v663] == 0;
                                  while ( !v55 );
                                  v665 = &v614[v663 + 1];
                                  if ( v1388 == 1 )
                                  {
                                    v666 = 8 * v662;
                                    v741 = -1;
                                    *((_QWORD *)v1432 + v662) = v665;
                                    do
                                      ++v741;
                                    while ( v665[v741] );
                                    v668 = (__int64)&v665[v741 + 1];
LABEL_826:
                                    v742 = -1;
                                    v743 = (__int64 *)((char *)v1432 + v666);
                                    do
                                      v55 = *(_BYTE *)(v668 + v742++ + 1) == 0;
                                    while ( !v55 );
                                    v744 = v742 + 1;
                                    v745 = -1;
                                    v746 = v668 + v744;
                                    if ( v1388 == 3 )
                                    {
                                      *v743 = v746;
                                      do
                                        v55 = *(_BYTE *)(v746 + v745++ + 1) == 0;
                                      while ( !v55 );
                                      v747 = v745 + 1;
                                      v674 = -1;
                                      v675 = v746 + v747;
                                      do
                                        ++v674;
                                      while ( *(_BYTE *)(v675 + v674) );
                                      goto LABEL_723;
                                    }
                                    do
                                      v55 = *(_BYTE *)(v746 + v745++ + 1) == 0;
                                    while ( !v55 );
                                    v748 = v745 + 1;
                                    v674 = -1;
                                    v675 = v746 + v748;
                                    if ( v1388 == 4 )
                                    {
                                      *v743 = v675;
                                      do
                                        ++v674;
                                      while ( *(_BYTE *)(v675 + v674) );
                                      goto LABEL_723;
                                    }
                                    do
                                      ++v674;
                                    while ( *(_BYTE *)(v675 + v674) );
                                    v676 = v675 + v674 + 1;
                                    if ( v1388 == 5 )
                                    {
                                      *v743 = v676;
                                      v749 = -1;
                                      do
                                        ++v749;
                                      while ( *(_BYTE *)(v676 + v749) );
                                      v678 = v749 + v676 + 1;
LABEL_844:
                                      v750 = -1;
                                      do
                                        v55 = *(_BYTE *)(v678 + v750++ + 1) == 0;
                                      while ( !v55 );
                                      v680 = v678 + v750 + 1;
                                      if ( v1388 == 7 )
                                      {
                                        *((_QWORD *)v1432 + v662) = v680;
                                        v751 = -1;
                                        do
                                          ++v751;
                                        while ( *(_BYTE *)(v680 + v751) );
                                        v682 = v751 + v680 + 1;
LABEL_850:
                                        v752 = -1;
                                        do
                                          v55 = *(_BYTE *)(v682 + v752++ + 1) == 0;
                                        while ( !v55 );
                                        v684 = v682 + v752 + 1;
                                        if ( v1388 == 9 )
                                        {
                                          *((_QWORD *)v1432 + v662) = v684;
                                          v753 = -1;
                                          do
                                            ++v753;
                                          while ( *(_BYTE *)(v684 + v753) );
                                          v686 = v753 + v684 + 1;
LABEL_856:
                                          v754 = -1;
                                          do
                                            v55 = *(_BYTE *)(v686 + v754++ + 1) == 0;
                                          while ( !v55 );
                                          v688 = v686 + v754 + 1;
                                          if ( v1388 == 11 )
                                          {
                                            *((_QWORD *)v1432 + v662) = v688;
                                            v755 = -1;
                                            do
                                              ++v755;
                                            while ( *(_BYTE *)(v688 + v755) );
                                            v690 = v755 + v688 + 1;
LABEL_862:
                                            v756 = -1;
                                            do
                                              v55 = *(_BYTE *)(v690 + v756++ + 1) == 0;
                                            while ( !v55 );
                                            v692 = v690 + v756 + 1;
                                            if ( v1388 == 13 )
                                            {
                                              *((_QWORD *)v1432 + v662) = v692;
                                              v757 = -1;
                                              do
                                                ++v757;
                                              while ( *(_BYTE *)(v692 + v757) );
                                              v694 = v757 + v692 + 1;
LABEL_868:
                                              v758 = -1;
                                              do
                                                v55 = *(_BYTE *)(v694 + v758++ + 1) == 0;
                                              while ( !v55 );
                                              v696 = v694 + v758 + 1;
                                              if ( v1388 == 15 )
                                              {
                                                *((_QWORD *)v1432 + v662) = v696;
                                                v759 = -1;
                                                do
                                                  ++v759;
                                                while ( *(_BYTE *)(v696 + v759) );
                                                v698 = v759 + v696 + 1;
LABEL_874:
                                                v760 = -1;
                                                do
                                                  v55 = *(_BYTE *)(v698 + v760++ + 1) == 0;
                                                while ( !v55 );
                                                v700 = v698 + v760 + 1;
                                                if ( v1388 == 17 )
                                                {
                                                  *((_QWORD *)v1432 + v662) = v700;
                                                  v761 = -1;
                                                  do
                                                    ++v761;
                                                  while ( *(_BYTE *)(v700 + v761) );
                                                  v702 = v761 + v700 + 1;
LABEL_880:
                                                  v762 = -1;
                                                  do
                                                    v55 = *(_BYTE *)(v702 + v762++ + 1) == 0;
                                                  while ( !v55 );
                                                  v704 = v702 + v762 + 1;
                                                  if ( v1388 == 19 )
                                                  {
                                                    *((_QWORD *)v1432 + v662) = v704;
                                                    v763 = -1;
                                                    do
                                                      ++v763;
                                                    while ( *(_BYTE *)(v704 + v763) );
                                                    v706 = v763 + v704 + 1;
LABEL_886:
                                                    v764 = -1;
                                                    do
                                                      v55 = *(_BYTE *)(v706 + v764++ + 1) == 0;
                                                    while ( !v55 );
                                                    v708 = v706 + v764 + 1;
                                                    if ( v1388 == 21 )
                                                    {
                                                      *((_QWORD *)v1432 + v662) = v708;
                                                      v765 = -1;
                                                      do
                                                        ++v765;
                                                      while ( *(_BYTE *)(v708 + v765) );
                                                      v710 = v765 + v708 + 1;
LABEL_892:
                                                      v766 = -1;
                                                      do
                                                        v55 = *(_BYTE *)(v710 + v766++ + 1) == 0;
                                                      while ( !v55 );
                                                      v712 = v710 + v766 + 1;
                                                      if ( v1388 == 23 )
                                                      {
                                                        *((_QWORD *)v1432 + v662) = v712;
                                                        v767 = -1;
                                                        do
                                                          ++v767;
                                                        while ( *(_BYTE *)(v712 + v767) );
                                                        v714 = v767 + v712 + 1;
LABEL_898:
                                                        v768 = -1;
                                                        do
                                                          v55 = *(_BYTE *)(v714 + v768++ + 1) == 0;
                                                        while ( !v55 );
                                                        v716 = v714 + v768 + 1;
                                                        if ( v1388 == 25 )
                                                        {
                                                          *((_QWORD *)v1432 + v662) = v716;
                                                          v769 = -1;
                                                          do
                                                            ++v769;
                                                          while ( *(_BYTE *)(v716 + v769) );
                                                          v718 = v769 + v716 + 1;
LABEL_904:
                                                          v770 = -1;
                                                          do
                                                            v55 = *(_BYTE *)(v718 + v770++ + 1) == 0;
                                                          while ( !v55 );
                                                          v720 = v718 + v770 + 1;
                                                          if ( v1388 == 27 )
                                                          {
                                                            *((_QWORD *)v1432 + v662) = v720;
                                                            v771 = -1;
                                                            do
                                                              ++v771;
                                                            while ( *(_BYTE *)(v720 + v771) );
                                                            v722 = v771 + v720 + 1;
LABEL_910:
                                                            v772 = -1;
                                                            do
                                                              v55 = *(_BYTE *)(v722 + v772++ + 1) == 0;
                                                            while ( !v55 );
                                                            v724 = v722 + v772 + 1;
                                                            if ( v1388 == 29 )
                                                            {
                                                              *((_QWORD *)v1432 + v662) = v724;
                                                              v773 = -1;
                                                              do
                                                                ++v773;
                                                              while ( *(_BYTE *)(v724 + v773) );
                                                              v726 = v773 + v724 + 1;
LABEL_916:
                                                              v774 = -1;
                                                              do
                                                                v55 = *(_BYTE *)(v726 + v774++ + 1) == 0;
                                                              while ( !v55 );
                                                              v728 = v726 + v774 + 1;
                                                              if ( v1388 == 31 )
                                                              {
                                                                *((_QWORD *)v1432 + v662) = v728;
                                                                v775 = -1;
                                                                do
                                                                  ++v775;
                                                                while ( *(_BYTE *)(v728 + v775) );
                                                                v730 = v775 + v728 + 1;
LABEL_922:
                                                                v776 = -1;
                                                                do
                                                                  v55 = *(_BYTE *)(v730 + v776++ + 1) == 0;
                                                                while ( !v55 );
                                                                v732 = v730 + v776 + 1;
                                                                if ( v1388 == 33 )
                                                                {
                                                                  *((_QWORD *)v1432 + v662) = v732;
                                                                  v777 = -1;
                                                                  do
                                                                    ++v777;
                                                                  while ( *(_BYTE *)(v732 + v777) );
                                                                  v734 = v777 + v732 + 1;
LABEL_928:
                                                                  v778 = -1;
                                                                  do
                                                                    v55 = *(_BYTE *)(v734 + v778++ + 1) == 0;
                                                                  while ( !v55 );
                                                                  v736 = v734 + v778 + 1;
                                                                  if ( v1388 == 35 )
                                                                  {
                                                                    *((_QWORD *)v1432 + v662) = v736;
                                                                    v779 = -1;
                                                                    do
                                                                      ++v779;
                                                                    while ( *(_BYTE *)(v736 + v779) );
                                                                    v738 = v779 + v736 + 1;
                                                                    goto LABEL_934;
                                                                  }
LABEL_814:
                                                                  v737 = -1;
                                                                  do
                                                                    v55 = *(_BYTE *)(v736 + v737++ + 1) == 0;
                                                                  while ( !v55 );
                                                                  v738 = v736 + v737 + 1;
                                                                  if ( v1388 == 36 )
                                                                  {
                                                                    *((_QWORD *)v1432 + v662) = v738;
                                                                    v739 = -1;
                                                                    do
                                                                      v55 = *(_BYTE *)(v738 + v739++ + 1) == 0;
                                                                    while ( !v55 );
                                                                    v740 = v738 + v739 + 1;
                                                                  }
                                                                  else
                                                                  {
LABEL_934:
                                                                    v780 = -1;
                                                                    do
                                                                      v55 = *(_BYTE *)(v738 + v780++ + 1) == 0;
                                                                    while ( !v55 );
                                                                    v740 = v738 + v780 + 1;
                                                                    if ( v1388 == 37 )
                                                                      *((_QWORD *)v1432 + v662) = v740;
                                                                  }
                                                                  v781 = -1;
                                                                  do
                                                                    v55 = *(_BYTE *)(v740 + v781++ + 1) == 0;
                                                                  while ( !v55 );
                                                                  ++v662;
                                                                  v614 = (_BYTE *)(v740 + v781 + 1);
                                                                  if ( v662 == 6 )
                                                                  {
                                                                    v782 = MemoryAllocT<unsigned short *>();
                                                                    SP_MEM<unsigned long>::operator=(&v1414, v782);
                                                                    v615 = (LPVOID *)v1414;
                                                                    if ( v1414 )
                                                                    {
                                                                      *(_OWORD *)v1414 = 0;
                                                                      v615[2] = 0;
                                                                      v783 = 0;
                                                                      while ( 2 )
                                                                      {
                                                                        v784 = 0;
                                                                        while ( *((_WORD *)&Size + v783) != `CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::wStringIds[v784] )
                                                                        {
                                                                          v784 = (unsigned int)(v784 + 1);
                                                                          if ( (unsigned int)v784 >= 6 )
                                                                            goto LABEL_954;
                                                                        }
                                                                        v785 = *((_QWORD *)v1432 + v784);
                                                                        v786 = -1;
                                                                        do
                                                                          ++v786;
                                                                        while ( *(_BYTE *)(v785 + v786) );
                                                                        v787 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_1800AC0F0[0])(
                                                                                 65001,
                                                                                 0,
                                                                                 v785,
                                                                                 (unsigned int)(v786 + 1),
                                                                                 0,
                                                                                 0);
                                                                        v788 = v787;
                                                                        if ( !v787 )
                                                                          goto LABEL_956;
                                                                        v789 = MemoryAllocT<unsigned long>(2LL * v787);
                                                                        v615[v783] = (LPVOID)v789;
                                                                        if ( !v789 )
                                                                        {
                                                                          v557 = v1428;
                                                                          goto LABEL_962;
                                                                        }
                                                                        v790 = -1;
                                                                        do
                                                                          ++v790;
                                                                        while ( *(_BYTE *)(v785 + v790) );
                                                                        if ( !((unsigned int (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int))off_1800AC0F0[0])(
                                                                                65001,
                                                                                0,
                                                                                v785,
                                                                                (unsigned int)(v790 + 1),
                                                                                v789,
                                                                                v788) )
                                                                        {
LABEL_956:
                                                                          v791 = GetLastError();
                                                                          v556 = v791;
                                                                          if ( v791 > 0 )
                                                                            v556 = (unsigned __int16)v791 | 0x80070000;
                                                                          v557 = v1428;
                                                                          if ( v556 >= 0 )
                                                                            v556 = -2147467259;
                                                                          goto LABEL_963;
                                                                        }
LABEL_954:
                                                                        v783 = (unsigned int)(v783 + 1);
                                                                        if ( (unsigned int)v783 < 3 )
                                                                          continue;
                                                                        break;
                                                                      }
                                                                      v556 = 0;
                                                                      v557 = v1428;
                                                                      LODWORD(v1455[0]) = v1398;
                                                                      v1414 = 0;
                                                                      v1410 = (SIZE_T)v615;
                                                                    }
                                                                    else
                                                                    {
LABEL_962:
                                                                      v556 = -2147024882;
LABEL_963:
                                                                      v1336 = v556;
                                                                      if ( v615 )
                                                                      {
                                                                        for ( nn = 0; nn != 3; ++nn )
                                                                        {
                                                                          v793 = v615[nn];
                                                                          if ( v793 )
                                                                          {
                                                                            v794 = -1;
                                                                            do
                                                                              v55 = *(_WORD *)&v793[2 * v794++ + 2] == 0;
                                                                            while ( !v55 );
                                                                            for ( i1 = 2 * v794 + 2; i1; --i1 )
                                                                              *v793++ = 0;
                                                                            v796 = v615[nn];
                                                                            v797 = GetProcessHeap();
                                                                            HeapFree(v797, 0, v796);
                                                                          }
                                                                        }
                                                                        v556 = v1336;
                                                                      }
                                                                      v615 = (LPVOID *)v1409;
                                                                    }
LABEL_974:
                                                                    v798 = v1435;
                                                                    if ( v1435 && v557 )
                                                                    {
                                                                      do
                                                                      {
                                                                        *v798++ = 0;
                                                                        --v557;
                                                                      }
                                                                      while ( v557 );
                                                                    }
                                                                    SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1414);
                                                                    SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1435);
                                                                    SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1404);
                                                                    if ( v556 < 0 )
                                                                      goto LABEL_1006;
                                                                    v1455[1] = *v615;
                                                                    v1456[0] = v615[1];
                                                                    v1456[1] = v615[2];
                                                                    v1450 = 0;
                                                                    LODWORD(v1450) = 16;
                                                                    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_1800AC198)(
                                                                                          66,
                                                                                          0,
                                                                                          &v1450,
                                                                                          0) )
                                                                    {
                                                                      v799 = GetLastError();
                                                                      v556 = v799;
                                                                      if ( v799 > 0 )
                                                                        v556 = (unsigned __int16)v799 | 0x80070000;
                                                                      HIDWORD(v1455[0]) = 0;
                                                                      if ( v556 >= 0 )
                                                                        v556 = -2147467259;
                                                                      goto LABEL_1006;
                                                                    }
                                                                    v800 = v425 & 0xF;
                                                                    HIDWORD(v1455[0]) = BYTE4(v1450) & 1;
                                                                    LODWORD(v1413) = 42;
                                                                    if ( v800 == 1 )
                                                                    {
                                                                      v801 = 42;
                                                                    }
                                                                    else
                                                                    {
                                                                      if ( (v425 & 0xF) != 2 )
                                                                      {
                                                                        if ( (v425 & 0xF) == 3 )
                                                                        {
                                                                          v801 = 225;
                                                                          LODWORD(v1406) = 225;
                                                                        }
                                                                        else
                                                                        {
                                                                          v801 = 0;
                                                                          LODWORD(v1406) = 0;
                                                                        }
LABEL_994:
                                                                        memset_0(v1572, 0, 0xDCu);
                                                                        v1573 = 220;
                                                                        if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_1800AC110[0])(
                                                                               0,
                                                                               0xFFFFFFFFLL,
                                                                               v1572) )
                                                                        {
                                                                          v802 = v1574;
                                                                          v803 = v1575;
                                                                          v1389 = v1576;
                                                                          if ( v1574 < 0x60u )
                                                                            v802 = 96;
                                                                        }
                                                                        else
                                                                        {
                                                                          v803 = 0;
                                                                          v802 = 96;
                                                                          v1389 = 0;
                                                                        }
                                                                        v804 = (size_t)lpMem;
                                                                        v1561[0] = 0;
                                                                        v1557 = 0;
                                                                        if ( v800 == 1 )
                                                                          v804 = pcchLength;
                                                                        v1358 = (unsigned __int16 *)v804;
                                                                        *(_OWORD *)v1558 = 0;
                                                                        v1559 = 0;
                                                                        v1560 = 0;
                                                                        *(_OWORD *)((char *)v1561 + 12) = 0;
                                                                        v1404 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC128[0])(
                                                                                  0,
                                                                                  0,
                                                                                  1027);
                                                                        if ( !v1404 )
                                                                        {
                                                                          v805 = GetLastError();
                                                                          v556 = v805;
                                                                          if ( v805 > 0 )
                                                                            v556 = (unsigned __int16)v805 | 0x80070000;
                                                                          if ( v556 >= 0 )
                                                                            v556 = -2147467259;
                                                                          goto LABEL_1006;
                                                                        }
                                                                        v812 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC0E8)(
                                                                                 v801,
                                                                                 v802,
                                                                                 72);
                                                                        *(_DWORD *)v1558 = 400;
                                                                        LODWORD(v1557) = -v812;
                                                                        LOBYTE(v1558[5]) = 5;
                                                                        StringCchCopyW(&v1558[6], 0x20u, v1358);
                                                                        v813 = ((__int64 (__fastcall *)(__int128 *))off_1800AC050[0])(&v1557);
                                                                        if ( v813 )
                                                                        {
                                                                          v556 = 0;
                                                                          *(_QWORD *)&v1457 = v813;
                                                                        }
                                                                        else
                                                                        {
                                                                          v814 = GetLastError();
                                                                          v556 = v814;
                                                                          if ( v814 > 0 )
                                                                            v556 = (unsigned __int16)v814 | 0x80070000;
                                                                          if ( v556 >= 0 )
                                                                            v556 = -2147467259;
                                                                        }
                                                                        off_1800AC190[0](0, v1404);
                                                                        if ( v556 < 0 )
                                                                          goto LABEL_1006;
                                                                        v815 = lpMem;
                                                                        v1566[0] = 0;
                                                                        v1562 = 0;
                                                                        if ( v800 == 1 )
                                                                          v815 = (void *)pcchLength;
                                                                        lpMem = v815;
                                                                        *(_OWORD *)v1563 = 0;
                                                                        v1564 = 0;
                                                                        v1565 = 0;
                                                                        *(_OWORD *)((char *)v1566 + 12) = 0;
                                                                        v816 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC128[0])(
                                                                                 0,
                                                                                 0,
                                                                                 1027);
                                                                        if ( !v816 )
                                                                        {
LABEL_1041:
                                                                          v817 = GetLastError();
                                                                          v556 = v817;
                                                                          if ( v817 > 0 )
                                                                            v556 = (unsigned __int16)v817 | 0x80070000;
                                                                          if ( v556 >= 0 )
                                                                            v556 = -2147467259;
                                                                          goto LABEL_1006;
                                                                        }
                                                                        v818 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC0E8)(
                                                                                 (unsigned int)v1406,
                                                                                 v802,
                                                                                 72);
                                                                        *(_DWORD *)v1563 = 400;
                                                                        LODWORD(v1562) = -v818;
                                                                        LOBYTE(v1563[5]) = 5;
                                                                        StringCchCopyW(
                                                                          &v1563[6],
                                                                          0x20u,
                                                                          (const unsigned __int16 *)lpMem);
                                                                        v819 = ((__int64 (__fastcall *)(__int128 *))off_1800AC050[0])(&v1562);
                                                                        if ( v819 )
                                                                        {
                                                                          v821 = 0;
                                                                          *((_QWORD *)&v1457 + 1) = v819;
                                                                        }
                                                                        else
                                                                        {
                                                                          v820 = GetLastError();
                                                                          v821 = v820;
                                                                          if ( v820 > 0 )
                                                                            v821 = (unsigned __int16)v820 | 0x80070000;
                                                                          if ( v821 >= 0 )
                                                                            v821 = -2147467259;
                                                                        }
                                                                        v1338 = v821;
                                                                        off_1800AC190[0](0, v816);
                                                                        v556 = v1338;
                                                                        if ( v1338 < 0 )
                                                                          goto LABEL_1006;
                                                                        if ( v800 == 1 )
                                                                          goto LABEL_1060;
                                                                        if ( v800 == 2 )
                                                                        {
                                                                          *((_QWORD *)&v1425 + 1) = (unsigned int)(v803 / 4);
                                                                          v803 /= 4;
                                                                          goto LABEL_1059;
                                                                        }
                                                                        if ( v800 != 3 )
                                                                        {
                                                                          v803 = 0;
                                                                          v822 = 0;
                                                                          goto LABEL_1061;
                                                                        }
LABEL_1060:
                                                                        v822 = v1389;
LABEL_1061:
                                                                        *((_QWORD *)&v1425 + 1) = __PAIR64__(v822, v803);
                                                                        if ( v800 != 1 )
                                                                        {
                                                                          if ( (unsigned int)(v800 - 2) >= 2 )
                                                                          {
                                                                            v823 = 0;
                                                                            LODWORD(v1406) = 0;
                                                                            LODWORD(v1413) = 0;
                                                                            goto LABEL_1065;
                                                                          }
LABEL_1059:
                                                                          v823 = 0;
                                                                          LODWORD(v1413) = 0;
                                                                          LODWORD(v1406) = 0;
                                                                          goto LABEL_1065;
                                                                        }
                                                                        v823 = 150;
                                                                        LODWORD(v1406) = 32;
LABEL_1065:
                                                                        v1398 = v823;
                                                                        v824 = v803 - v823;
                                                                        v825 = v1455[1];
                                                                        DWORD1(v1460) = v824;
                                                                        DWORD1(v1459) = v824;
                                                                        v1359 = (unsigned __int16 *)((__int64 (__fastcall *)(void *, _QWORD))off_1800AC0A8)(v1403, v1457);
                                                                        v826 = ((__int64 (__fastcall *)(void *, LPVOID, __int64, char *, int, _QWORD))off_1800AC108)(
                                                                                 v1403,
                                                                                 v825,
                                                                                 0xFFFFFFFFLL,
                                                                                 (char *)&v1458 + 12,
                                                                                 3152,
                                                                                 0);
                                                                        v827 = -2147467259;
                                                                        if ( v826 )
                                                                          v827 = 0;
                                                                        v1339 = v827;
                                                                        if ( v1359 )
                                                                          off_1800AC0A8(
                                                                            (WARBIRD_DELAY_LOAD *)v1403,
                                                                            (int)v1359);
                                                                        if ( !v826 )
                                                                          goto LABEL_1116;
                                                                        v828 = v1456[0];
                                                                        v1360 = (unsigned __int16 *)((__int64 (__fastcall *)(void *, _QWORD))off_1800AC0A8)(v1403, *((_QWORD *)&v1457 + 1));
                                                                        v829 = ((__int64 (__fastcall *)(void *, LPVOID, __int64, char *, int, _QWORD))off_1800AC108)(
                                                                                 v1403,
                                                                                 v828,
                                                                                 0xFFFFFFFFLL,
                                                                                 (char *)&v1459 + 12,
                                                                                 3152,
                                                                                 0);
                                                                        v830 = -2147467259;
                                                                        if ( v829 )
                                                                          v830 = 0;
                                                                        v1339 = v830;
                                                                        if ( v1360 )
                                                                          off_1800AC0A8(
                                                                            (WARBIRD_DELAY_LOAD *)v1403,
                                                                            (int)v1360);
                                                                        if ( !v829 )
                                                                          goto LABEL_1116;
                                                                        if ( v800 == 2 || v800 == 3 )
                                                                        {
                                                                          v824 = DWORD1(v1460);
                                                                          if ( SDWORD1(v1459) > SDWORD1(v1460) )
                                                                            v824 = DWORD1(v1459);
                                                                        }
                                                                        if ( LODWORD(v1455[0]) )
                                                                        {
                                                                          ((void (__fastcall *)(char *, _QWORD, _QWORD))off_1800AC180)(
                                                                            (char *)&v1458 + 12,
                                                                            v824 - DWORD1(v1459),
                                                                            (unsigned int)v1413);
                                                                          v831 = v824 - DWORD1(v1460);
                                                                        }
                                                                        else
                                                                        {
                                                                          ((void (__fastcall *)(char *, _QWORD, _QWORD))off_1800AC180)(
                                                                            (char *)&v1458 + 12,
                                                                            v1398,
                                                                            (unsigned int)v1413);
                                                                          v831 = v1398;
                                                                        }
                                                                        ((void (__fastcall *)(char *, __int64, _QWORD))off_1800AC180)(
                                                                          (char *)&v1459 + 12,
                                                                          v831,
                                                                          (unsigned int)(DWORD2(v1459) + v1406));
                                                                        if ( (unsigned int)(v800 - 2) <= 1 )
                                                                        {
                                                                          v843 = DWORD2(v1460);
                                                                          *((_QWORD *)&v1425 + 1) = __PAIR64__(DWORD2(v1460), v824);
                                                                          DWORD2(v1458) = -5723992;
                                                                        }
                                                                        else
                                                                        {
                                                                          if ( v800 == 1 )
                                                                          {
                                                                            memset(v1571, 0, sizeof(v1571));
                                                                            DWORD2(v1458) = 0xFFFFFF;
                                                                            v1567 = 0;
                                                                            *(_OWORD *)v1568 = 0;
                                                                            v1569 = 0;
                                                                            v1570 = 0;
                                                                            v832 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC128[0])(
                                                                                     0,
                                                                                     0,
                                                                                     1027);
                                                                            if ( !v832 )
                                                                              goto LABEL_1041;
                                                                            v833 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))off_1800AC0E8)(
                                                                                     11,
                                                                                     v802,
                                                                                     72);
                                                                            *(_DWORD *)v1568 = 400;
                                                                            LODWORD(v1567) = -v833;
                                                                            LOBYTE(v1568[5]) = 5;
                                                                            StringCchCopyW(
                                                                              &v1568[6],
                                                                              0x20u,
                                                                              (const unsigned __int16 *)v1402);
                                                                            v834 = ((__int64 (__fastcall *)(__int128 *))off_1800AC050[0])(&v1567);
                                                                            if ( v834 )
                                                                            {
                                                                              v836 = 0;
                                                                              *(_QWORD *)&v1458 = v834;
                                                                            }
                                                                            else
                                                                            {
                                                                              v835 = GetLastError();
                                                                              v836 = v835;
                                                                              if ( v835 > 0 )
                                                                                v836 = (unsigned __int16)v835
                                                                                     | 0x80070000;
                                                                              if ( v836 >= 0 )
                                                                                v836 = -2147467259;
                                                                            }
                                                                            v1340 = v836;
                                                                            off_1800AC190[0](0, v832);
                                                                            v556 = v1340;
                                                                            if ( v1340 >= 0 )
                                                                            {
                                                                              v837 = v1456[1];
                                                                              DWORD1(v1461) = v824;
                                                                              v838 = (WARBIRD_DELAY_LOAD *)v1403;
                                                                              v839 = ((__int64 (__fastcall *)(void *, _QWORD))off_1800AC0A8)(
                                                                                       v1403,
                                                                                       v1458);
                                                                              v840 = ((__int64 (__fastcall *)(WARBIRD_DELAY_LOAD *, LPVOID, __int64, char *, int, _QWORD))off_1800AC108)(
                                                                                       v838,
                                                                                       v837,
                                                                                       0xFFFFFFFFLL,
                                                                                       (char *)&v1460 + 12,
                                                                                       1120,
                                                                                       0);
                                                                              v841 = -2147467259;
                                                                              if ( v840 )
                                                                                v841 = 0;
                                                                              v1339 = v841;
                                                                              if ( v839 )
                                                                                off_1800AC0A8(v838, v839);
                                                                              if ( v840 )
                                                                              {
                                                                                v842 = DWORD1(v1461) + 24;
                                                                                DWORD2(v1461) = 32;
                                                                                if ( DWORD1(v1461) + 24 < 90 )
                                                                                  v842 = 90;
                                                                                DWORD1(v1461) = v842;
                                                                                HIDWORD(v1460) = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC0E8)(
                                                                                                   HIDWORD(v1460),
                                                                                                   v802,
                                                                                                   96);
                                                                                LODWORD(v1461) = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC0E8)(
                                                                                                   (unsigned int)v1461,
                                                                                                   v802,
                                                                                                   96);
                                                                                DWORD1(v1461) = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC0E8)(
                                                                                                  DWORD1(v1461),
                                                                                                  v802,
                                                                                                  96);
                                                                                DWORD2(v1461) = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800AC0E8)(
                                                                                                  DWORD2(v1461),
                                                                                                  v802,
                                                                                                  96);
                                                                                off_1800AC180((CIVIAudioFilter *)((char *)&v1460 + 12));
LABEL_1101:
                                                                                *(_QWORD *)&v1425 = 0;
                                                                                goto LABEL_1102;
                                                                              }
LABEL_1116:
                                                                              v556 = v1339;
                                                                            }
LABEL_1006:
                                                                            off_1800AC190[0](0, (int)v1403);
LABEL_1007:
                                                                            while ( _InterlockedCompareExchange(
                                                                                      &g_WarbirdSecureFunctionsLock,
                                                                                      1,
                                                                                      0) )
                                                                              ;
                                                                            v806 = g_WarbirdSecureFunctionsRefCount;
                                                                            if ( g_WarbirdSecureFunctionsRefCount > 0 )
                                                                            {
                                                                              --g_WarbirdSecureFunctionsRefCount;
                                                                              if ( v806 == 1 )
                                                                              {
                                                                                if ( WARBIRD::g_arModuleInfo )
                                                                                  FreeLibrary(WARBIRD::g_arModuleInfo);
                                                                                if ( *((_QWORD *)&xmmword_1800AD870 + 1) )
                                                                                  FreeLibrary(*((HMODULE *)&xmmword_1800AD870
                                                                                              + 1));
                                                                                if ( hLibModule )
                                                                                  FreeLibrary(hLibModule);
                                                                                if ( *((_QWORD *)&xmmword_1800AD8A0 + 1) )
                                                                                  FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0
                                                                                              + 1));
                                                                                qword_1800AC100 = 0;
                                                                                WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC078 = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                                                                off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC108 = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC138 = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                                                                xmmword_1800AD870 = 0;
                                                                                xmmword_1800AD880 = 0;
                                                                                *(_OWORD *)&hLibModule = 0;
                                                                                xmmword_1800AD8A0 = 0;
                                                                                xmmword_1800AD8B0 = 0;
                                                                                off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC180 = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC188 = CIVIAudioFilter::IsDirty;
                                                                                off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                              }
                                                                            }
                                                                            _InterlockedExchange(
                                                                              &g_WarbirdSecureFunctionsLock,
                                                                              0);
                                                                            SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(&v1410);
                                                                            if ( v556 < 0 )
                                                                              goto LABEL_1345;
                                                                            v807 = v1425;
                                                                            v1469 = 0;
                                                                            psz = 0;
                                                                            v1383 = DWORD1(v1425);
                                                                            v1462 = 0;
                                                                            v1463 = 0;
                                                                            v1464 = 0;
                                                                            v1465 = 0;
                                                                            v1466 = 0;
                                                                            v1467 = 0;
                                                                            v1468 = 0;
                                                                            v808 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800AC080[0])(
                                                                                     v1418,
                                                                                     7);
                                                                            if ( !v808
                                                                              || !((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800AC098[0])(
                                                                                    v808,
                                                                                    104,
                                                                                    &v1462) )
                                                                            {
                                                                              v809 = 0;
                                                                              v811 = v425 & 0xF;
                                                                              v810 = v811;
                                                                              goto LABEL_1118;
                                                                            }
                                                                            if ( HIWORD(v1463) != 32
                                                                              || !*(_QWORD *)((char *)&v1464 + 4)
                                                                              || (int)v1463 <= 0
                                                                              || (v809 = 1, SDWORD1(v1463) <= 0) )
                                                                            {
                                                                              v809 = 0;
                                                                            }
                                                                            v810 = v425 & 0xF;
                                                                            v811 = v810;
                                                                            if ( v809 )
                                                                            {
LABEL_1119:
                                                                              ((void (__fastcall *)(char *, _QWORD, _QWORD))off_1800AC180)(
                                                                                (char *)&v1458 + 12,
                                                                                v807,
                                                                                v1383);
                                                                              ((void (__fastcall *)(char *, _QWORD, _QWORD))off_1800AC180)(
                                                                                (char *)&v1459 + 12,
                                                                                v807,
                                                                                v1383);
                                                                              if ( v810 == 1 )
                                                                              {
                                                                                v850 = 11691808;
                                                                                if ( HIDWORD(v1455[0]) )
                                                                                  v850 = 0;
                                                                                psz = (STRSAFE_PCNZWCH)((__int64 (__fastcall *)(__int64))off_1800AC058[0])(v850);
                                                                              }
                                                                            }
                                                                            else
                                                                            {
LABEL_1118:
                                                                              if ( v810 == 1 )
                                                                                goto LABEL_1119;
                                                                            }
                                                                            v851 = v1418;
                                                                            LODWORD(Size) = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800AC0B0)(
                                                                                              v1418,
                                                                                              1);
                                                                            v852 = 2064;
                                                                            if ( LODWORD(v1455[0]) )
                                                                              v852 = 133138;
                                                                            LODWORD(v1422) = v852;
                                                                            if ( v809 )
                                                                            {
                                                                              v1501 = 0;
                                                                              v1533 = 0;
                                                                              v1494 = 0;
                                                                              v1526 = 0;
                                                                              v1412 = v1455[1];
                                                                              memset(v1552, 0, 28);
                                                                              v1495 = 0;
                                                                              v1496 = 0;
                                                                              v1497 = 0;
                                                                              v1498 = 0;
                                                                              v1499 = 0;
                                                                              v1500 = 0;
                                                                              v1527 = 0;
                                                                              v1528 = 0;
                                                                              v1529 = 0;
                                                                              v1530 = 0;
                                                                              v1531 = 0;
                                                                              v1532 = 0;
                                                                              v1551 = 0;
                                                                              v1534 = 0;
                                                                              if ( !v1455[1] )
                                                                                goto LABEL_1343;
                                                                              v853 = (unsigned __int16 *)v1457;
                                                                              v854 = v1418;
                                                                              v1399 = HIDWORD(v1455[0]);
                                                                              v1361 = (unsigned __int16 *)v1457;
                                                                              v855 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800AC080[0])(
                                                                                       v1418,
                                                                                       7);
                                                                              if ( v855 )
                                                                              {
                                                                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800AC098[0])(
                                                                                       v855,
                                                                                       104,
                                                                                       &v1494) )
                                                                                {
                                                                                  v1390 = v1495;
                                                                                  v1402 = *(_QWORD *)((char *)&v1496 + 4);
                                                                                  v853 = v1361;
                                                                                  v1398 = DWORD1(v1495);
                                                                                }
                                                                                else
                                                                                {
                                                                                  v1402 = 0;
                                                                                  v1398 = 0;
                                                                                  v1390 = 0;
                                                                                }
                                                                                v856 = ((__int64 (__fastcall *)(LPVOID))off_1800AC040[0])(v854);
                                                                                pcchLength = v856;
                                                                                v857 = (WARBIRD_DELAY_LOAD *)v856;
                                                                                if ( v856 )
                                                                                {
                                                                                  v858 = 0;
                                                                                  DWORD1(v1551) = DWORD1(v1459)
                                                                                                - HIDWORD(v1458);
                                                                                  DWORD2(v1551) = v1459 - DWORD2(v1459);
                                                                                  v1451 = 0;
                                                                                  memset(v1552, 0, 28);
                                                                                  LODWORD(v1551) = 40;
                                                                                  HIDWORD(v1551) = 2097153;
                                                                                  v859 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800AC048[0])(
                                                                                           v856,
                                                                                           &v1551,
                                                                                           0,
                                                                                           &v1451,
                                                                                           0,
                                                                                           0);
                                                                                  v1410 = v859;
                                                                                  if ( v859 )
                                                                                  {
                                                                                    if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_1800AC098[0])(
                                                                                           v859,
                                                                                           104,
                                                                                           &v1526) )
                                                                                    {
                                                                                      v1404 = *(_QWORD *)((char *)&v1528 + 4);
                                                                                      v857 = (WARBIRD_DELAY_LOAD *)pcchLength;
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v1404 = 0;
                                                                                    }
                                                                                    DWORD2(v1534) = DWORD1(v1459) - HIDWORD(v1458);
                                                                                    HIDWORD(v1534) = DWORD2(v1459) - v1459;
                                                                                    off_1800AC0A8(v857, v1410);
                                                                                    ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int64))off_1800AC0B0)(
                                                                                      v857,
                                                                                      1);
                                                                                    v861 = ((__int64 (__fastcall *)(WARBIRD_DELAY_LOAD *, unsigned __int16 *))off_1800AC0A8)(
                                                                                             v857,
                                                                                             v853);
                                                                                    v862 = off_1800AC118[0];
                                                                                    v1417 = v861;
                                                                                    v863 = ((__int64 (__fastcall *)(_QWORD))off_1800AC0A0[0])(0);
                                                                                    ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int128 *, __int64))v862)(
                                                                                      v857,
                                                                                      &v1534,
                                                                                      v863);
                                                                                    ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, void *, __int64, __int128 *, _DWORD, _QWORD))off_1800AC108)(
                                                                                      v857,
                                                                                      v1412,
                                                                                      0xFFFFFFFFLL,
                                                                                      &v1534,
                                                                                      (_DWORD)v1422,
                                                                                      0);
                                                                                    if ( v810 == 1 )
                                                                                    {
                                                                                      if ( v1399 )
                                                                                        v864 = ((__int64 (__fastcall *)(__int64))off_1800AC148[0])(8);
                                                                                      else
                                                                                        v864 = 0xFFFFFF;
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v864 = -5723992;
                                                                                    }
                                                                                    v865 = -HIDWORD(v1458);
                                                                                    if ( v1458 >= 0 )
                                                                                      v865 = 0;
                                                                                    v866 = 0;
                                                                                    if ( v1458 >= 0 )
                                                                                      v866 = HIDWORD(v1458);
                                                                                    v867 = -(int)v1459;
                                                                                    if ( (int)v1459 >= 0 )
                                                                                      v867 = 0;
                                                                                    v868 = 0;
                                                                                    if ( (int)v1459 >= 0 )
                                                                                      v868 = v1459;
                                                                                    v869 = v1390;
                                                                                    v870 = DWORD2(v1534) - v865;
                                                                                    if ( DWORD2(v1534) - v865 >= v1390 - v866 )
                                                                                      v870 = v1390 - v866;
                                                                                    v871 = HIDWORD(v1534) - v867;
                                                                                    if ( HIDWORD(v1534) - v867 >= (int)(v1398 - v868) )
                                                                                      v871 = v1398 - v868;
                                                                                    v1407 = v871;
                                                                                    if ( v870 <= 0 || v871 <= 0 )
                                                                                    {
                                                                                      v878 = v1329;
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v1391 = 0;
                                                                                      v872 = v1404
                                                                                           + 4
                                                                                           * (v865
                                                                                            + (__int64)(v867 * DWORD2(v1534)));
                                                                                      v1404 = v872;
                                                                                      v873 = (char *)(v1402 + 4 * (v866 + (__int64)(v868 * (int)v869)));
                                                                                      v1399 = v864 >> 8;
                                                                                      LODWORD(v1416) = HIWORD(v864);
                                                                                      v1362 = (unsigned __int16 *)(4LL * SDWORD2(v1534));
                                                                                      v1412 = (void *)(4 * v869);
                                                                                      v1402 = (SIZE_T)v873;
                                                                                      do
                                                                                      {
                                                                                        v874 = (unsigned __int8 *)v872;
                                                                                        v875 = v873;
                                                                                        for ( i2 = 0; i2 < v870; ++i2 )
                                                                                        {
                                                                                          if ( (unsigned __int8)((*v874 + v874[2] + 2 * (unsigned int)v874[1]) >> 2) != 0xFF )
                                                                                          {
                                                                                            v877 = (unsigned __int8)~((*v874 + v874[2] + 2 * (unsigned int)v874[1]) >> 2);
                                                                                            v875[2] -= ~((*v874 + v874[2] + 2 * (unsigned int)v874[1]) >> 2) * (v864 - v875[2]);
                                                                                            v875[1] -= v877 * (BYTE1(v864) - v875[1]);
                                                                                            *v875 -= v877 * (BYTE2(v864) - *v875);
                                                                                            v875[3] += v877 * (255 - (unsigned __int8)v875[3]) / 255;
                                                                                          }
                                                                                          v874 += 4;
                                                                                          v875 += 4;
                                                                                        }
                                                                                        v872 = (SIZE_T)v1362 + v1404;
                                                                                        v873 = (char *)v1412 + v1402;
                                                                                        v1404 += (SIZE_T)v1362;
                                                                                        v1402 += (SIZE_T)v1412;
                                                                                        ++v1391;
                                                                                      }
                                                                                      while ( v1391 < v1407 );
                                                                                      v878 = v1329;
                                                                                    }
                                                                                    ((void (__fastcall *)(SIZE_T))off_1800AC068)(v1410);
                                                                                    v857 = (WARBIRD_DELAY_LOAD *)pcchLength;
                                                                                    if ( v1417 )
                                                                                      off_1800AC0A8(
                                                                                        (WARBIRD_DELAY_LOAD *)pcchLength,
                                                                                        v1417);
                                                                                    else
                                                                                      v1329 = v878;
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    v860 = GetLastError();
                                                                                    v858 = v860;
                                                                                    if ( v860 > 0 )
                                                                                      v858 = (unsigned __int16)v860
                                                                                           | 0x80070000;
                                                                                    if ( v858 >= 0 )
                                                                                      v858 = -2147467259;
                                                                                  }
                                                                                  ((void (__fastcall *)(WARBIRD_DELAY_LOAD *))off_1800AC060[0])(v857);
                                                                                  if ( v858 >= 0 )
                                                                                  {
                                                                                    v1486 = 0;
                                                                                    v1493 = 0;
                                                                                    v1502 = 0;
                                                                                    v1509 = 0;
                                                                                    v1412 = v1456[0];
                                                                                    memset(v1546, 0, 28);
                                                                                    v1487 = 0;
                                                                                    v1488 = 0;
                                                                                    v1489 = 0;
                                                                                    v1490 = 0;
                                                                                    v1491 = 0;
                                                                                    v1492 = 0;
                                                                                    v1503 = 0;
                                                                                    v1504 = 0;
                                                                                    v1505 = 0;
                                                                                    v1506 = 0;
                                                                                    v1507 = 0;
                                                                                    v1508 = 0;
                                                                                    v1545 = 0;
                                                                                    v1535 = 0;
                                                                                    if ( v1456[0] )
                                                                                    {
                                                                                      v879 = v1418;
                                                                                      v1399 = HIDWORD(v1455[0]);
                                                                                      v1363 = (unsigned __int16 *)*((_QWORD *)&v1457 + 1);
                                                                                      v880 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800AC080[0])(
                                                                                               v1418,
                                                                                               7);
                                                                                      if ( !v880 )
                                                                                        goto LABEL_1225;
                                                                                      if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800AC098[0])(
                                                                                             v880,
                                                                                             104,
                                                                                             &v1486) )
                                                                                      {
                                                                                        v881 = v1487;
                                                                                        v882 = DWORD1(v1487);
                                                                                        v1402 = *(_QWORD *)((char *)&v1488 + 4);
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v882 = 0;
                                                                                        v1402 = 0;
                                                                                        v881 = 0;
                                                                                      }
                                                                                      v1392 = v881;
                                                                                      lpMem = (LPVOID)((__int64 (__fastcall *)(LPVOID))off_1800AC040[0])(v879);
                                                                                      v883 = (WARBIRD_DELAY_LOAD *)lpMem;
                                                                                      if ( !lpMem )
                                                                                        goto LABEL_1225;
                                                                                      DWORD1(v1545) = DWORD1(v1460) - HIDWORD(v1459);
                                                                                      DWORD2(v1545) = v1460 - DWORD2(v1460);
                                                                                      v1452 = 0;
                                                                                      memset(v1546, 0, 28);
                                                                                      LODWORD(v1545) = 40;
                                                                                      HIDWORD(v1545) = 2097153;
                                                                                      v884 = ((__int64 (__fastcall *)(LPVOID, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800AC048[0])(
                                                                                               lpMem,
                                                                                               &v1545,
                                                                                               0,
                                                                                               &v1452,
                                                                                               0,
                                                                                               0);
                                                                                      v1410 = v884;
                                                                                      if ( v884 )
                                                                                      {
                                                                                        if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_1800AC098[0])(
                                                                                               v884,
                                                                                               104,
                                                                                               &v1502) )
                                                                                        {
                                                                                          v1404 = *(_QWORD *)((char *)&v1504 + 4);
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v1404 = 0;
                                                                                        }
                                                                                        v886 = 0;
                                                                                        DWORD2(v1535) = DWORD1(v1460) - HIDWORD(v1459);
                                                                                        HIDWORD(v1535) = DWORD2(v1460) - v1460;
                                                                                        off_1800AC0A8(v883, v1410);
                                                                                        ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int64))off_1800AC0B0)(
                                                                                          v883,
                                                                                          1);
                                                                                        v887 = ((__int64 (__fastcall *)(WARBIRD_DELAY_LOAD *, unsigned __int16 *))off_1800AC0A8)(
                                                                                                 v883,
                                                                                                 v1363);
                                                                                        v888 = off_1800AC118[0];
                                                                                        pcchLength = v887;
                                                                                        v889 = ((__int64 (__fastcall *)(_QWORD))off_1800AC0A0[0])(0);
                                                                                        ((void (__fastcall *)(LPVOID, __int128 *, __int64))v888)(
                                                                                          lpMem,
                                                                                          &v1535,
                                                                                          v889);
                                                                                        ((void (__fastcall *)(LPVOID, void *, __int64, __int128 *, _DWORD, _QWORD))off_1800AC108)(
                                                                                          lpMem,
                                                                                          v1412,
                                                                                          0xFFFFFFFFLL,
                                                                                          &v1535,
                                                                                          (_DWORD)v1422,
                                                                                          0);
                                                                                        if ( v811 == 1 )
                                                                                        {
                                                                                          if ( v1399 )
                                                                                          {
                                                                                            v890 = ((__int64 (__fastcall *)(__int64))off_1800AC148[0])(8);
                                                                                            v1400 = v890;
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            v890 = 0xFFFFFF;
                                                                                          }
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v890 = -5723992;
                                                                                          v1400 = -5723992;
                                                                                        }
                                                                                        v891 = -HIDWORD(v1459);
                                                                                        if ( v1459 >= 0 )
                                                                                          v891 = 0;
                                                                                        v892 = 0;
                                                                                        if ( v1459 >= 0 )
                                                                                          v892 = HIDWORD(v1459);
                                                                                        v893 = -(int)v1460;
                                                                                        if ( (int)v1460 >= 0 )
                                                                                          v893 = 0;
                                                                                        v894 = 0;
                                                                                        if ( (int)v1460 >= 0 )
                                                                                          v894 = v1460;
                                                                                        v895 = v881 - v892;
                                                                                        v896 = DWORD2(v1535) - v891;
                                                                                        if ( DWORD2(v1535) - v891 >= v895 )
                                                                                          v896 = v895;
                                                                                        v897 = v882 - v894;
                                                                                        v898 = HIDWORD(v1535) - v893;
                                                                                        if ( HIDWORD(v1535) - v893 >= v897 )
                                                                                          v898 = v897;
                                                                                        v1399 = v898;
                                                                                        if ( v896 <= 0 || v898 <= 0 )
                                                                                        {
                                                                                          v909 = v1329;
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v899 = v1392;
                                                                                          v900 = v890 >> 8;
                                                                                          v901 = HIWORD(v1400);
                                                                                          v1393 = 0;
                                                                                          v902 = v1404
                                                                                               + 4
                                                                                               * (v891
                                                                                                + (__int64)(v893 * DWORD2(v1535)));
                                                                                          v1404 = v902;
                                                                                          v903 = (char *)(v1402 + 4 * (v892 + (__int64)(v894 * (int)v899)));
                                                                                          v1364 = (unsigned __int16 *)(4LL * SDWORD2(v1535));
                                                                                          v1412 = (void *)(4 * v899);
                                                                                          v1402 = (SIZE_T)v903;
                                                                                          do
                                                                                          {
                                                                                            v904 = (unsigned __int8 *)v902;
                                                                                            v905 = v1400;
                                                                                            v906 = v903;
                                                                                            for ( i3 = 0; i3 < v896; ++i3 )
                                                                                            {
                                                                                              if ( (unsigned __int8)((*v904 + v904[2] + 2 * (unsigned int)v904[1]) >> 2) != 0xFF )
                                                                                              {
                                                                                                v908 = (unsigned __int8)~((*v904 + v904[2] + 2 * (unsigned int)v904[1]) >> 2);
                                                                                                v906[2] -= ~((*v904 + v904[2] + 2 * (unsigned int)v904[1]) >> 2) * (v905 - v906[2]);
                                                                                                v906[1] -= v908 * (v900 - v906[1]);
                                                                                                *v906 -= v908 * (v901 - *v906);
                                                                                                v906[3] += v908 * (255 - (unsigned __int8)v906[3]) / 255;
                                                                                              }
                                                                                              v904 += 4;
                                                                                              v906 += 4;
                                                                                            }
                                                                                            v902 = (SIZE_T)v1364 + v1404;
                                                                                            v903 = (char *)v1412 + v1402;
                                                                                            v1404 += (SIZE_T)v1364;
                                                                                            v1402 += (SIZE_T)v1412;
                                                                                            ++v1393;
                                                                                          }
                                                                                          while ( v1393 < (int)v1399 );
                                                                                          v909 = v1329;
                                                                                        }
                                                                                        ((void (__fastcall *)(SIZE_T))off_1800AC068)(v1410);
                                                                                        if ( pcchLength )
                                                                                        {
                                                                                          v883 = (WARBIRD_DELAY_LOAD *)lpMem;
                                                                                          off_1800AC0A8(
                                                                                            (WARBIRD_DELAY_LOAD *)lpMem,
                                                                                            pcchLength);
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v1329 = v909;
                                                                                          v883 = (WARBIRD_DELAY_LOAD *)lpMem;
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v885 = GetLastError();
                                                                                        v886 = v885;
                                                                                        if ( v885 > 0 )
                                                                                          v886 = (unsigned __int16)v885
                                                                                               | 0x80070000;
                                                                                        if ( v886 >= 0 )
                                                                                          v886 = -2147467259;
                                                                                      }
                                                                                      ((void (__fastcall *)(WARBIRD_DELAY_LOAD *))off_1800AC060[0])(v883);
                                                                                      if ( v886 >= 0 )
                                                                                      {
                                                                                        v910 = v1418;
                                                                                        v911 = 0;
                                                                                        v912 = 0;
                                                                                        goto LABEL_1335;
                                                                                      }
                                                                                    }
                                                                                  }
LABEL_1343:
                                                                                  if ( psz )
                                                                                    ((void (__fastcall *)(STRSAFE_PCNZWCH))off_1800AC068)(psz);
LABEL_1345:
                                                                                  v974 = v1455[1];
                                                                                  if ( v1455[1] )
                                                                                  {
                                                                                    v975 = -1;
                                                                                    do
                                                                                      v55 = *((_WORD *)v1455[1] + ++v975) == 0;
                                                                                    while ( !v55 );
                                                                                    for ( i4 = 2 * v975 + 2; i4; --i4 )
                                                                                      *v974++ = 0;
                                                                                    v977 = v1455[1];
                                                                                    v978 = GetProcessHeap();
                                                                                    HeapFree(v978, 0, v977);
                                                                                    v1455[1] = 0;
                                                                                  }
                                                                                  v979 = v1456[0];
                                                                                  if ( v1456[0] )
                                                                                  {
                                                                                    v980 = -1;
                                                                                    do
                                                                                      v55 = *((_WORD *)v1456[0] + ++v980) == 0;
                                                                                    while ( !v55 );
                                                                                    for ( i5 = 2 * v980 + 2; i5; --i5 )
                                                                                      *v979++ = 0;
                                                                                    v982 = v1456[0];
                                                                                    v983 = GetProcessHeap();
                                                                                    HeapFree(v983, 0, v982);
                                                                                    v1456[0] = 0;
                                                                                  }
                                                                                  v984 = v1456[1];
                                                                                  if ( v1456[1] )
                                                                                  {
                                                                                    v985 = -1;
                                                                                    do
                                                                                      v55 = *((_WORD *)v1456[1] + ++v985) == 0;
                                                                                    while ( !v55 );
                                                                                    v986 = 2 * v985 + 2;
                                                                                    if ( v986 )
                                                                                    {
                                                                                      do
                                                                                      {
                                                                                        *v984++ = 0;
                                                                                        --v986;
                                                                                      }
                                                                                      while ( v986 );
                                                                                      v984 = v1456[1];
                                                                                    }
                                                                                    v987 = GetProcessHeap();
                                                                                    HeapFree(v987, 0, v984);
                                                                                    v1456[1] = 0;
                                                                                  }
                                                                                  if ( (_QWORD)v1457 )
                                                                                  {
                                                                                    ((void (*)(void))off_1800AC068)();
                                                                                    *(_QWORD *)&v1457 = 0;
                                                                                  }
                                                                                  if ( *((_QWORD *)&v1457 + 1) )
                                                                                  {
                                                                                    ((void (*)(void))off_1800AC068)();
                                                                                    *((_QWORD *)&v1457 + 1) = 0;
                                                                                  }
                                                                                  if ( (_QWORD)v1458 )
                                                                                  {
                                                                                    ((void (*)(void))off_1800AC068)();
                                                                                    *(_QWORD *)&v1458 = 0;
                                                                                  }
                                                                                  while ( _InterlockedCompareExchange(
                                                                                            &g_WarbirdSecureFunctionsLock,
                                                                                            1,
                                                                                            0) )
                                                                                    ;
                                                                                  v988 = g_WarbirdSecureFunctionsRefCount;
                                                                                  if ( g_WarbirdSecureFunctionsRefCount > 0 )
                                                                                  {
                                                                                    --g_WarbirdSecureFunctionsRefCount;
                                                                                    if ( v988 == 1 )
                                                                                    {
                                                                                      if ( WARBIRD::g_arModuleInfo )
                                                                                        FreeLibrary(WARBIRD::g_arModuleInfo);
                                                                                      if ( *((_QWORD *)&xmmword_1800AD870
                                                                                           + 1) )
                                                                                        FreeLibrary(*((HMODULE *)&xmmword_1800AD870 + 1));
                                                                                      if ( hLibModule )
                                                                                        FreeLibrary(hLibModule);
                                                                                      if ( *((_QWORD *)&xmmword_1800AD8A0
                                                                                           + 1) )
                                                                                        FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0 + 1));
                                                                                      qword_1800AC100 = 0;
                                                                                      WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC078 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                                                                      off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC108 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC138 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                                                                      xmmword_1800AD870 = 0;
                                                                                      xmmword_1800AD880 = 0;
                                                                                      *(_OWORD *)&hLibModule = 0;
                                                                                      xmmword_1800AD8A0 = 0;
                                                                                      xmmword_1800AD8B0 = 0;
                                                                                      off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC180 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC188 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    }
                                                                                  }
                                                                                  _InterlockedExchange(
                                                                                    &g_WarbirdSecureFunctionsLock,
                                                                                    0);
                                                                                  v989 = g_WarbirdPaintInitTime;
                                                                                  LODWORD(Src) = g_WarbirdNotificationInformation;
                                                                                  v990 = ((__int64 (*)(void))off_1800AC0C8[0])();
                                                                                  v1577 = 0;
                                                                                  v1404 = (unsigned int)(v990 - v989);
                                                                                  v1581 = 0;
                                                                                  v1578 = 0;
                                                                                  v1579 = 0;
                                                                                  v1580 = 0;
                                                                                  while ( _InterlockedCompareExchange(
                                                                                            &g_WarbirdSecureFunctionsLock,
                                                                                            1,
                                                                                            0) )
                                                                                    ;
                                                                                  if ( g_WarbirdSecureFunctionsRefCount )
                                                                                  {
LABEL_1432:
                                                                                    ++g_WarbirdSecureFunctionsRefCount;
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    v991 = MemoryAllocT<unsigned long>(824);
                                                                                    pcchLength = v991;
                                                                                    v992 = (WCHAR *)v991;
                                                                                    if ( v991 )
                                                                                    {
                                                                                      v993 = 0;
                                                                                      v994 = qword_18009D240;
                                                                                      v995 = 0;
                                                                                      v996 = v991;
                                                                                      v997 = 0;
                                                                                      v998 = -1;
                                                                                      v999 = 103;
                                                                                      do
                                                                                      {
                                                                                        v1000 = *(unsigned __int8 *)v994 << 8;
                                                                                        v1001 = *((unsigned __int8 *)v994
                                                                                                + 1);
                                                                                        v1002 = *((unsigned __int8 *)v994++
                                                                                                + 4);
                                                                                        v1003 = *((unsigned __int8 *)v994
                                                                                                - 5)
                                                                                              | ((*((unsigned __int8 *)v994
                                                                                                  - 6)
                                                                                                | ((v1000 | v1001) << 8)) << 8);
                                                                                        v1004 = *((unsigned __int8 *)v994
                                                                                                - 1)
                                                                                              | ((*((unsigned __int8 *)v994
                                                                                                  - 2)
                                                                                                | ((*((unsigned __int8 *)v994 - 3)
                                                                                                  | (v1002 << 8)) << 8)) << 8);
                                                                                        v1005 = v995
                                                                                              ^ v1004
                                                                                              ^ v997
                                                                                              ^ v1003
                                                                                              ^ 0xAC987321;
                                                                                        v1006 = v997
                                                                                              ^ v1003
                                                                                              ^ (__ROR4__(v1005, 22)
                                                                                               + 4991
                                                                                               * __ROR4__(
                                                                                                   v1005 + 1419157410,
                                                                                                   27));
                                                                                        v1007 = v1005
                                                                                              ^ (43881
                                                                                               * __ROR4__(
                                                                                                   v1006 + 133239679,
                                                                                                   9)
                                                                                               - __ROR4__(v1006, 30));
                                                                                        v1008 = v1006
                                                                                              ^ (24670 * v1007
                                                                                               - (v1007 >> 13)
                                                                                               - 123127970);
                                                                                        v1009 = v1007
                                                                                              ^ (2033
                                                                                               * __ROR4__(
                                                                                                   v1008 ^ 0xAB69,
                                                                                                   26)
                                                                                               - __ROR4__(v1008, 30));
                                                                                        v1010 = v1008
                                                                                              ^ (133239679
                                                                                               - (v1009 ^ 0xAB69605E));
                                                                                        v1011 = v1009
                                                                                              ^ (43881 * (v1010 ^ 0x137F))
                                                                                              ^ __ROR4__(v1010, 6);
                                                                                        v1012 = v1010
                                                                                              ^ (__ROR4__(v1011, 30)
                                                                                               + 24670
                                                                                               * __ROR4__(
                                                                                                   v1011 + 133239679,
                                                                                                   15));
                                                                                        v1013 = v1011
                                                                                              ^ (2033
                                                                                               * __ROR4__(
                                                                                                   v1012 + 1419157410,
                                                                                                   14)
                                                                                               - __ROR4__(v1012, 24));
                                                                                        v1014 = v1012
                                                                                              ^ __ROR4__(v1013, 10)
                                                                                              ^ (4991
                                                                                               * __ROR4__(
                                                                                                   v1013 ^ 0xAB69605E,
                                                                                                   12));
                                                                                        v1015 = v1013
                                                                                              ^ (v1014 >> 10)
                                                                                              ^ (43881 * (v1014 ^ 0x7F1));
                                                                                        v1016 = v1014
                                                                                              ^ (2033
                                                                                               * (__ROR4__(~v1015, 5)
                                                                                                + 24670));
                                                                                        v1017 = v1016
                                                                                              ^ (((v1015
                                                                                                 ^ (v1016 - 2033)
                                                                                                 ^ 0xAB69605E) >> 2)
                                                                                               + 4991
                                                                                               * __ROR4__(
                                                                                                   v1015
                                                                                                 ^ (v1016 - 2033)
                                                                                                 ^ 0xAB6967AF,
                                                                                                   30));
                                                                                        v1018 = v1015
                                                                                              ^ (v1016 - 2033)
                                                                                              ^ 0xAB69605E
                                                                                              ^ (__ROR4__(v1017, 25)
                                                                                               + 43881
                                                                                               * __ROR4__(
                                                                                                   v1017 - 133239679,
                                                                                                   6));
                                                                                        v1019 = v1017
                                                                                              ^ (24670
                                                                                               * (v1018 ^ 0x137F)
                                                                                               + __ROR4__(v1018, 9));
                                                                                        v1020 = v1018
                                                                                              ^ (__ROR4__(v1019, 25)
                                                                                               + 2033
                                                                                               * __ROR4__(
                                                                                                   v1019 ^ 0xAB69,
                                                                                                   27));
                                                                                        v1021 = v1020
                                                                                              ^ v1019
                                                                                              ^ 0xAC987321;
                                                                                        v1022 = v1020
                                                                                              ^ (4991
                                                                                               * __ROR4__(v1021, 3)
                                                                                               - 219010071);
                                                                                        v1023 = v1021
                                                                                              ^ (24670
                                                                                               * __ROR4__(
                                                                                                   v1022 - 133239679,
                                                                                                   1)
                                                                                               - __ROR4__(v1022, 6));
                                                                                        v1024 = v1022
                                                                                              ^ (__ROR4__(v1023, 18)
                                                                                               + 2033
                                                                                               * __ROR4__(
                                                                                                   v1023 - 1419157410,
                                                                                                   29));
                                                                                        v1025 = v1023
                                                                                              ^ (4991
                                                                                               * __ROR4__(
                                                                                                   v1024 - 1419157410,
                                                                                                   17)
                                                                                               - __ROR4__(v1024, 14));
                                                                                        v996 += 8LL;
                                                                                        v1026 = v998;
                                                                                        v998 = v1004;
                                                                                        v1027 = v1024
                                                                                              ^ (v1025 >> 3)
                                                                                              ^ (43881 * (v1025 ^ 0x605E));
                                                                                        v995 = v1027 ^ v1026;
                                                                                        v1028 = v993
                                                                                              ^ __ROR4__(v1027, 30)
                                                                                              ^ (24670
                                                                                               * __ROR4__(
                                                                                                   v1027 ^ 0x7F1137F,
                                                                                                   28));
                                                                                        v993 = v1003;
                                                                                        v997 = v1025 ^ v1028;
                                                                                        *(_BYTE *)(v996 - 5) = v997;
                                                                                        *(_BYTE *)(v996 - 1) = v995;
                                                                                        *(_BYTE *)(v996 - 6) = __ROR4__(v997, 8);
                                                                                        *(_BYTE *)(v996 - 2) = __ROR4__(v995, 8);
                                                                                        *(_BYTE *)(v996 - 7) = __ROR4__(v997, 16);
                                                                                        *(_BYTE *)(v996 - 3) = __ROR4__(v995, 16);
                                                                                        *(_BYTE *)(v996 - 8) = __ROR4__(v997, 24);
                                                                                        *(_BYTE *)(v996 - 4) = __ROR4__(v995, 24);
                                                                                        --v999;
                                                                                      }
                                                                                      while ( v999 );
                                                                                      v1029 = 0;
                                                                                      v1030 = 0;
                                                                                      v1031 = 0;
                                                                                      do
                                                                                      {
                                                                                        v1030 = _mm_xor_ps(
                                                                                                  v1030,
                                                                                                  (__m128)_mm_loadu_si128((const __m128i *)((char *)v992 + v1029)));
                                                                                        v1032 = (__m128)_mm_loadu_si128((const __m128i *)((char *)v992 + v1029 + 16));
                                                                                        v1029 += 32LL;
                                                                                        v1031 = _mm_xor_ps(v1031, v1032);
                                                                                      }
                                                                                      while ( v1029 < 0x320 );
                                                                                      v1033 = _mm_xor_ps(v1031, v1030);
                                                                                      v1034 = _mm_xor_ps(
                                                                                                v1033,
                                                                                                (__m128)_mm_srli_si128((__m128i)v1033, 8));
                                                                                      v1035 = _mm_xor_ps(
                                                                                                v1034,
                                                                                                (__m128)_mm_srli_si128((__m128i)v1034, 4));
                                                                                      v1036 = _mm_xor_ps(
                                                                                                v1035,
                                                                                                (__m128)_mm_srli_si128((__m128i)v1035, 2));
                                                                                      for ( i6 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v1036, (__m128)_mm_srli_si128((__m128i)v1036, 1)));
                                                                                            v1029 < 0x338;
                                                                                            ++v1029 )
                                                                                      {
                                                                                        i6 ^= *((_BYTE *)v992 + v1029);
                                                                                      }
                                                                                      if ( i6 == 64 )
                                                                                      {
                                                                                        v1038 = 0;
                                                                                        *((_BYTE *)v992 + 823) = 0;
                                                                                        v1039 = 0;
                                                                                        v1040 = 0;
                                                                                        v1395 = 0;
                                                                                        *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                                                                        v1041 = v992;
                                                                                        xmmword_1800AD870 = 0;
                                                                                        xmmword_1800AD880 = 0;
                                                                                        *(_OWORD *)&hLibModule = 0;
                                                                                        xmmword_1800AD8A0 = 0;
                                                                                        xmmword_1800AD8B0 = 0;
                                                                                        if ( *(_BYTE *)v992 )
                                                                                        {
                                                                                          while ( 1 )
                                                                                          {
                                                                                            v1042 = -1;
                                                                                            do
                                                                                              v55 = v1041[++v1042] == 0;
                                                                                            while ( !v55 );
                                                                                            v1369 = (unsigned __int16 *)(24 * v1038);
                                                                                            v1043 = &WARBIRD::g_arModuleInfo + 3 * v1038;
                                                                                            if ( !GetModuleHandleExW(
                                                                                                    0,
                                                                                                    v1041,
                                                                                                    v1043) )
                                                                                              break;
                                                                                            v1044 = &v1041[v1042];
                                                                                            if ( *(_WORD *)*v1043 == 23117 )
                                                                                            {
                                                                                              v1045 = *((int *)*v1043 + 15);
                                                                                              if ( (unsigned int)v1045 < 0x10000000 )
                                                                                              {
                                                                                                v1046 = (char *)*v1043 + v1045;
                                                                                                if ( v1046 >= (char *)*v1043 )
                                                                                                {
                                                                                                  if ( *(_DWORD *)v1046 == 17744 )
                                                                                                  {
                                                                                                    if ( ((*((_WORD *)v1046 + 12) - 267) & 0xFEFF) != 0 )
                                                                                                    {
                                                                                                      v1040 = -1073741811;
                                                                                                    }
                                                                                                    else
                                                                                                    {
                                                                                                      v1040 = 0;
                                                                                                      *(HMODULE *)((char *)&WARBIRD::g_arModuleInfo + (_QWORD)v1369 + 12) = (HMODULE)*((_QWORD *)v1046 + 17);
                                                                                                      *(_DWORD *)((char *)&WARBIRD::g_arModuleInfo + (_QWORD)v1369 + 8) = *((_DWORD *)v1046 + 20);
                                                                                                    }
                                                                                                  }
                                                                                                  else
                                                                                                  {
                                                                                                    v1040 = -1073741701;
                                                                                                  }
                                                                                                }
                                                                                                else
                                                                                                {
                                                                                                  v1040 = -1073741701;
                                                                                                }
                                                                                              }
                                                                                              else
                                                                                              {
                                                                                                v1040 = -1073741701;
                                                                                              }
                                                                                            }
                                                                                            else
                                                                                            {
                                                                                              v1040 = -1073741701;
                                                                                            }
                                                                                            v1047 = *(_DWORD *)(v1044 + 1);
                                                                                            v1048 = 0;
                                                                                            v1041 = v1044 + 3;
                                                                                            for ( LODWORD(Size) = v1047;
                                                                                                  v1048 < v1047;
                                                                                                  ++v1048 )
                                                                                            {
                                                                                              v1049 = -1;
                                                                                              do
                                                                                                ++v1049;
                                                                                              while ( *((_BYTE *)v1041 + v1049) );
                                                                                              if ( v1040 >= 0 )
                                                                                              {
                                                                                                v1050 = (void **)GetProcAddress(*(&WARBIRD::g_arModuleInfo + 3 * v1395), (LPCSTR)v1041);
                                                                                                if ( !v1050 )
                                                                                                {
                                                                                                  v1052 = GetProcessHeap();
                                                                                                  HeapFree(
                                                                                                    v1052,
                                                                                                    0,
                                                                                                    (LPVOID)pcchLength);
                                                                                                  goto LABEL_1432;
                                                                                                }
                                                                                                (&WARBIRD::g_FuncAddress)[v1039] = v1050;
                                                                                                v1047 = Size;
                                                                                              }
                                                                                              v1039 = (unsigned int)(v1039 + 1);
                                                                                              v1041 = (const WCHAR *)((char *)v1041 + v1049 + 1);
                                                                                            }
                                                                                            v1038 = ++v1395;
                                                                                            if ( !*(_BYTE *)v1041 )
                                                                                            {
                                                                                              v992 = (WCHAR *)pcchLength;
                                                                                              goto LABEL_1418;
                                                                                            }
                                                                                          }
                                                                                          v1053 = GetProcessHeap();
                                                                                          HeapFree(
                                                                                            v1053,
                                                                                            0,
                                                                                            (LPVOID)pcchLength);
                                                                                        }
                                                                                        else
                                                                                        {
LABEL_1418:
                                                                                          v1051 = GetProcessHeap();
                                                                                          HeapFree(v1051, 0, v992);
                                                                                          if ( v1040 >= 0 )
                                                                                            goto LABEL_1432;
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v1054 = GetProcessHeap();
                                                                                        HeapFree(v1054, 0, v992);
                                                                                      }
                                                                                    }
                                                                                    if ( WARBIRD::g_arModuleInfo )
                                                                                      FreeLibrary(WARBIRD::g_arModuleInfo);
                                                                                    if ( *((_QWORD *)&xmmword_1800AD870
                                                                                         + 1) )
                                                                                      FreeLibrary(*((HMODULE *)&xmmword_1800AD870
                                                                                                  + 1));
                                                                                    if ( hLibModule )
                                                                                      FreeLibrary(hLibModule);
                                                                                    if ( *((_QWORD *)&xmmword_1800AD8A0
                                                                                         + 1) )
                                                                                      FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0
                                                                                                  + 1));
                                                                                    qword_1800AC100 = 0;
                                                                                    WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC078 = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                                                                    off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC108 = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC138 = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                                                                    xmmword_1800AD870 = 0;
                                                                                    xmmword_1800AD880 = 0;
                                                                                    *(_OWORD *)&hLibModule = 0;
                                                                                    xmmword_1800AD8A0 = 0;
                                                                                    xmmword_1800AD8B0 = 0;
                                                                                    off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC180 = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC188 = CIVIAudioFilter::IsDirty;
                                                                                    off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                  }
                                                                                  _InterlockedExchange(
                                                                                    &g_WarbirdSecureFunctionsLock,
                                                                                    0);
                                                                                  LODWORD(v1581) = (_DWORD)Src;
                                                                                  LODWORD(v1578) = v1404;
                                                                                  v1577 = 1;
                                                                                  LODWORD(v1579) = -1721306479;
                                                                                  DWORD2(v1578) = 1;
                                                                                  LODWORD(v1580) = 1;
                                                                                  DWORD2(v1579) = 1;
                                                                                  DWORD2(v1580) = 1;
                                                                                  ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_1800AC100)(
                                                                                    0,
                                                                                    8225,
                                                                                    4,
                                                                                    &v1577);
                                                                                  while ( _InterlockedCompareExchange(
                                                                                            &g_WarbirdSecureFunctionsLock,
                                                                                            1,
                                                                                            0) )
                                                                                    ;
                                                                                  v1055 = g_WarbirdSecureFunctionsRefCount;
                                                                                  if ( g_WarbirdSecureFunctionsRefCount > 0 )
                                                                                  {
                                                                                    --g_WarbirdSecureFunctionsRefCount;
                                                                                    if ( v1055 == 1 )
                                                                                    {
                                                                                      if ( WARBIRD::g_arModuleInfo )
                                                                                        FreeLibrary(WARBIRD::g_arModuleInfo);
                                                                                      if ( *((_QWORD *)&xmmword_1800AD870
                                                                                           + 1) )
                                                                                        FreeLibrary(*((HMODULE *)&xmmword_1800AD870 + 1));
                                                                                      if ( hLibModule )
                                                                                        FreeLibrary(hLibModule);
                                                                                      if ( *((_QWORD *)&xmmword_1800AD8A0
                                                                                           + 1) )
                                                                                        FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0 + 1));
                                                                                      qword_1800AC100 = 0;
                                                                                      WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC078 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                                                                      off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC108 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC138 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                                                                      xmmword_1800AD870 = 0;
                                                                                      xmmword_1800AD880 = 0;
                                                                                      *(_OWORD *)&hLibModule = 0;
                                                                                      xmmword_1800AD8A0 = 0;
                                                                                      xmmword_1800AD8B0 = 0;
                                                                                      off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC180 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC188 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    }
                                                                                  }
                                                                                  _InterlockedExchange(
                                                                                    &g_WarbirdSecureFunctionsLock,
                                                                                    0);
                                                                                  off_1800AC190[0](0, (int)v1418);
LABEL_1447:
                                                                                  SH_HANDLE::~SH_HANDLE((SH_HANDLE *)&v1431[1]);
                                                                                  lpMem = 0;
                                                                                  v1056 = GetProcessHeap();
                                                                                  v1057 = HeapAlloc(v1056, 8u, 0xA0u);
                                                                                  v1418 = v1057;
                                                                                  v1058 = v1057;
                                                                                  if ( v1057 )
                                                                                  {
                                                                                    *v1057 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
                                                                                    v1057[1] = xmmword_1800AD470;
                                                                                    v1057[2] = xmmword_1800AD480;
                                                                                    v1057[3] = xmmword_1800AD490;
                                                                                    v1057[4] = xmmword_1800AD4A0;
                                                                                    v1057[5] = xmmword_1800AD4B0;
                                                                                    v1057[6] = xmmword_1800AD4C0;
                                                                                    v1057[7] = xmmword_1800AD4D0;
                                                                                    v1057[8] = xmmword_1800AD4E0;
                                                                                    v1057[9] = xmmword_1800AD4F0;
                                                                                    v1059 = GetProcessHeap();
                                                                                    v1060 = HeapAlloc(v1059, 8u, 8u);
                                                                                    v1413 = v1060;
                                                                                    v1061 = v1060;
                                                                                    if ( !v1060 )
                                                                                    {
                                                                                      v1061 = 0;
                                                                                      goto LABEL_1737;
                                                                                    }
                                                                                    *v1060 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
                                                                                    v1062 = __rdtsc();
                                                                                    v1063 = v1329;
                                                                                    v1064 = GetProcessHeap();
                                                                                    v1065 = (unsigned int *)HeapAlloc(v1064, 8u, 0xC4u);
                                                                                    v1066 = v1065;
                                                                                    if ( !v1065 )
                                                                                      goto LABEL_1737;
                                                                                    v1067 = v1065 + 1;
                                                                                    v1068 = v1066;
                                                                                    if ( v1067 >= v1066
                                                                                      && v1066 + 2 <= v1066 + 49 )
                                                                                    {
                                                                                      *v1066 = 4;
                                                                                      *v1067 = 4;
                                                                                      v1069 = 0;
                                                                                      do
                                                                                      {
                                                                                        v1070 = *v1066 + 4;
                                                                                        if ( *v1066 >= 0xFFFFFFFC )
                                                                                          goto LABEL_1730;
                                                                                        v1071 = (unsigned __int64)v1066
                                                                                              + v1070;
                                                                                        if ( v1071 < (unsigned __int64)v1066 )
                                                                                          goto LABEL_1730;
                                                                                        ++v1069;
                                                                                        v1066 = (unsigned int *)((char *)v1066 + v1070);
                                                                                      }
                                                                                      while ( !v1069 );
                                                                                      if ( v1071 + 4 < v1071
                                                                                        || v1066 + 41 > v1068 + 49 )
                                                                                      {
                                                                                        goto LABEL_1730;
                                                                                      }
                                                                                      *v1066 = 160;
                                                                                      if ( v1058 )
                                                                                        memcpy_0(
                                                                                          (void *)(v1071 + 4),
                                                                                          v1058,
                                                                                          0xA0u);
                                                                                      if ( !v1061 )
                                                                                        goto LABEL_1726;
                                                                                      if ( v1068 )
                                                                                      {
                                                                                        v1072 = v1068;
                                                                                        v1073 = 0;
                                                                                        while ( 1 )
                                                                                        {
                                                                                          v1074 = *v1072 + 4;
                                                                                          if ( *v1072 >= 0xFFFFFFFC )
                                                                                            goto LABEL_1730;
                                                                                          v1075 = (unsigned __int64)v1072
                                                                                                + v1074;
                                                                                          if ( v1075 < (unsigned __int64)v1072 )
                                                                                            goto LABEL_1730;
                                                                                          ++v1073;
                                                                                          v1072 = (unsigned int *)((char *)v1072 + v1074);
                                                                                          if ( v1073 >= 2 )
                                                                                          {
                                                                                            if ( v1075 + 4 < v1075
                                                                                              || v1072 + 3 > v1068 + 49 )
                                                                                            {
                                                                                              goto LABEL_1729;
                                                                                            }
                                                                                            *v1072 = 8;
                                                                                            memcpy_0(
                                                                                              (void *)(v1075 + 4),
                                                                                              v1061,
                                                                                              8u);
                                                                                            v1076 = 196;
                                                                                            v1077 = (unsigned __int64 *)v1068;
                                                                                            v1063 = v1329;
                                                                                            v1078 = 0;
                                                                                            v1399 = 196;
                                                                                            while ( 1 )
                                                                                            {
                                                                                              v1079 = *(_DWORD *)v1077 + 4;
                                                                                              if ( *(_DWORD *)v1077 >= 0xFFFFFFFC )
                                                                                                goto LABEL_1730;
                                                                                              v1080 = (char *)v1077 + v1079;
                                                                                              if ( v1080 < (char *)v1077 )
                                                                                                goto LABEL_1730;
                                                                                              ++v1078;
                                                                                              v1077 = (unsigned __int64 *)((char *)v1077 + v1079);
                                                                                              if ( v1078 >= 3 )
                                                                                              {
                                                                                                v1081 = (unsigned __int64 *)(v1080 + 4);
                                                                                                if ( v1081 < v1077 )
                                                                                                  goto LABEL_1729;
                                                                                                if ( (char *)v1077 + 12 <= (char *)(v1068 + 49) )
                                                                                                {
                                                                                                  *(_DWORD *)v1077 = 8;
                                                                                                  *v1081 = v1062;
                                                                                                  goto LABEL_1476;
                                                                                                }
                                                                                                goto LABEL_1730;
                                                                                              }
                                                                                            }
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                      v1076 = 220;
                                                                                      v1399 = 220;
LABEL_1476:
                                                                                      v1398 = 4;
                                                                                      v1370 = (unsigned __int16 *)__rdtsc();
                                                                                      v1404 = (v1076 + 15) & 0xFFFFFFF8;
                                                                                      if ( (unsigned int)v1404 < v1076 + 8 )
                                                                                        goto LABEL_1726;
                                                                                      v1082 = 0;
                                                                                      v1419 = 0;
                                                                                      v1083 = GetProcessHeap();
                                                                                      v1084 = HeapAlloc(
                                                                                                v1083,
                                                                                                8u,
                                                                                                (v1076 + 15)
                                                                                              & 0xFFFFFFF8);
                                                                                      v1085 = (char *)v1084;
                                                                                      if ( !v1084 )
                                                                                      {
                                                                                        v1170 = -805306345;
                                                                                        goto LABEL_1719;
                                                                                      }
                                                                                      *v1084 = v1398;
                                                                                      v1086 = v1084 + 1;
                                                                                      if ( v1085 + 4 < v1085
                                                                                        || (*v1086 = v1076,
                                                                                            v1085 + 8 < v1085 + 4) )
                                                                                      {
                                                                                        v1320 = GetProcessHeap();
                                                                                        HeapFree(v1320, 0, v1085);
                                                                                        v1170 = -805306219;
                                                                                        goto LABEL_1719;
                                                                                      }
                                                                                      LODWORD(v1089) = v1404;
                                                                                      v1087 = 0;
                                                                                      v1088 = v1399;
                                                                                      v1429 = 0;
                                                                                      v1415 = 0;
                                                                                      v1414 = 0;
                                                                                      v1417 = 0;
                                                                                      *(_QWORD *)&v1085[(unsigned int)v1404 - 8] = v1370;
                                                                                      memcpy_0(v1085 + 8, v1068, v1088);
                                                                                      v1089 = (unsigned int)v1089;
                                                                                      v1402 = v1089;
                                                                                      if ( !(_DWORD)v1089
                                                                                        || (v1410 = (unsigned int)v1089 + 8LL,
                                                                                            psz = (STRSAFE_PCNZWCH)MemoryAllocT<unsigned long>(v1410),
                                                                                            (v1090 = psz) == 0) )
                                                                                      {
                                                                                        v1171 = 0;
                                                                                        goto LABEL_1693;
                                                                                      }
                                                                                      v1091 = 0;
                                                                                      pcchLength = (size_t)v1085;
                                                                                      v1092 = 0;
                                                                                      if ( (unsigned int)v1089 < 0x20uLL )
                                                                                        goto LABEL_1773;
                                                                                      pcchLength = (size_t)v1085;
                                                                                      v1093 = 0;
                                                                                      v1094 = 0;
                                                                                      do
                                                                                      {
                                                                                        v1093 = _mm_xor_ps(
                                                                                                  v1093,
                                                                                                  (__m128)_mm_loadu_si128((const __m128i *)&v1085[v1092]));
                                                                                        v1095 = (__m128)_mm_loadu_si128((const __m128i *)&v1085[v1092 + 16]);
                                                                                        v1092 += 32LL;
                                                                                        v1094 = _mm_xor_ps(v1094, v1095);
                                                                                      }
                                                                                      while ( v1092 < (v1089 & 0xFFFFFFE0) );
                                                                                      v1096 = _mm_xor_ps(v1094, v1093);
                                                                                      v1097 = _mm_xor_ps(
                                                                                                v1096,
                                                                                                (__m128)_mm_srli_si128((__m128i)v1096, 8));
                                                                                      v1098 = _mm_xor_ps(
                                                                                                v1097,
                                                                                                (__m128)_mm_srli_si128((__m128i)v1097, 4));
                                                                                      v1099 = _mm_xor_ps(
                                                                                                v1098,
                                                                                                (__m128)_mm_srli_si128((__m128i)v1098, 2));
                                                                                      v1091 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v1099, (__m128)_mm_srli_si128((__m128i)v1099, 1)));
                                                                                      v1396 = v1091;
                                                                                      if ( v1092 < (unsigned int)v1089 )
                                                                                      {
LABEL_1773:
                                                                                        do
                                                                                          v1091 ^= v1085[v1092++];
                                                                                        while ( v1092 < (unsigned int)v1089 );
                                                                                        v1396 = v1091;
                                                                                      }
                                                                                      v1411 = v1068;
                                                                                      v1406 = 0xC81ECB17B1B54A58uLL;
                                                                                      v1371 = (unsigned __int16 *)((unsigned __int64)(unsigned int)v1089 >> 3);
                                                                                      if ( v1371 )
                                                                                      {
                                                                                        v1100 = HIDWORD(v1406);
                                                                                        v1101 = psz;
                                                                                        v1102 = (unsigned __int8 *)pcchLength;
                                                                                        v1103 = WORD1(v1406);
                                                                                        v1104 = -1;
                                                                                        LODWORD(Src) = HIWORD(HIDWORD(v1406));
                                                                                        LODWORD(Size) = HIWORD(HIDWORD(v1406));
                                                                                        v1105 = HIWORD(HIDWORD(v1406));
                                                                                        LODWORD(v1409) = HIDWORD(v1406) ^ 0xB1B54A58;
                                                                                        v1404 = 0;
                                                                                        v1106 = WORD2(v1406);
                                                                                        LODWORD(v1416) = 0;
                                                                                        v1407 = 0;
                                                                                        v1399 = 0;
                                                                                        v1403 = (void *)pcchLength;
                                                                                        do
                                                                                        {
                                                                                          v1107 = *v1102;
                                                                                          v1108 = v1102[1];
                                                                                          v1109 = v1102[4];
                                                                                          v1102 += 8;
                                                                                          v1110 = *(v1102 - 5)
                                                                                                | ((*(v1102 - 6)
                                                                                                  | (((v1107 << 8) | v1108) << 8)) << 8);
                                                                                          v1111 = *(v1102 - 1)
                                                                                                | ((*(v1102 - 2)
                                                                                                  | ((*(v1102 - 3) | (v1109 << 8)) << 8)) << 8);
                                                                                          v1112 = v1399
                                                                                                ^ v1110
                                                                                                ^ ((v1104 ^ v1111)
                                                                                                 - 19032);
                                                                                          v1113 = v1112 ^ v1100;
                                                                                          v1114 = v1104
                                                                                                ^ v1111
                                                                                                ^ (__ROR4__(v1113, 7)
                                                                                                 + v1103
                                                                                                 * __ROR4__(v1112, 15));
                                                                                          v1115 = v1113
                                                                                                ^ (v1106
                                                                                                 * __ROR4__(
                                                                                                     v1114 - 1313519016,
                                                                                                     9)
                                                                                                 - __ROR4__(v1114, 10));
                                                                                          v1116 = v1114
                                                                                                ^ (__ROR4__(v1115, 27)
                                                                                                 + v1105
                                                                                                 * __ROR4__(
                                                                                                     v1115 ^ v1106,
                                                                                                     28));
                                                                                          v1117 = v1115
                                                                                                ^ (HIDWORD(v1406)
                                                                                                 - (v1116 ^ 0xB1B54A58));
                                                                                          v1118 = v1117
                                                                                                ^ (19032
                                                                                                 * (v1106
                                                                                                  ^ __ROR4__(v1116 ^ (v1103 * (v1117 - 19032) - (v1117 >> 6)), 15)));
                                                                                          v1119 = v1116
                                                                                                ^ (v1103
                                                                                                 * (v1117 - 19032)
                                                                                                 - (v1117 >> 6))
                                                                                                ^ (v1106
                                                                                                 * (v1105
                                                                                                  + __ROR4__(~v1118, 3)));
                                                                                          v1120 = v1118
                                                                                                ^ (v1119
                                                                                                 - 19032
                                                                                                 - HIDWORD(v1406));
                                                                                          v1121 = v1119
                                                                                                ^ (v1103
                                                                                                 * ((unsigned int)Src
                                                                                                  ^ v1120))
                                                                                                ^ __ROR4__(v1120, 10);
                                                                                          v1122 = v1120
                                                                                                ^ __ROR4__(v1121, 3)
                                                                                                ^ (v1106
                                                                                                 * __ROR4__(
                                                                                                     v1121 ^ 0x4A58,
                                                                                                     26));
                                                                                          v1123 = v1121
                                                                                                ^ (19032
                                                                                                 * (__ROR4__(v1122, 15)
                                                                                                  - v1105));
                                                                                          v1124 = v1122
                                                                                                ^ (19032
                                                                                                 * ((unsigned int)Src
                                                                                                  ^ v1123))
                                                                                                ^ ((v1123 ^ (v1123 >> 14)) >> 1)
                                                                                                ^ (19032
                                                                                                 * (((v1123 - v1106) >> 29)
                                                                                                  | (8 * (v1123 - v1106))));
                                                                                          v1125 = v1123
                                                                                                ^ (v1103
                                                                                                 * (v1124 - v1106)
                                                                                                 - (v1124 >> 13));
                                                                                          v1126 = v1124
                                                                                                ^ __ROR4__(v1125, 11)
                                                                                                ^ (v1106
                                                                                                 * __ROR4__(
                                                                                                     -1313519016 - v1125,
                                                                                                     9));
                                                                                          v1127 = v1125
                                                                                                ^ (v1126
                                                                                                 - v1105
                                                                                                 + 1313519016);
                                                                                          v1128 = v1126
                                                                                                ^ (19032
                                                                                                 * (v1103 ^ v1127)
                                                                                                 - __ROR4__(v1127, 7));
                                                                                          v1129 = v1127
                                                                                                ^ (v1103
                                                                                                 * __ROR4__(
                                                                                                     (unsigned int)Src ^ v1128,
                                                                                                     28)
                                                                                                 - __ROR4__(v1128, 16));
                                                                                          v1130 = v1128
                                                                                                ^ (__ROR4__(v1129, 4)
                                                                                                 + v1106
                                                                                                 * __ROR4__(
                                                                                                     -1313519016 - v1129,
                                                                                                     10));
                                                                                          v1101 += 4;
                                                                                          v1131 = v1129
                                                                                                ^ __ROR4__(v1130, 9)
                                                                                                ^ (v1105
                                                                                                 * __ROR4__(
                                                                                                     v1130 + 1313519016,
                                                                                                     4));
                                                                                          v1132 = v1130
                                                                                                ^ (19032
                                                                                                 * __ROR4__(
                                                                                                     HIDWORD(v1406) ^ v1131,
                                                                                                     24)
                                                                                                 - __ROR4__(v1131, 30));
                                                                                          v1133 = v1131
                                                                                                ^ (v1103
                                                                                                 * __ROR4__(
                                                                                                     HIDWORD(v1406) - v1132,
                                                                                                     11)
                                                                                                 - __ROR4__(v1132, 12));
                                                                                          v1134 = v1132
                                                                                                ^ (v1133 >> 8)
                                                                                                ^ (v1106
                                                                                                 * (v1103 ^ v1133));
                                                                                          v1135 = v1133 ^ v1134;
                                                                                          v1136 = v1416 ^ v1134;
                                                                                          v1104 = (unsigned int)v1409
                                                                                                ^ v1407
                                                                                                ^ v1135;
                                                                                          *((_BYTE *)v1101 - 5) = v1136;
                                                                                          *((_BYTE *)v1101 - 1) = v1104;
                                                                                          *((_BYTE *)v1101 - 6) = __ROR4__(v1136, 8);
                                                                                          *((_BYTE *)v1101 - 2) = __ROR4__(v1104, 8);
                                                                                          *((_BYTE *)v1101 - 7) = __ROR4__(v1136, 16);
                                                                                          *((_BYTE *)v1101 - 3) = __ROR4__(v1104, 16);
                                                                                          *((_BYTE *)v1101 - 8) = __ROR4__(v1136, 24);
                                                                                          *((_BYTE *)v1101 - 4) = __ROR4__(v1104, 24);
                                                                                          v1399 = v1136;
                                                                                          v1100 = HIDWORD(v1406);
                                                                                          LODWORD(v1416) = v1110;
                                                                                          v1407 = v1111;
                                                                                          ++v1404;
                                                                                        }
                                                                                        while ( v1404 < (unsigned __int64)v1371 );
                                                                                        v1082 = v1429;
                                                                                        v1068 = v1411;
                                                                                        v1087 = (unsigned int *)v1429;
                                                                                        v1085 = (char *)v1403;
                                                                                        v1089 = v1402;
                                                                                        v1090 = psz;
                                                                                      }
                                                                                      *(_QWORD *)((char *)v1090 + v1089) = v1396;
                                                                                      v1137 = GetProcessHeap();
                                                                                      v1138 = HeapAlloc(
                                                                                                v1137,
                                                                                                8u,
                                                                                                0x30u);
                                                                                      if ( v1138 )
                                                                                      {
                                                                                        v1140 = v1410;
                                                                                        *(_DWORD *)v1138 = v1410;
                                                                                        v1141 = GetProcessHeap();
                                                                                        v1142 = HeapAlloc(
                                                                                                  v1141,
                                                                                                  8u,
                                                                                                  v1140);
                                                                                        if ( !v1142 )
                                                                                          goto LABEL_1497;
                                                                                        v1143 = psz;
                                                                                        *((_QWORD *)v1138 + 1) = v1142;
                                                                                        memcpy_0(v1142, v1143, v1140);
                                                                                        *((_DWORD *)v1138 + 4) = 160;
                                                                                        v1144 = GetProcessHeap();
                                                                                        v1145 = HeapAlloc(
                                                                                                  v1144,
                                                                                                  8u,
                                                                                                  0xA0u);
                                                                                        if ( !v1145 )
                                                                                          goto LABEL_1497;
                                                                                        *((_QWORD *)v1138 + 3) = v1145;
                                                                                        *v1145 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                                                                                        v1145[1] = xmmword_1800AD3C0;
                                                                                        v1145[2] = xmmword_1800AD3D0;
                                                                                        v1145[3] = xmmword_1800AD3E0;
                                                                                        v1145[4] = xmmword_1800AD3F0;
                                                                                        v1145[5] = xmmword_1800AD400;
                                                                                        v1145[6] = xmmword_1800AD410;
                                                                                        v1145[7] = xmmword_1800AD420;
                                                                                        v1145[8] = xmmword_1800AD430;
                                                                                        v1145[9] = xmmword_1800AD440;
                                                                                        *((_DWORD *)v1138 + 8) = 8;
                                                                                        v1146 = GetProcessHeap();
                                                                                        v1147 = HeapAlloc(v1146, 8u, 8u);
                                                                                        if ( v1147 )
                                                                                        {
                                                                                          *((_QWORD *)v1138 + 5) = v1147;
                                                                                          v1139 = 0;
                                                                                          *v1147 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                                                                                          v1082 = v1138;
                                                                                        }
                                                                                        else
                                                                                        {
LABEL_1497:
                                                                                          v1139 = -1073741801;
                                                                                          v1372 = (unsigned __int16 *)*((_QWORD *)v1138 + 1);
                                                                                          if ( v1372 )
                                                                                          {
                                                                                            v1148 = GetProcessHeap();
                                                                                            HeapFree(v1148, 0, v1372);
                                                                                            *((_QWORD *)v1138 + 1) = 0;
                                                                                          }
                                                                                          v1373 = (unsigned __int16 *)*((_QWORD *)v1138 + 3);
                                                                                          if ( v1373 )
                                                                                          {
                                                                                            v1149 = GetProcessHeap();
                                                                                            HeapFree(v1149, 0, v1373);
                                                                                            *((_QWORD *)v1138 + 3) = 0;
                                                                                          }
                                                                                          v1374 = (unsigned __int16 *)*((_QWORD *)v1138 + 5);
                                                                                          if ( v1374 )
                                                                                          {
                                                                                            v1150 = GetProcessHeap();
                                                                                            HeapFree(v1150, 0, v1374);
                                                                                            *((_QWORD *)v1138 + 5) = 0;
                                                                                          }
                                                                                          v1151 = GetProcessHeap();
                                                                                          HeapFree(v1151, 0, v1138);
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v1139 = -1073741801;
                                                                                      }
                                                                                      v1152 = GetProcessHeap();
                                                                                      HeapFree(v1152, 0, (LPVOID)psz);
                                                                                      v1153 = v1139 | 0x10000000;
                                                                                      if ( v1153 < 0 )
                                                                                      {
                                                                                        v1170 = v1153;
                                                                                        v1171 = v1415;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      if ( *(_DWORD *)v1082 >= 0xFFFFFFFC
                                                                                        || (v1154 = *(_DWORD *)v1082 + 8,
                                                                                            v1154 < *(_DWORD *)v1082 + 4)
                                                                                        || (v1155 = v1154 + *((_DWORD *)v1082 + 4),
                                                                                            v1155 < v1154)
                                                                                        || (v1156 = v1155 + 4,
                                                                                            v1155 + 4 < v1155)
                                                                                        || (v1157 = v1156 + *((_DWORD *)v1082 + 8),
                                                                                            LODWORD(Size) = v1157,
                                                                                            v1157 < v1156) )
                                                                                      {
                                                                                        v1170 = -805306219;
                                                                                        v1171 = v1415;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      v1158 = v1157;
                                                                                      v1159 = GetProcessHeap();
                                                                                      v1160 = HeapAlloc(
                                                                                                v1159,
                                                                                                8u,
                                                                                                v1158);
                                                                                      if ( !v1160 )
                                                                                      {
                                                                                        v1170 = -805306345;
                                                                                        v1171 = v1415;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      v1161 = v1160 + 1;
                                                                                      *v1160 = *(_DWORD *)v1082;
                                                                                      if ( v1160 + 1 < v1160 )
                                                                                        goto LABEL_1688;
                                                                                      memcpy_0(
                                                                                        v1160 + 1,
                                                                                        (const void *)v1082[1],
                                                                                        *(unsigned int *)v1082);
                                                                                      v1162 = (_DWORD *)((char *)v1161 + *(unsigned int *)v1082);
                                                                                      if ( v1162 < v1161
                                                                                        || (v1163 = v1162 + 1,
                                                                                            *v1162 = *((_DWORD *)v1082 + 4),
                                                                                            v1162 + 1 < v1162)
                                                                                        || (memcpy_0(
                                                                                              v1162 + 1,
                                                                                              (const void *)v1082[3],
                                                                                              *((unsigned int *)v1082 + 4)),
                                                                                            v1164 = (_DWORD *)((char *)v1163 + *((unsigned int *)v1082 + 4)),
                                                                                            v1164 < v1163)
                                                                                        || (v1165 = v1164 + 1,
                                                                                            *v1164 = *((_DWORD *)v1082 + 8),
                                                                                            v1164 + 1 < v1164)
                                                                                        || (memcpy_0(
                                                                                              v1164 + 1,
                                                                                              (const void *)v1082[5],
                                                                                              *((unsigned int *)v1082 + 8)),
                                                                                            (_DWORD *)((char *)v1165 + *((unsigned int *)v1082 + 8)) < v1165) )
                                                                                      {
LABEL_1688:
                                                                                        v1299 = GetProcessHeap();
                                                                                        HeapFree(v1299, 0, v1160);
                                                                                        v1170 = -805306219;
                                                                                        v1171 = v1415;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      if ( !v1068 )
                                                                                      {
                                                                                        v1166 = -1073741811;
                                                                                        goto LABEL_1687;
                                                                                      }
                                                                                      if ( v1398 <= 1 )
                                                                                      {
                                                                                        v1166 = -1073741811;
                                                                                        goto LABEL_1687;
                                                                                      }
                                                                                      v1167 = v1068 + 1;
                                                                                      if ( v1068 + 1 < v1068
                                                                                        || (v1168 = (unsigned int *)((char *)v1167 + *v1068),
                                                                                            v1168 < v1167)
                                                                                        || (v1169 = v1168 + 1,
                                                                                            v1168 + 1 < v1168) )
                                                                                      {
                                                                                        v1166 = -1073741675;
LABEL_1687:
                                                                                        LODWORD(Size) = v1166;
                                                                                        v1415 = v1160;
                                                                                        v1170 = v1166;
                                                                                        v1171 = v1160;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      v1415 = v1160;
                                                                                      if ( v1398 <= 2 )
                                                                                      {
                                                                                        v1170 = -1073741811;
                                                                                        v1171 = v1160;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      v1172 = *v1168;
                                                                                      v1173 = (unsigned int *)((char *)v1169 + v1172);
                                                                                      if ( (unsigned int *)((char *)v1169 + v1172) < v1169 )
                                                                                      {
                                                                                        v1415 = v1160;
                                                                                      }
                                                                                      else if ( v1173 + 1 >= v1173 )
                                                                                      {
                                                                                        v1174 = v1172 + 48;
                                                                                        if ( (unsigned int)v1172 >= 0xFFFFFFD0
                                                                                          || (v1175 = v1172 + 52,
                                                                                              v1174 + 4 < v1174)
                                                                                          || (v1176 = v1175 + *v1173,
                                                                                              v1398 = v1176,
                                                                                              v1176 < v1175) )
                                                                                        {
                                                                                          v1415 = v1160;
                                                                                          v1170 = -1073741675;
                                                                                          v1171 = v1160;
                                                                                          goto LABEL_1694;
                                                                                        }
                                                                                        if ( v1176 > 0x400000 )
                                                                                        {
                                                                                          v1415 = v1160;
                                                                                          v1170 = -2147418113;
                                                                                          v1171 = v1160;
                                                                                          goto LABEL_1694;
                                                                                        }
                                                                                        v1171 = v1160;
                                                                                        v1177 = v1176;
                                                                                        v1178 = GetProcessHeap();
                                                                                        v1087 = (unsigned int *)HeapAlloc(v1178, 8u, v1177);
                                                                                        if ( !v1087 )
                                                                                        {
                                                                                          v1170 = -805306345;
                                                                                          v1087 = 0;
                                                                                          goto LABEL_1694;
                                                                                        }
                                                                                        hModule = 0;
                                                                                        v1444 = Size;
                                                                                        v1179 = v1171;
                                                                                        v1446 = 0;
                                                                                        v1445 = v1398;
                                                                                        v1443[0] = v1171;
                                                                                        v1443[1] = v1087;
                                                                                        if ( GetModuleHandleExW(
                                                                                               1u,
                                                                                               L"ntdll.dll",
                                                                                               &hModule)
                                                                                          && (v1182 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                                                                        {
                                                                                          v1180 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, _QWORD))v1182)(
                                                                                                    134,
                                                                                                    v1443,
                                                                                                    32,
                                                                                                    0)
                                                                                                | 0x10000000;
                                                                                          if ( v1180 >= 0 )
                                                                                          {
                                                                                            v1183 = v1445;
                                                                                            goto LABEL_1547;
                                                                                          }
LABEL_1544:
                                                                                          v1183 = v1398;
                                                                                          if ( v1180 == -805306333 )
                                                                                          {
                                                                                            v1170 = -2147024774;
                                                                                            goto LABEL_1694;
                                                                                          }
                                                                                          if ( v1180 >= 0 )
                                                                                          {
LABEL_1547:
                                                                                            if ( v1183 < 4 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            v1184 = *v1087;
                                                                                            v1185 = v1087 + 1;
                                                                                            LODWORD(Size) = *v1087;
                                                                                            if ( v1087 + 1 < v1087 )
                                                                                              goto LABEL_1681;
                                                                                            if ( v1183 - 4 < (unsigned int)v1184 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            v1186 = (unsigned int *)((char *)v1185 + v1184);
                                                                                            v1404 = v1184;
                                                                                            v1410 = (SIZE_T)v1185 + v1184;
                                                                                            if ( (unsigned int *)((char *)v1185 + v1184) < v1185
                                                                                              || (unsigned int)v1184 >= 0xFFFFFFFC )
                                                                                            {
                                                                                              goto LABEL_1681;
                                                                                            }
                                                                                            if ( v1183
                                                                                               - ((_DWORD)v1184
                                                                                                + 4) < 4 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            v1187 = (unsigned int)*v1186;
                                                                                            v1188 = v1186 + 1;
                                                                                            LODWORD(Src) = *v1186;
                                                                                            if ( v1186 + 1 < v1186 )
                                                                                              goto LABEL_1681;
                                                                                            v1189 = v1184 + 8;
                                                                                            if ( (int)v1184 + 8 < (unsigned int)(v1184 + 4) )
                                                                                              goto LABEL_1681;
                                                                                            if ( v1183 - v1189 < (unsigned int)v1187 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            v1190 = (unsigned __int64)v1188 + v1187;
                                                                                            v1402 = v1187;
                                                                                            v1375 = (unsigned __int16 *)((char *)v1188 + v1187);
                                                                                            if ( (_DWORD *)((char *)v1188 + v1187) < v1188 )
                                                                                              goto LABEL_1681;
                                                                                            v1191 = v1189 + v1187;
                                                                                            if ( v1189
                                                                                               + (unsigned int)v1187 < v1189 )
                                                                                              goto LABEL_1681;
                                                                                            if ( v1183 - v1191 < 4 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            v1412 = (void *)(v1190 + 4);
                                                                                            if ( v1190 + 4 < v1190 )
                                                                                              goto LABEL_1681;
                                                                                            v1192 = v1191 + 4;
                                                                                            if ( v1191 + 4 < v1191 )
                                                                                              goto LABEL_1681;
                                                                                            v1193 = *(_DWORD *)v1375;
                                                                                            LODWORD(v1409) = v1193;
                                                                                            if ( v1183 - v1192 < v1193 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            if ( v1192 + v1193 < v1192 )
                                                                                            {
LABEL_1681:
                                                                                              v1170 = -805306219;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            if ( v1183 != v1192 + v1193 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            if ( (unsigned int)v1184
                                                                                               + (_DWORD)v1187
                                                                                               + v1193
                                                                                               + 12LL != v1183 )
                                                                                            {
                                                                                              v1170 = -805306306;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            v1194 = GetProcessHeap();
                                                                                            pcchLength = (size_t)HeapAlloc(v1194, 8u, 0x30u);
                                                                                            v1195 = pcchLength;
                                                                                            if ( !pcchLength )
                                                                                            {
                                                                                              v1171 = v1179;
                                                                                              v1170 = -805306345;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            if ( v1087 != (unsigned int *)-4LL )
                                                                                            {
                                                                                              *(_DWORD *)pcchLength = Size;
                                                                                              v1196 = GetProcessHeap();
                                                                                              v1197 = HeapAlloc(v1196, 8u, v1404);
                                                                                              if ( v1197 )
                                                                                              {
                                                                                                v1198 = v1404;
                                                                                                *(_QWORD *)(v1195 + 8) = v1197;
                                                                                                v1343 = 0;
                                                                                                memcpy_0(
                                                                                                  v1197,
                                                                                                  v1087 + 1,
                                                                                                  v1198);
                                                                                                goto LABEL_1579;
                                                                                              }
LABEL_1586:
                                                                                              v1171 = v1179;
                                                                                              v1415 = v1179;
                                                                                              v1206 = (_QWORD *)pcchLength;
                                                                                              v1343 = -1073741801;
                                                                                              v1422 = v1087;
                                                                                              v1429 = v1082;
                                                                                              v1207 = *(unsigned __int16 **)(pcchLength + 8);
                                                                                              v1403 = v1085;
                                                                                              v1411 = v1068;
                                                                                              psz = 0;
                                                                                              v1376 = v1207;
                                                                                              if ( v1207 )
                                                                                              {
                                                                                                v1208 = GetProcessHeap();
                                                                                                HeapFree(
                                                                                                  v1208,
                                                                                                  0,
                                                                                                  v1376);
                                                                                                v1206[1] = 0;
                                                                                              }
                                                                                              v1377 = (unsigned __int16 *)v1206[3];
                                                                                              if ( v1377 )
                                                                                              {
                                                                                                v1209 = GetProcessHeap();
                                                                                                HeapFree(
                                                                                                  v1209,
                                                                                                  0,
                                                                                                  v1377);
                                                                                                v1206[3] = 0;
                                                                                              }
                                                                                              v1378 = (unsigned __int16 *)v1206[5];
                                                                                              if ( v1378 )
                                                                                              {
                                                                                                v1210 = GetProcessHeap();
                                                                                                HeapFree(
                                                                                                  v1210,
                                                                                                  0,
                                                                                                  v1378);
                                                                                                v1206[5] = 0;
                                                                                              }
                                                                                              v1211 = GetProcessHeap();
                                                                                              HeapFree(v1211, 0, v1206);
                                                                                              v1212 = (SIZE_T *)psz;
LABEL_1596:
                                                                                              v1215 = v1343;
                                                                                              if ( v1343 < 0 )
                                                                                              {
                                                                                                v1216 = (wchar_t *)psz;
                                                                                                if ( psz )
                                                                                                {
                                                                                                  v1379 = (unsigned __int16 *)*((_QWORD *)psz + 1);
                                                                                                  if ( v1379 )
                                                                                                  {
                                                                                                    v1217 = GetProcessHeap();
                                                                                                    HeapFree(v1217, 0, v1379);
                                                                                                    *((_QWORD *)v1216 + 1) = 0;
                                                                                                  }
                                                                                                  v1380 = (unsigned __int16 *)*((_QWORD *)v1216 + 3);
                                                                                                  if ( v1380 )
                                                                                                  {
                                                                                                    v1218 = GetProcessHeap();
                                                                                                    HeapFree(v1218, 0, v1380);
                                                                                                    *((_QWORD *)v1216 + 3) = 0;
                                                                                                  }
                                                                                                  v1381 = (unsigned __int16 *)*((_QWORD *)v1216 + 5);
                                                                                                  if ( v1381 )
                                                                                                  {
                                                                                                    v1219 = GetProcessHeap();
                                                                                                    HeapFree(v1219, 0, v1381);
                                                                                                    *((_QWORD *)v1216 + 5) = 0;
                                                                                                  }
                                                                                                  v1220 = GetProcessHeap();
                                                                                                  HeapFree(
                                                                                                    v1220,
                                                                                                    0,
                                                                                                    v1216);
                                                                                                  v1215 = v1343;
                                                                                                }
                                                                                                v1212 = (SIZE_T *)v1414;
                                                                                              }
                                                                                              else
                                                                                              {
                                                                                                v1414 = v1212;
                                                                                              }
                                                                                              v1221 = v1215 | 0x10000000;
                                                                                              if ( v1221 < 0 )
                                                                                              {
                                                                                                v1170 = v1221;
                                                                                                goto LABEL_1694;
                                                                                              }
                                                                                              if ( !v1212 )
                                                                                              {
                                                                                                v1170 = -805306355;
                                                                                                goto LABEL_1694;
                                                                                              }
                                                                                              v1410 = v1212[1];
                                                                                              if ( !v1410 )
                                                                                              {
                                                                                                v1170 = -805306355;
                                                                                                goto LABEL_1694;
                                                                                              }
                                                                                              v1222 = *(unsigned int *)v1212;
                                                                                              if ( !(_DWORD)v1222 )
                                                                                              {
                                                                                                v1170 = -805306355;
                                                                                                goto LABEL_1694;
                                                                                              }
                                                                                              v1223 = v1222 - 8;
                                                                                              v1402 = v1222 - 8;
                                                                                              v1224 = (const wchar_t *)MemoryAllocT<unsigned long>(v1222 - 8);
                                                                                              psz = v1224;
                                                                                              if ( v1224 )
                                                                                              {
                                                                                                v1225 = (unsigned __int8 *)v1410;
                                                                                                LOBYTE(v1407) = 0;
                                                                                                v1412 = (void *)0x7F1137FAB69605ELL;
                                                                                                pcchLength = (size_t)v1224;
                                                                                                v1226 = v1223 & 7;
                                                                                                if ( (v1223 & 7) != 0 )
                                                                                                {
                                                                                                  v1423 = 0;
                                                                                                  v1227 = 0;
                                                                                                  v1400 = 0;
                                                                                                  do
                                                                                                  {
                                                                                                    v1228 = *v1225;
                                                                                                    v1229 = 8 * v1227;
                                                                                                    if ( v1227 >= 4 )
                                                                                                    {
                                                                                                      v1232 = v1400;
                                                                                                      v1231 = (v1228 << (56 - v1229)) | v1423;
                                                                                                      v1423 = v1231;
                                                                                                    }
                                                                                                    else
                                                                                                    {
                                                                                                      v1230 = 24 - v1229;
                                                                                                      v1231 = v1423;
                                                                                                      v1232 = (v1228 << v1230) | v1400;
                                                                                                      v1400 = v1232;
                                                                                                    }
                                                                                                    ++v1225;
                                                                                                    ++v1227;
                                                                                                  }
                                                                                                  while ( (int)v1227 < (int)v1226 );
                                                                                                  v1223 = v1402;
                                                                                                  v1233 = v1232 ^ 0x92F65A5;
                                                                                                  v1234 = (_BYTE *)pcchLength;
                                                                                                  v1235 = v1231 ^ 0x699A899C;
                                                                                                  LODWORD(Size) = v1231 ^ 0x699A899C;
                                                                                                  v1236 = 0;
                                                                                                  LODWORD(v1406) = v1233;
                                                                                                  v1422 = v1087;
                                                                                                  v1415 = v1171;
                                                                                                  v1429 = v1082;
                                                                                                  v1403 = v1085;
                                                                                                  v1411 = v1068;
                                                                                                  do
                                                                                                  {
                                                                                                    if ( v1236 >= 4 )
                                                                                                    {
                                                                                                      v1235 = __ROR4__(v1235, 24);
                                                                                                      v1237 = v1235;
                                                                                                    }
                                                                                                    else
                                                                                                    {
                                                                                                      v1233 = __ROR4__(v1233, 24);
                                                                                                      v1237 = v1233;
                                                                                                    }
                                                                                                    ++v1236;
                                                                                                    *v1234 = v1237;
                                                                                                    v1238 = (size_t)++v1234;
                                                                                                  }
                                                                                                  while ( v1236 < (int)v1226 );
                                                                                                  pcchLength = v1238;
                                                                                                  if ( v1226 <= 4 )
                                                                                                  {
                                                                                                    v1239 = 0;
                                                                                                    if ( v1226 < 4 )
                                                                                                      LODWORD(v1406) = (unsigned int)v1406 >> (8 * (4 - v1226)) << (8 * (4 - v1226));
                                                                                                  }
                                                                                                  else
                                                                                                  {
                                                                                                    v1239 = (unsigned int)Size >> (8 * (8 - v1226)) << (8 * (8 - v1226));
                                                                                                  }
                                                                                                }
                                                                                                else
                                                                                                {
                                                                                                  v1400 = 0;
                                                                                                  v1239 = 0;
                                                                                                  LODWORD(v1406) = 0;
                                                                                                }
                                                                                                v1382 = (unsigned __int16 *)(v1223 >> 3);
                                                                                                if ( v1223 >> 3 )
                                                                                                {
                                                                                                  v1240 = HIDWORD(v1412);
                                                                                                  v1241 = pcchLength;
                                                                                                  v1242 = v1400;
                                                                                                  LODWORD(v1416) = HIDWORD(v1412) ^ 0xAB69605E;
                                                                                                  v1243 = 43881;
                                                                                                  v1244 = HIWORD(HIDWORD(v1412));
                                                                                                  v1245 = 24670;
                                                                                                  v1399 = 43881;
                                                                                                  v1404 = 0;
                                                                                                  LODWORD(Size) = 43881;
                                                                                                  v1246 = WORD2(v1412);
                                                                                                  LODWORD(Src) = 24670;
                                                                                                  do
                                                                                                  {
                                                                                                    v1247 = v1225[3] | ((v1225[2] | ((v1225[1] | (*v1225 << 8)) << 8)) << 8);
                                                                                                    v1248 = v1225[7] | ((v1225[6] | ((v1225[5] | (v1225[4] << 8)) << 8)) << 8);
                                                                                                    v1412 = v1225 + 8;
                                                                                                    v1249 = v1239 ^ v1248 ^ v1416 ^ v1406 ^ v1247;
                                                                                                    v1250 = v1406 ^ v1247 ^ (__ROR4__(v1249, 22) + v1246 * __ROR4__(v1249 + 1419157410, 27));
                                                                                                    v1251 = v1249 ^ (v1243 * __ROR4__(v1250 + v1240, 9) - __ROR4__(v1250, 30));
                                                                                                    v1252 = v1250 ^ (v1245 * (v1251 - v1246) - (v1251 >> 13));
                                                                                                    v1253 = v1251 ^ (v1244 * __ROR4__(v1399 ^ v1252, 26) - __ROR4__(v1252, 30));
                                                                                                    v1254 = v1252 ^ (v1240 - (v1253 ^ 0xAB69605E));
                                                                                                    v1255 = v1253 ^ (v1243 * (v1254 ^ v1246)) ^ __ROR4__(v1254, 6);
                                                                                                    v1256 = v1254 ^ (__ROR4__(v1255, 30) + v1245 * __ROR4__(v1240 + v1255, 15));
                                                                                                    v1257 = v1255 ^ (v1244 * __ROR4__(v1256 + 1419157410, 14) - __ROR4__(v1256, 24));
                                                                                                    v1258 = v1256 ^ __ROR4__(v1257, 10) ^ (v1246 * __ROR4__(v1257 ^ 0xAB69605E, 12));
                                                                                                    v1243 = Size;
                                                                                                    v1259 = v1257 ^ (v1258 >> 10) ^ (Size * (v1244 ^ v1258));
                                                                                                    v1245 = (int)Src;
                                                                                                    v1260 = v1258 ^ (v1244 * ((_DWORD)Src + __ROR4__(~v1259, 5)));
                                                                                                    v1261 = v1259 ^ (v1260 - v1244) ^ 0xAB69605E;
                                                                                                    v1262 = v1260 ^ ((v1261 >> 2) + v1246 * __ROR4__(v1244 ^ v1261, 30));
                                                                                                    v1263 = v1261 ^ (__ROR4__(v1262, 25) + Size * __ROR4__(v1262 - v1240, 6));
                                                                                                    v1264 = v1262 ^ ((_DWORD)Src * (v1263 ^ v1246) + __ROR4__(v1263, 9));
                                                                                                    v1265 = v1263 ^ (__ROR4__(v1264, 25) + v1244 * __ROR4__(v1264 ^ v1399, 27));
                                                                                                    v1266 = v1264 ^ v1265 ^ v1416;
                                                                                                    v1267 = v1265 ^ (v1246 * (__ROR4__(v1266, 3) - Size));
                                                                                                    v1268 = v1266 ^ ((_DWORD)Src * __ROR4__(v1267 - v1240, 1) - __ROR4__(v1267, 6));
                                                                                                    v1241 += 8LL;
                                                                                                    v1269 = v1267 ^ (__ROR4__(v1268, 18) + v1244 * __ROR4__(v1268 - 1419157410, 29));
                                                                                                    v1270 = v1268 ^ (v1246 * __ROR4__(v1269 - 1419157410, 17) - __ROR4__(v1269, 14));
                                                                                                    v1271 = v1269 ^ (v1270 >> 3) ^ (Size * (v1270 ^ (unsigned int)Src));
                                                                                                    v1272 = v1242 ^ __ROR4__(v1271, 30) ^ ((_DWORD)Src * __ROR4__(v1271 ^ v1240, 28));
                                                                                                    v1242 = v1247;
                                                                                                    v1273 = v1270 ^ v1272;
                                                                                                    v1274 = v1423;
                                                                                                    *(_BYTE *)(v1241 - 5) = v1273;
                                                                                                    v1239 = v1271 ^ v1274;
                                                                                                    *(_BYTE *)(v1241 - 1) = v1239;
                                                                                                    *(_BYTE *)(v1241 - 6) = __ROR4__(v1273, 8);
                                                                                                    *(_BYTE *)(v1241 - 2) = __ROR4__(v1239, 8);
                                                                                                    *(_BYTE *)(v1241 - 7) = __ROR4__(v1273, 16);
                                                                                                    *(_BYTE *)(v1241 - 3) = __ROR4__(v1239, 16);
                                                                                                    *(_BYTE *)(v1241 - 8) = __ROR4__(v1273, 24);
                                                                                                    *(_BYTE *)(v1241 - 4) = __ROR4__(v1239, 24);
                                                                                                    LODWORD(v1406) = v1273;
                                                                                                    v1225 = (unsigned __int8 *)v1412;
                                                                                                    v1423 = v1248;
                                                                                                    ++v1404;
                                                                                                  }
                                                                                                  while ( v1404 < (unsigned __int64)v1382 );
                                                                                                  v1068 = v1411;
                                                                                                  v1085 = (char *)v1403;
                                                                                                  v1082 = v1429;
                                                                                                  v1087 = v1422;
                                                                                                  v1171 = v1415;
                                                                                                  v1223 = v1402;
                                                                                                }
                                                                                                v1275 = (wchar_t *)psz;
                                                                                                if ( v1223 )
                                                                                                {
                                                                                                  v1276 = 0;
                                                                                                  if ( v1223 < 0x20 )
                                                                                                  {
                                                                                                    i7 = v1407;
                                                                                                    goto LABEL_1642;
                                                                                                  }
                                                                                                  v1277 = 0;
                                                                                                  v1278 = 0;
                                                                                                  do
                                                                                                  {
                                                                                                    v1277 = _mm_xor_ps(v1277, (__m128)_mm_loadu_si128((const __m128i *)((char *)psz + v1276)));
                                                                                                    v1279 = (__m128)_mm_loadu_si128((const __m128i *)((char *)psz + v1276 + 16));
                                                                                                    v1276 += 32LL;
                                                                                                    v1280 = _mm_xor_ps(v1279, v1278);
                                                                                                    v1278 = v1280;
                                                                                                  }
                                                                                                  while ( v1276 < (v1223 & 0xFFFFFFFFFFFFFFE0uLL) );
                                                                                                  v1281 = _mm_xor_ps(v1277, v1280);
                                                                                                  v1282 = _mm_xor_ps(v1281, (__m128)_mm_srli_si128((__m128i)v1281, 8));
                                                                                                  v1283 = _mm_xor_ps(v1282, (__m128)_mm_srli_si128((__m128i)v1282, 4));
                                                                                                  v1284 = _mm_xor_ps(v1283, (__m128)_mm_srli_si128((__m128i)v1283, 2));
                                                                                                  for ( i7 = _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v1284, (__m128)_mm_srli_si128((__m128i)v1284, 1)));
                                                                                                        v1276 < v1223;
                                                                                                        ++v1276 )
                                                                                                  {
LABEL_1642:
                                                                                                    i7 ^= *((_BYTE *)psz + v1276);
                                                                                                  }
                                                                                                }
                                                                                                else
                                                                                                {
                                                                                                  i7 = v1407;
                                                                                                }
                                                                                                if ( i7 == *(_QWORD *)(v1223 + v1410) )
                                                                                                {
                                                                                                  v1286 = psz;
                                                                                                  v1417 = (size_t)psz;
                                                                                                  if ( (unsigned int)v1223 < 4 )
                                                                                                    goto LABEL_1647;
                                                                                                  if ( psz + 2 < psz )
                                                                                                    goto LABEL_1677;
                                                                                                  if ( (unsigned int)(v1223 - 4) < 4 )
                                                                                                  {
                                                                                                    v1170 = -805306306;
                                                                                                    goto LABEL_1694;
                                                                                                  }
                                                                                                  v1287 = psz + 4;
                                                                                                  if ( psz + 4 < psz + 2 )
                                                                                                    goto LABEL_1677;
                                                                                                  v1288 = *((unsigned int *)psz + 1);
                                                                                                  if ( (int)v1223 - 8 < (unsigned int)v1288 )
                                                                                                  {
                                                                                                    v1170 = -805306306;
                                                                                                    goto LABEL_1694;
                                                                                                  }
                                                                                                  if ( (unsigned int)v1288 >= 0xFFFFFFF8 )
                                                                                                  {
LABEL_1677:
                                                                                                    v1297 = -1073741675;
                                                                                                  }
                                                                                                  else
                                                                                                  {
                                                                                                    v1289 = (unsigned __int64)v1287 + v1288;
                                                                                                    v1290 = *((unsigned int *)psz + 1);
                                                                                                    v1404 = v1290;
                                                                                                    if ( (char *)psz + (unsigned int)v1223 < (char *)v1287 + v1288 || (unsigned __int64)(unsigned int)v1223 + -v1288 - 8 >= 8 )
                                                                                                    {
LABEL_1647:
                                                                                                      v1170 = -805306306;
                                                                                                      goto LABEL_1694;
                                                                                                    }
                                                                                                    v1291 = 0;
                                                                                                    if ( psz != (STRSAFE_PCNZWCH)-8LL )
                                                                                                    {
                                                                                                      if ( v1289 < (unsigned __int64)v1287 )
                                                                                                        goto LABEL_1677;
                                                                                                      v1292 = psz + 4;
                                                                                                      if ( v1289 > (unsigned __int64)v1287 )
                                                                                                      {
                                                                                                        while ( v1292 + 2 >= v1292 )
                                                                                                        {
                                                                                                          if ( (unsigned __int64)(v1292 + 2) > v1289 )
                                                                                                            goto LABEL_1668;
                                                                                                          v1293 = *(_DWORD *)v1292 + 4;
                                                                                                          if ( *(_DWORD *)v1292 >= 0xFFFFFFFC )
                                                                                                            break;
                                                                                                          v1294 = (char *)v1292 + v1293;
                                                                                                          if ( v1294 < (char *)v1292 )
                                                                                                            break;
                                                                                                          if ( (unsigned __int64)v1294 > v1289 )
                                                                                                            goto LABEL_1668;
                                                                                                          ++v1291;
                                                                                                          v1292 = (STRSAFE_PCNZWCH)((char *)v1292 + v1293);
                                                                                                          if ( (unsigned __int64)v1294 >= v1289 )
                                                                                                          {
                                                                                                            v1286 = (_DWORD *)v1417;
                                                                                                            goto LABEL_1667;
                                                                                                          }
                                                                                                        }
                                                                                                        goto LABEL_1677;
                                                                                                      }
LABEL_1667:
                                                                                                      if ( v1292 != (STRSAFE_PCNZWCH)v1289 )
                                                                                                      {
LABEL_1668:
                                                                                                        v1170 = -805306355;
                                                                                                        goto LABEL_1694;
                                                                                                      }
                                                                                                    }
                                                                                                    LODWORD(Size) = *v1286;
                                                                                                    v1295 = 0;
                                                                                                    v1402 = 0;
                                                                                                    if ( (_DWORD)v1288 )
                                                                                                    {
                                                                                                      v1296 = GetProcessHeap();
                                                                                                      v1295 = HeapAlloc(v1296, 8u, v1404);
                                                                                                      v1402 = (SIZE_T)v1295;
                                                                                                      if ( v1295 )
                                                                                                      {
                                                                                                        v1290 = v1404;
                                                                                                        goto LABEL_1672;
                                                                                                      }
                                                                                                      v1170 = -805306345;
LABEL_1694:
                                                                                                      if ( v1085 )
                                                                                                      {
                                                                                                        v1300 = GetProcessHeap();
                                                                                                        HeapFree(v1300, 0, v1085);
                                                                                                      }
                                                                                                      if ( v1082 )
                                                                                                      {
                                                                                                        v1301 = (void *)v1082[1];
                                                                                                        if ( v1301 )
                                                                                                        {
                                                                                                          v1302 = GetProcessHeap();
                                                                                                          HeapFree(v1302, 0, v1301);
                                                                                                          v1082[1] = 0;
                                                                                                        }
                                                                                                        v1303 = (void *)v1082[3];
                                                                                                        if ( v1303 )
                                                                                                        {
                                                                                                          v1304 = GetProcessHeap();
                                                                                                          HeapFree(v1304, 0, v1303);
                                                                                                          v1082[3] = 0;
                                                                                                        }
                                                                                                        v1305 = (void *)v1082[5];
                                                                                                        if ( v1305 )
                                                                                                        {
                                                                                                          v1306 = GetProcessHeap();
                                                                                                          HeapFree(v1306, 0, v1305);
                                                                                                          v1082[5] = 0;
                                                                                                        }
                                                                                                        v1307 = GetProcessHeap();
                                                                                                        HeapFree(v1307, 0, v1082);
                                                                                                      }
                                                                                                      if ( v1171 )
                                                                                                      {
                                                                                                        v1308 = GetProcessHeap();
                                                                                                        HeapFree(v1308, 0, v1171);
                                                                                                      }
                                                                                                      if ( v1087 )
                                                                                                      {
                                                                                                        v1309 = GetProcessHeap();
                                                                                                        HeapFree(v1309, 0, v1087);
                                                                                                      }
                                                                                                      v1310 = v1414;
                                                                                                      if ( v1414 )
                                                                                                      {
                                                                                                        v1311 = (void *)*((_QWORD *)v1414 + 1);
                                                                                                        if ( v1311 )
                                                                                                        {
                                                                                                          v1312 = GetProcessHeap();
                                                                                                          HeapFree(v1312, 0, v1311);
                                                                                                          v1310[1] = 0;
                                                                                                        }
                                                                                                        v1313 = (void *)v1310[3];
                                                                                                        if ( v1313 )
                                                                                                        {
                                                                                                          v1314 = GetProcessHeap();
                                                                                                          HeapFree(v1314, 0, v1313);
                                                                                                          v1310[3] = 0;
                                                                                                        }
                                                                                                        v1315 = (void *)v1310[5];
                                                                                                        if ( v1315 )
                                                                                                        {
                                                                                                          v1316 = GetProcessHeap();
                                                                                                          HeapFree(v1316, 0, v1315);
                                                                                                          v1310[5] = 0;
                                                                                                        }
                                                                                                        v1317 = GetProcessHeap();
                                                                                                        HeapFree(v1317, 0, v1310);
                                                                                                      }
                                                                                                      v1318 = (void *)v1417;
                                                                                                      if ( v1417 )
                                                                                                      {
                                                                                                        v1319 = GetProcessHeap();
                                                                                                        HeapFree(v1319, 0, v1318);
                                                                                                      }
                                                                                                      LODWORD(v1082) = v1419;
LABEL_1719:
                                                                                                      if ( v1170 >= 0 && (_DWORD)v1082 && lpMem )
                                                                                                        v1058 = v1418;
                                                                                                      else
                                                                                                        v1058 = v1418;
LABEL_1726:
                                                                                                      if ( !v1068 )
                                                                                                        goto LABEL_1731;
                                                                                                      goto LABEL_1730;
                                                                                                    }
LABEL_1672:
                                                                                                    if ( v1287 )
                                                                                                      memcpy_0(v1295, v1287, v1290);
                                                                                                    lpMem = (LPVOID)v1402;
                                                                                                    v1419 = v1291;
                                                                                                    v1297 = 0;
                                                                                                    if ( (_DWORD)Size != v1291 )
                                                                                                    {
                                                                                                      v1170 = -805306306;
                                                                                                      goto LABEL_1694;
                                                                                                    }
                                                                                                  }
                                                                                                  v1170 = v1297 | 0x10000000;
                                                                                                  goto LABEL_1694;
                                                                                                }
                                                                                                v1298 = GetProcessHeap();
                                                                                                HeapFree(
                                                                                                  v1298,
                                                                                                  0,
                                                                                                  v1275);
                                                                                              }
LABEL_1693:
                                                                                              v1170 = -805306367;
                                                                                              goto LABEL_1694;
                                                                                            }
                                                                                            *(_DWORD *)pcchLength = 0;
                                                                                            *(_QWORD *)(v1195 + 8) = 0;
                                                                                            v1343 = 0;
LABEL_1579:
                                                                                            if ( v1410 != -4 )
                                                                                            {
                                                                                              *(_DWORD *)(v1195 + 16) = (_DWORD)Src;
                                                                                              v1199 = GetProcessHeap();
                                                                                              v1200 = HeapAlloc(v1199, 8u, v1402);
                                                                                              if ( v1200 )
                                                                                              {
                                                                                                v1201 = v1402;
                                                                                                v1202 = (const void *)(v1410 + 4);
                                                                                                *(_QWORD *)(v1195 + 24) = v1200;
                                                                                                v1343 = 0;
                                                                                                memcpy_0(
                                                                                                  v1200,
                                                                                                  v1202,
                                                                                                  v1201);
                                                                                                goto LABEL_1583;
                                                                                              }
LABEL_1585:
                                                                                              pcchLength = v1195;
                                                                                              goto LABEL_1586;
                                                                                            }
                                                                                            *(_DWORD *)(v1195 + 16) = 0;
                                                                                            *(_QWORD *)(v1195 + 24) = 0;
LABEL_1583:
                                                                                            if ( v1412 )
                                                                                            {
                                                                                              v1203 = (unsigned int)v1409;
                                                                                              *(_DWORD *)(v1195 + 32) = (_DWORD)v1409;
                                                                                              v1404 = v1203;
                                                                                              v1204 = GetProcessHeap();
                                                                                              v1205 = HeapAlloc(v1204, 8u, v1404);
                                                                                              if ( !v1205 )
                                                                                                goto LABEL_1585;
                                                                                              v1213 = v1404;
                                                                                              v1214 = v1412;
                                                                                              v1343 = 0;
                                                                                              *(_QWORD *)(v1195 + 40) = v1205;
                                                                                              memcpy_0(
                                                                                                v1205,
                                                                                                v1214,
                                                                                                v1213);
                                                                                            }
                                                                                            else
                                                                                            {
                                                                                              *(_DWORD *)(v1195 + 32) = 0;
                                                                                              *(_QWORD *)(v1195 + 40) = 0;
                                                                                            }
                                                                                            v1212 = (SIZE_T *)v1195;
                                                                                            psz = (STRSAFE_PCNZWCH)v1195;
                                                                                            v1171 = v1179;
                                                                                            v1422 = v1087;
                                                                                            v1415 = v1179;
                                                                                            v1429 = v1082;
                                                                                            v1403 = v1085;
                                                                                            v1411 = v1068;
                                                                                            goto LABEL_1596;
                                                                                          }
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v1180 = GetLastError();
                                                                                          v1181 = v1180 < 0;
                                                                                          if ( v1180 > 0 )
                                                                                          {
                                                                                            v1180 = (unsigned __int16)v1180 | 0x80070000;
                                                                                            v1181 = v1180 < 0;
                                                                                          }
                                                                                          if ( v1181 )
                                                                                            goto LABEL_1544;
                                                                                          v1180 = -2147467259;
                                                                                        }
                                                                                        v1170 = v1180;
                                                                                        goto LABEL_1694;
                                                                                      }
                                                                                      v1171 = v1415;
                                                                                      v1170 = -1073741675;
                                                                                      goto LABEL_1694;
                                                                                    }
                                                                                    v1413 = v1061;
LABEL_1729:
                                                                                    v1329 = v1063;
LABEL_1730:
                                                                                    v1321 = GetProcessHeap();
                                                                                    HeapFree(v1321, 0, v1068);
LABEL_1731:
                                                                                    v1322 = lpMem;
                                                                                    if ( lpMem )
                                                                                    {
                                                                                      v1323 = GetProcessHeap();
                                                                                      HeapFree(v1323, 0, v1322);
                                                                                    }
                                                                                    v1061 = v1413;
                                                                                    if ( v1058 )
                                                                                    {
LABEL_1737:
                                                                                      v1324 = GetProcessHeap();
                                                                                      HeapFree(v1324, 0, v1058);
                                                                                    }
                                                                                    if ( v1061 )
                                                                                    {
                                                                                      v1325 = GetProcessHeap();
                                                                                      HeapFree(v1325, 0, v1061);
                                                                                    }
                                                                                  }
                                                                                  v2 = v1330;
LABEL_1741:
                                                                                  v1326 = v1329;
                                                                                  v1434 = (DWORD *)v1438;
                                                                                  *(_QWORD *)&v1431[1] = 0;
LABEL_1744:
                                                                                  while ( _InterlockedCompareExchange(
                                                                                            &g_WarbirdSecureFunctionsLock,
                                                                                            1,
                                                                                            0) )
                                                                                    ;
                                                                                  v1327 = g_WarbirdSecureFunctionsRefCount;
                                                                                  if ( g_WarbirdSecureFunctionsRefCount > 0 )
                                                                                  {
                                                                                    --g_WarbirdSecureFunctionsRefCount;
                                                                                    if ( v1327 == 1 )
                                                                                    {
                                                                                      if ( WARBIRD::g_arModuleInfo )
                                                                                        FreeLibrary(WARBIRD::g_arModuleInfo);
                                                                                      if ( *((_QWORD *)&xmmword_1800AD870
                                                                                           + 1) )
                                                                                        FreeLibrary(*((HMODULE *)&xmmword_1800AD870 + 1));
                                                                                      if ( hLibModule )
                                                                                        FreeLibrary(hLibModule);
                                                                                      if ( *((_QWORD *)&xmmword_1800AD8A0
                                                                                           + 1) )
                                                                                        FreeLibrary(*((HMODULE *)&xmmword_1800AD8A0 + 1));
                                                                                      qword_1800AC100 = 0;
                                                                                      WARBIRD::g_FuncAddress = (void * near *)WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC038[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC040[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC048[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC050[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC058[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC060[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC068 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC070[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC078 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC080[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC088[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC090[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC098[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0A0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0A8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0B0 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC0B8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0C0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0C8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0D0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0D8[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0E0 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0E8 = WARBIRD_DELAY_LOAD::MulDiv;
                                                                                      off_1800AC0F0[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC0F8 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC108 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC110[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC118[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC120[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC128[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC130 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC138 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC140[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC148[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC150[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      *(_OWORD *)&WARBIRD::g_arModuleInfo = 0;
                                                                                      xmmword_1800AD870 = 0;
                                                                                      xmmword_1800AD880 = 0;
                                                                                      *(_OWORD *)&hLibModule = 0;
                                                                                      xmmword_1800AD8A0 = 0;
                                                                                      xmmword_1800AD8B0 = 0;
                                                                                      off_1800AC158[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC160[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC168 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC170[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC178[0] = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC180 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC188 = CIVIAudioFilter::IsDirty;
                                                                                      off_1800AC190[0] = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                      off_1800AC198 = WARBIRD_DELAY_LOAD::GetSysColor;
                                                                                    }
                                                                                  }
                                                                                  _InterlockedExchange(
                                                                                    &g_WarbirdSecureFunctionsLock,
                                                                                    0);
                                                                                  SP_HLOCAL<unsigned char>::~SP_HLOCAL<unsigned char>(&v1431[1]);
                                                                                  if ( v2 >= 0 )
                                                                                  {
                                                                                    if ( v1326 == 4 )
                                                                                    {
                                                                                      v2 = 0;
                                                                                      *v1449 = *v1434;
                                                                                      goto LABEL_1769;
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    switch ( v2 )
                                                                                    {
                                                                                      case -805306316:
                                                                                        v2 = -1073418222;
                                                                                        goto LABEL_1769;
                                                                                      case -805306139:
                                                                                      case -1073425151:
                                                                                        v2 = -1073418201;
                                                                                        goto LABEL_1769;
                                                                                      case -805306306:
                                                                                        v2 = -1073418200;
                                                                                        goto LABEL_1769;
                                                                                    }
                                                                                    if ( v2 != -2147024774 )
                                                                                      goto LABEL_1769;
                                                                                  }
                                                                                  v2 = -1073418210;
                                                                                  goto LABEL_1769;
                                                                                }
                                                                              }
LABEL_1225:
                                                                              GetLastError();
                                                                              goto LABEL_1343;
                                                                            }
                                                                            if ( HIDWORD(v1455[0])
                                                                              || (v913 = -64, v811 == 1) )
                                                                            {
                                                                              v913 = -1;
                                                                            }
                                                                            BYTE2(v1398) = v913;
                                                                            LOWORD(v1398) = 0;
                                                                            HIBYTE(v1398) = 1;
                                                                            v1403 = (void *)((__int64 (__fastcall *)(LPVOID))off_1800AC040[0])(v851);
                                                                            if ( !v1403 )
                                                                              goto LABEL_1225;
                                                                            v914 = HIDWORD(v1458);
                                                                            if ( v811 == 1 )
                                                                            {
                                                                              v915 = 0;
                                                                              LODWORD(v1415) = 0;
                                                                              v916 = DWORD1(v1460) - HIDWORD(v1459);
                                                                              if ( DWORD1(v1460) - HIDWORD(v1459) <= DWORD1(v1459) - HIDWORD(v1458) )
                                                                                v916 = DWORD1(v1459) - HIDWORD(v1458);
                                                                              LODWORD(v1413) = v916;
                                                                              LODWORD(v1406) = DWORD2(v1460) - v1459;
                                                                              if ( LODWORD(v1455[0]) )
                                                                              {
                                                                                v914 = v916
                                                                                     + HIDWORD(v1458)
                                                                                     - DWORD1(v1459);
                                                                                v917 = v916
                                                                                     + HIDWORD(v1459)
                                                                                     - DWORD1(v1460);
                                                                              }
                                                                              else
                                                                              {
                                                                                v914 = 0;
                                                                                v917 = 0;
                                                                              }
                                                                              v918 = v914
                                                                                   + DWORD1(v1459)
                                                                                   - HIDWORD(v1458);
                                                                              v1341 = v917
                                                                                    + DWORD1(v1460)
                                                                                    - HIDWORD(v1459);
                                                                              v919 = DWORD2(v1459) - v1459;
                                                                              v1419 = v917;
                                                                              v1399 = v1460 - v1459;
                                                                              v1394 = DWORD2(v1460) - v1459;
                                                                            }
                                                                            else
                                                                            {
                                                                              v915 = v1459;
                                                                              v918 = DWORD1(v1459);
                                                                              v919 = DWORD2(v1459);
                                                                              LODWORD(v1406) = HIDWORD(v1425);
                                                                              LODWORD(v1413) = DWORD2(v1425);
                                                                              v1419 = HIDWORD(v1459);
                                                                              v1399 = v1460;
                                                                              v1394 = DWORD2(v1460);
                                                                              LODWORD(v1415) = v1459;
                                                                              v1341 = DWORD1(v1460);
                                                                            }
                                                                            v1541[1] = (_DWORD)v1413;
                                                                            v1541[2] = -(int)v1406;
                                                                            v1453 = 0;
                                                                            memset(&v1541[4], 0, 28);
                                                                            v1541[0] = 40;
                                                                            v1541[3] = 2097153;
                                                                            v920 = ((__int64 (__fastcall *)(void *, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800AC048[0])(
                                                                                     v1403,
                                                                                     v1541,
                                                                                     0,
                                                                                     &v1453,
                                                                                     0,
                                                                                     0);
                                                                            v1411 = (unsigned int *)v920;
                                                                            if ( !v920 )
                                                                            {
                                                                              GetLastError();
                                                                              v912 = v1403;
                                                                              goto LABEL_1342;
                                                                            }
                                                                            off_1800AC0A8(
                                                                              (WARBIRD_DELAY_LOAD *)v1403,
                                                                              v920);
                                                                            if ( v811 == 1 && psz )
                                                                            {
                                                                              v1538 = 0;
                                                                              v1539 = (int)v1413;
                                                                              v1540 = v1406;
                                                                              off_1800AC118[0](
                                                                                (WARBIRD_DELAY_LOAD *)v1403,
                                                                                (int)&v1538);
                                                                            }
                                                                            v1485 = 0;
                                                                            v1517 = 0;
                                                                            v1478 = 0;
                                                                            v1510 = 0;
                                                                            v1412 = v1455[1];
                                                                            memset(v1548, 0, 28);
                                                                            v1479 = 0;
                                                                            v1480 = 0;
                                                                            v1481 = 0;
                                                                            v1482 = 0;
                                                                            v1483 = 0;
                                                                            v1484 = 0;
                                                                            v1511 = 0;
                                                                            v1512 = 0;
                                                                            v1513 = 0;
                                                                            v1514 = 0;
                                                                            v1515 = 0;
                                                                            v1516 = 0;
                                                                            v1547 = 0;
                                                                            v1537 = 0;
                                                                            if ( !v1455[1] )
                                                                              goto LABEL_1338;
                                                                            LODWORD(Src) = HIDWORD(v1455[0]);
                                                                            v1365 = (unsigned __int16 *)v1457;
                                                                            v921 = ((__int64 (__fastcall *)(void *, __int64))off_1800AC080[0])(
                                                                                     v1403,
                                                                                     7);
                                                                            if ( !v921
                                                                              || (!((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800AC098[0])(
                                                                                     v921,
                                                                                     104,
                                                                                     &v1478)
                                                                                ? (v922 = 0, v1402 = 0, v1407 = 0)
                                                                                : (v1402 = *(_QWORD *)((char *)&v1480 + 4),
                                                                                   v1407 = v1479,
                                                                                   v922 = DWORD1(v1479)),
                                                                                  LODWORD(v1416) = v922,
                                                                                  (lpMem = (LPVOID)((__int64 (__fastcall *)(void *))off_1800AC040[0])(v1403)) == 0) )
                                                                            {
                                                                              GetLastError();
                                                                              goto LABEL_1338;
                                                                            }
                                                                            LODWORD(v1547) = 40;
                                                                            v1447 = 0;
                                                                            DWORD2(v1547) = v915 - v919;
                                                                            memset(v1548, 0, 28);
                                                                            LODWORD(v1409) = v918 - v914;
                                                                            DWORD1(v1547) = v918 - v914;
                                                                            HIDWORD(v1547) = 2097153;
                                                                            v923 = ((__int64 (__fastcall *)(LPVOID, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800AC048[0])(
                                                                                     lpMem,
                                                                                     &v1547,
                                                                                     0,
                                                                                     &v1447,
                                                                                     0,
                                                                                     0);
                                                                            v1410 = v923;
                                                                            if ( v923 )
                                                                            {
                                                                              v925 = 0;
                                                                              if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_1800AC098[0])(
                                                                                     v923,
                                                                                     104,
                                                                                     &v1510) )
                                                                              {
                                                                                v1404 = *(_QWORD *)((char *)&v1512 + 4);
                                                                              }
                                                                              else
                                                                              {
                                                                                v1404 = 0;
                                                                              }
                                                                              HIDWORD(v1537) = v919 - v915;
                                                                              v926 = lpMem;
                                                                              DWORD2(v1537) = (_DWORD)v1409;
                                                                              off_1800AC0A8(
                                                                                (WARBIRD_DELAY_LOAD *)lpMem,
                                                                                v1410);
                                                                              ((void (__fastcall *)(LPVOID, __int64))off_1800AC0B0)(
                                                                                v926,
                                                                                1);
                                                                              v927 = ((__int64 (__fastcall *)(LPVOID, unsigned __int16 *))off_1800AC0A8)(
                                                                                       v926,
                                                                                       v1365);
                                                                              v928 = off_1800AC118[0];
                                                                              pcchLength = v927;
                                                                              v929 = ((__int64 (__fastcall *)(_QWORD))off_1800AC0A0[0])(0);
                                                                              ((void (__fastcall *)(LPVOID, __int128 *, __int64))v928)(
                                                                                v926,
                                                                                &v1537,
                                                                                v929);
                                                                              ((void (__fastcall *)(LPVOID, void *, __int64, __int128 *, _DWORD, _QWORD))off_1800AC108)(
                                                                                v926,
                                                                                v1412,
                                                                                0xFFFFFFFFLL,
                                                                                &v1537,
                                                                                (_DWORD)v1422,
                                                                                0);
                                                                              if ( v811 == 1 )
                                                                              {
                                                                                if ( (_DWORD)Src )
                                                                                  v930 = ((__int64 (__fastcall *)(__int64))off_1800AC148[0])(8);
                                                                                else
                                                                                  v930 = 0xFFFFFF;
                                                                              }
                                                                              else
                                                                              {
                                                                                v930 = -5723992;
                                                                              }
                                                                              v931 = (int)v1415;
                                                                              v932 = -v914;
                                                                              if ( v914 >= 0 )
                                                                                v932 = 0;
                                                                              v933 = 0;
                                                                              if ( v914 >= 0 )
                                                                                v933 = v914;
                                                                              if ( (int)v1415 >= 0 )
                                                                              {
                                                                                v934 = 0;
                                                                              }
                                                                              else
                                                                              {
                                                                                v934 = -(int)v1415;
                                                                                v931 = 0;
                                                                              }
                                                                              v935 = v1407;
                                                                              v936 = DWORD2(v1537) - v932;
                                                                              if ( DWORD2(v1537) - v932 >= v1407 - v933 )
                                                                                v936 = v1407 - v933;
                                                                              v937 = HIDWORD(v1537) - v934;
                                                                              if ( HIDWORD(v1537) - v934 >= (int)v1416 - v931 )
                                                                                v937 = v1416 - v931;
                                                                              v1407 = v937;
                                                                              if ( v936 <= 0 || v937 <= 0 )
                                                                              {
                                                                                v944 = v1329;
                                                                              }
                                                                              else
                                                                              {
                                                                                LODWORD(v1416) = 0;
                                                                                v938 = v1404
                                                                                     + 4
                                                                                     * (v932
                                                                                      + (__int64)(DWORD2(v1537) * v934));
                                                                                v1404 = v938;
                                                                                v939 = (char *)(v1402
                                                                                              + 4
                                                                                              * (v933
                                                                                               + (__int64)((int)v935 * v931)));
                                                                                LODWORD(Src) = v930 >> 8;
                                                                                LODWORD(v1409) = HIWORD(v930);
                                                                                v1366 = (unsigned __int16 *)(4LL * SDWORD2(v1537));
                                                                                v1412 = (void *)(4 * v935);
                                                                                v1402 = (SIZE_T)v939;
                                                                                do
                                                                                {
                                                                                  v940 = (unsigned __int8 *)v938;
                                                                                  v941 = v939;
                                                                                  for ( i8 = 0; i8 < v936; ++i8 )
                                                                                  {
                                                                                    if ( (unsigned __int8)((*v940 + v940[2] + 2 * (unsigned int)v940[1]) >> 2) != 0xFF )
                                                                                    {
                                                                                      v943 = (unsigned __int8)~((*v940 + v940[2] + 2 * (unsigned int)v940[1]) >> 2);
                                                                                      v941[2] -= ~((*v940
                                                                                                  + v940[2]
                                                                                                  + 2 * (unsigned int)v940[1]) >> 2)
                                                                                               * (v930 - v941[2]);
                                                                                      v941[1] -= v943
                                                                                               * (BYTE1(v930) - v941[1]);
                                                                                      *v941 -= v943
                                                                                             * (BYTE2(v930) - *v941);
                                                                                      v941[3] += v943
                                                                                               * (255
                                                                                                - (unsigned __int8)v941[3])
                                                                                               / 255;
                                                                                    }
                                                                                    v940 += 4;
                                                                                    v941 += 4;
                                                                                  }
                                                                                  v938 = (SIZE_T)v1366 + v1404;
                                                                                  v939 = (char *)v1412 + v1402;
                                                                                  v1404 += (SIZE_T)v1366;
                                                                                  v1402 += (SIZE_T)v1412;
                                                                                  LODWORD(v1416) = v1416 + 1;
                                                                                }
                                                                                while ( (int)v1416 < v1407 );
                                                                                v944 = v1329;
                                                                              }
                                                                              ((void (__fastcall *)(SIZE_T))off_1800AC068)(v1410);
                                                                              if ( !pcchLength )
                                                                              {
                                                                                v1329 = v944;
                                                                                goto LABEL_1283;
                                                                              }
                                                                              v945 = lpMem;
                                                                              off_1800AC0A8(
                                                                                (WARBIRD_DELAY_LOAD *)lpMem,
                                                                                pcchLength);
                                                                            }
                                                                            else
                                                                            {
                                                                              v924 = GetLastError();
                                                                              v925 = v924;
                                                                              if ( v924 > 0 )
                                                                                v925 = (unsigned __int16)v924
                                                                                     | 0x80070000;
                                                                              if ( v925 >= 0 )
                                                                                v925 = -2147467259;
LABEL_1283:
                                                                              v945 = lpMem;
                                                                            }
                                                                            ((void (__fastcall *)(LPVOID))off_1800AC060[0])(v945);
                                                                            if ( v925 < 0 )
                                                                              goto LABEL_1338;
                                                                            v1477 = 0;
                                                                            v1525 = 0;
                                                                            v1470 = 0;
                                                                            v1518 = 0;
                                                                            v1412 = v1456[0];
                                                                            memset(v1550, 0, 28);
                                                                            v1471 = 0;
                                                                            v1472 = 0;
                                                                            v1473 = 0;
                                                                            v1474 = 0;
                                                                            v1475 = 0;
                                                                            v1476 = 0;
                                                                            v1519 = 0;
                                                                            v1520 = 0;
                                                                            v1521 = 0;
                                                                            v1522 = 0;
                                                                            v1523 = 0;
                                                                            v1524 = 0;
                                                                            v1549 = 0;
                                                                            v1536 = 0;
                                                                            if ( v1456[0] )
                                                                            {
                                                                              v912 = v1403;
                                                                              LODWORD(Src) = HIDWORD(v1455[0]);
                                                                              v1367 = (unsigned __int16 *)*((_QWORD *)&v1457 + 1);
                                                                              v946 = ((__int64 (__fastcall *)(void *, __int64))off_1800AC080[0])(
                                                                                       v1403,
                                                                                       7);
                                                                              if ( v946 )
                                                                              {
                                                                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800AC098[0])(
                                                                                       v946,
                                                                                       104,
                                                                                       &v1470) )
                                                                                {
                                                                                  v947 = v1471;
                                                                                  v1402 = *(_QWORD *)((char *)&v1472 + 4);
                                                                                  LODWORD(v1416) = DWORD1(v1471);
                                                                                }
                                                                                else
                                                                                {
                                                                                  v1402 = 0;
                                                                                  v947 = 0;
                                                                                  LODWORD(v1416) = 0;
                                                                                }
                                                                                v1407 = v947;
                                                                                v948 = ((__int64 (__fastcall *)(void *))off_1800AC040[0])(v912);
                                                                                pcchLength = v948;
                                                                                v949 = (WARBIRD_DELAY_LOAD *)v948;
                                                                                if ( v948 )
                                                                                {
                                                                                  v1342 = v1341 - v1419;
                                                                                  DWORD1(v1549) = v1342;
                                                                                  v1448 = 0;
                                                                                  v950 = v1399;
                                                                                  DWORD2(v1549) = v1399 - v1394;
                                                                                  memset(v1550, 0, 28);
                                                                                  LODWORD(v1549) = 40;
                                                                                  HIDWORD(v1549) = 2097153;
                                                                                  v951 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800AC048[0])(
                                                                                           v948,
                                                                                           &v1549,
                                                                                           0,
                                                                                           &v1448,
                                                                                           0,
                                                                                           0);
                                                                                  v1410 = v951;
                                                                                  if ( v951 )
                                                                                  {
                                                                                    if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_1800AC098[0])(
                                                                                           v951,
                                                                                           104,
                                                                                           &v1518) )
                                                                                    {
                                                                                      v1404 = *(_QWORD *)((char *)&v1520 + 4);
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v1404 = 0;
                                                                                    }
                                                                                    v953 = 0;
                                                                                    HIDWORD(v1536) = v1394 - v950;
                                                                                    DWORD2(v1536) = v1342;
                                                                                    off_1800AC0A8(v949, v1410);
                                                                                    ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int64))off_1800AC0B0)(
                                                                                      v949,
                                                                                      1);
                                                                                    v954 = ((__int64 (__fastcall *)(WARBIRD_DELAY_LOAD *, unsigned __int16 *))off_1800AC0A8)(
                                                                                             v949,
                                                                                             v1367);
                                                                                    v955 = off_1800AC118[0];
                                                                                    v1417 = v954;
                                                                                    v956 = ((__int64 (__fastcall *)(_QWORD))off_1800AC0A0[0])(0);
                                                                                    ((void (__fastcall *)(size_t, __int128 *, __int64))v955)(
                                                                                      pcchLength,
                                                                                      &v1536,
                                                                                      v956);
                                                                                    v949 = (WARBIRD_DELAY_LOAD *)pcchLength;
                                                                                    ((void (__fastcall *)(size_t, void *, __int64, __int128 *, _DWORD, _QWORD))off_1800AC108)(
                                                                                      pcchLength,
                                                                                      v1412,
                                                                                      0xFFFFFFFFLL,
                                                                                      &v1536,
                                                                                      (_DWORD)v1422,
                                                                                      0);
                                                                                    if ( v811 == 1 )
                                                                                    {
                                                                                      if ( (_DWORD)Src )
                                                                                      {
                                                                                        v957 = ((__int64 (__fastcall *)(__int64))off_1800AC148[0])(8);
                                                                                        v1400 = v957;
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v957 = 0xFFFFFF;
                                                                                      }
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v957 = -5723992;
                                                                                      v1400 = -5723992;
                                                                                    }
                                                                                    v958 = -v1419;
                                                                                    if ( v1419 >= 0 )
                                                                                      v958 = 0;
                                                                                    v959 = 0;
                                                                                    if ( v1419 >= 0 )
                                                                                      v959 = v1419;
                                                                                    if ( v950 >= 0 )
                                                                                    {
                                                                                      v960 = 0;
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v960 = -v950;
                                                                                      v950 = 0;
                                                                                    }
                                                                                    v961 = v947 - v959;
                                                                                    v962 = DWORD2(v1536) - v958;
                                                                                    if ( DWORD2(v1536) - v958 >= v961 )
                                                                                      v962 = v961;
                                                                                    v963 = HIDWORD(v1536) - v960;
                                                                                    if ( HIDWORD(v1536) - v960 >= (int)v1416 - v950 )
                                                                                      v963 = v1416 - v950;
                                                                                    LODWORD(v1409) = v963;
                                                                                    if ( v962 <= 0 || v963 <= 0 )
                                                                                    {
                                                                                      v973 = v1329;
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v1399 = 0;
                                                                                      v964 = v1404
                                                                                           + 4
                                                                                           * (v958
                                                                                            + (__int64)(DWORD2(v1536) * v960));
                                                                                      v965 = v959
                                                                                           + (__int64)(v1407 * v950);
                                                                                      v966 = v957 >> 8;
                                                                                      v1404 = v964;
                                                                                      v967 = (char *)(v1402 + 4 * v965);
                                                                                      LODWORD(Src) = HIWORD(v957);
                                                                                      v968 = HIWORD(v957);
                                                                                      v1368 = (unsigned __int16 *)(4LL * SDWORD2(v1536));
                                                                                      v1412 = (void *)(4LL * v1407);
                                                                                      v1402 = (SIZE_T)v967;
                                                                                      do
                                                                                      {
                                                                                        v969 = (unsigned __int8 *)v964;
                                                                                        v970 = v967;
                                                                                        for ( i9 = 0; i9 < v962; ++i9 )
                                                                                        {
                                                                                          if ( (unsigned __int8)((*v969 + v969[2] + 2 * (unsigned int)v969[1]) >> 2) != 0xFF )
                                                                                          {
                                                                                            v972 = (unsigned __int8)~((*v969 + v969[2] + 2 * (unsigned int)v969[1]) >> 2);
                                                                                            v970[2] -= ~((*v969 + v969[2] + 2 * (unsigned int)v969[1]) >> 2) * (v1400 - v970[2]);
                                                                                            v970[1] -= v972 * (v966 - v970[1]);
                                                                                            *v970 -= v972 * (v968 - *v970);
                                                                                            v970[3] += v972 * (255 - (unsigned __int8)v970[3]) / 255;
                                                                                          }
                                                                                          v969 += 4;
                                                                                          v970 += 4;
                                                                                        }
                                                                                        v964 = (SIZE_T)v1368 + v1404;
                                                                                        v967 = (char *)v1412 + v1402;
                                                                                        v1404 += (SIZE_T)v1368;
                                                                                        v1402 += (SIZE_T)v1412;
                                                                                        ++v1399;
                                                                                      }
                                                                                      while ( (int)v1399 < (int)v1409 );
                                                                                      v949 = (WARBIRD_DELAY_LOAD *)pcchLength;
                                                                                      v973 = v1329;
                                                                                    }
                                                                                    ((void (__fastcall *)(SIZE_T))off_1800AC068)(v1410);
                                                                                    if ( v1417 )
                                                                                      off_1800AC0A8(v949, v1417);
                                                                                    else
                                                                                      v1329 = v973;
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    v952 = GetLastError();
                                                                                    v953 = v952;
                                                                                    if ( v952 > 0 )
                                                                                      v953 = (unsigned __int16)v952
                                                                                           | 0x80070000;
                                                                                    if ( v953 >= 0 )
                                                                                      v953 = -2147467259;
                                                                                  }
                                                                                  ((void (__fastcall *)(WARBIRD_DELAY_LOAD *))off_1800AC060[0])(v949);
                                                                                  if ( v953 >= 0 )
                                                                                  {
                                                                                    v912 = v1403;
                                                                                    v910 = v1418;
                                                                                    if ( v811 == 1 )
                                                                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, void *, _DWORD, _DWORD, int))WARBIRD::g_FuncAddress)(
                                                                                        v1418,
                                                                                        HIDWORD(v1458),
                                                                                        (unsigned int)v1459,
                                                                                        (unsigned int)v1413,
                                                                                        v1406,
                                                                                        v1403,
                                                                                        0,
                                                                                        0,
                                                                                        13369376);
                                                                                    else
                                                                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, void *, _DWORD, _DWORD, _DWORD, _DWORD, unsigned int))off_1800AC070[0])(
                                                                                        v1418,
                                                                                        (unsigned int)v1425,
                                                                                        DWORD1(v1425),
                                                                                        (unsigned int)v1413,
                                                                                        v1406,
                                                                                        v1403,
                                                                                        0,
                                                                                        0,
                                                                                        (_DWORD)v1413,
                                                                                        v1406,
                                                                                        v1398);
                                                                                    v911 = v1411;
LABEL_1335:
                                                                                    ((void (__fastcall *)(LPVOID, _QWORD))off_1800AC0B0)(
                                                                                      v910,
                                                                                      (unsigned int)Size);
                                                                                    if ( v911 )
LABEL_1340:
                                                                                      ((void (__fastcall *)(unsigned int *))off_1800AC068)(v911);
                                                                                    if ( !v912 )
                                                                                      goto LABEL_1343;
LABEL_1342:
                                                                                    ((void (__fastcall *)(void *))off_1800AC060[0])(v912);
                                                                                    goto LABEL_1343;
                                                                                  }
                                                                                  goto LABEL_1338;
                                                                                }
                                                                              }
                                                                              GetLastError();
                                                                            }
                                                                            else
                                                                            {
LABEL_1338:
                                                                              v912 = v1403;
                                                                            }
                                                                            v911 = v1411;
                                                                            goto LABEL_1340;
                                                                          }
                                                                          v843 = HIDWORD(v1425);
                                                                          v824 = DWORD2(v1425);
                                                                        }
                                                                        v844 = v800 - 1;
                                                                        if ( !v844 )
                                                                          goto LABEL_1101;
                                                                        v845 = v844 - 1;
                                                                        if ( v845 )
                                                                        {
                                                                          if ( v845 == 1 )
                                                                          {
                                                                            v1555 = 0;
                                                                            v1553 = 0;
                                                                            v1554 = 0;
                                                                            v846 = ((__int64 (__fastcall *)(_QWORD, __int64))off_1800AC178[0])(
                                                                                     0,
                                                                                     1);
                                                                            LODWORD(v1553) = 40;
                                                                            if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int128 *))off_1800AC138)(
                                                                                                 v846,
                                                                                                 &v1553) )
                                                                            {
                                                                              ((void (__fastcall *)(_QWORD, char *))off_1800AC170[0])(
                                                                                0,
                                                                                (char *)&v1554 + 4);
                                                                              ((void (__fastcall *)(_QWORD, char *))off_1800AC170[0])(
                                                                                0,
                                                                                (char *)&v1554 + 12);
                                                                              LODWORD(v1425) = (int)(50 * (HIDWORD(v1554) - v824))
                                                                                             / 100;
                                                                              DWORD1(v1425) = 50
                                                                                            * ((int)v1555 - v843)
                                                                                            / 100;
                                                                              v556 = 0;
                                                                              goto LABEL_1006;
                                                                            }
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          v847 = (int)v1455[0];
                                                                          v1544 = 0;
                                                                          v1542 = 0;
                                                                          v1543 = 0;
                                                                          v848 = ((__int64 (__fastcall *)(_QWORD, __int64))off_1800AC178[0])(
                                                                                   0,
                                                                                   1);
                                                                          LODWORD(v1542) = 40;
                                                                          if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int128 *))off_1800AC138)(
                                                                                               v848,
                                                                                               &v1542) )
                                                                          {
                                                                            ((void (__fastcall *)(_QWORD, char *))off_1800AC170[0])(
                                                                              0,
                                                                              (char *)&v1543 + 4);
                                                                            ((void (__fastcall *)(_QWORD, char *))off_1800AC170[0])(
                                                                              0,
                                                                              (char *)&v1543 + 12);
                                                                            if ( v847 )
                                                                              v849 = DWORD1(v1543)
                                                                                   + 5 * HIDWORD(v1543) / 100;
                                                                            else
                                                                              v849 = (int)(95 * (HIDWORD(v1543) - v824))
                                                                                   / 100;
                                                                            LODWORD(v1425) = v849;
                                                                            DWORD1(v1425) = 95
                                                                                          * ((int)v1544 - v843)
                                                                                          / 100;
                                                                            v556 = 0;
                                                                            goto LABEL_1006;
                                                                          }
                                                                        }
LABEL_1102:
                                                                        v556 = 0;
                                                                        goto LABEL_1006;
                                                                      }
                                                                      v801 = 15;
                                                                    }
                                                                    LODWORD(v1406) = 11;
                                                                    goto LABEL_994;
                                                                  }
                                                                  continue;
                                                                }
LABEL_808:
                                                                v733 = -1;
                                                                do
                                                                  v55 = *(_BYTE *)(v732 + v733++ + 1) == 0;
                                                                while ( !v55 );
                                                                v734 = v732 + v733 + 1;
                                                                if ( v1388 != 34 )
                                                                  goto LABEL_928;
                                                                *((_QWORD *)v1432 + v662) = v734;
                                                                v735 = -1;
                                                                do
                                                                  v55 = *(_BYTE *)(v734 + v735++ + 1) == 0;
                                                                while ( !v55 );
                                                                v736 = v734 + v735 + 1;
                                                                goto LABEL_814;
                                                              }
LABEL_802:
                                                              v729 = -1;
                                                              do
                                                                v55 = *(_BYTE *)(v728 + v729++ + 1) == 0;
                                                              while ( !v55 );
                                                              v730 = v728 + v729 + 1;
                                                              if ( v1388 != 32 )
                                                                goto LABEL_922;
                                                              *((_QWORD *)v1432 + v662) = v730;
                                                              v731 = -1;
                                                              do
                                                                v55 = *(_BYTE *)(v730 + v731++ + 1) == 0;
                                                              while ( !v55 );
                                                              v732 = v730 + v731 + 1;
                                                              goto LABEL_808;
                                                            }
LABEL_796:
                                                            v725 = -1;
                                                            do
                                                              v55 = *(_BYTE *)(v724 + v725++ + 1) == 0;
                                                            while ( !v55 );
                                                            v726 = v724 + v725 + 1;
                                                            if ( v1388 != 30 )
                                                              goto LABEL_916;
                                                            *((_QWORD *)v1432 + v662) = v726;
                                                            v727 = -1;
                                                            do
                                                              v55 = *(_BYTE *)(v726 + v727++ + 1) == 0;
                                                            while ( !v55 );
                                                            v728 = v726 + v727 + 1;
                                                            goto LABEL_802;
                                                          }
LABEL_790:
                                                          v721 = -1;
                                                          do
                                                            v55 = *(_BYTE *)(v720 + v721++ + 1) == 0;
                                                          while ( !v55 );
                                                          v722 = v720 + v721 + 1;
                                                          if ( v1388 != 28 )
                                                            goto LABEL_910;
                                                          *((_QWORD *)v1432 + v662) = v722;
                                                          v723 = -1;
                                                          do
                                                            v55 = *(_BYTE *)(v722 + v723++ + 1) == 0;
                                                          while ( !v55 );
                                                          v724 = v722 + v723 + 1;
                                                          goto LABEL_796;
                                                        }
LABEL_784:
                                                        v717 = -1;
                                                        do
                                                          v55 = *(_BYTE *)(v716 + v717++ + 1) == 0;
                                                        while ( !v55 );
                                                        v718 = v716 + v717 + 1;
                                                        if ( v1388 != 26 )
                                                          goto LABEL_904;
                                                        *((_QWORD *)v1432 + v662) = v718;
                                                        v719 = -1;
                                                        do
                                                          v55 = *(_BYTE *)(v718 + v719++ + 1) == 0;
                                                        while ( !v55 );
                                                        v720 = v718 + v719 + 1;
                                                        goto LABEL_790;
                                                      }
LABEL_778:
                                                      v713 = -1;
                                                      do
                                                        v55 = *(_BYTE *)(v712 + v713++ + 1) == 0;
                                                      while ( !v55 );
                                                      v714 = v712 + v713 + 1;
                                                      if ( v1388 != 24 )
                                                        goto LABEL_898;
                                                      *((_QWORD *)v1432 + v662) = v714;
                                                      v715 = -1;
                                                      do
                                                        v55 = *(_BYTE *)(v714 + v715++ + 1) == 0;
                                                      while ( !v55 );
                                                      v716 = v714 + v715 + 1;
                                                      goto LABEL_784;
                                                    }
LABEL_772:
                                                    v709 = -1;
                                                    do
                                                      v55 = *(_BYTE *)(v708 + v709++ + 1) == 0;
                                                    while ( !v55 );
                                                    v710 = v708 + v709 + 1;
                                                    if ( v1388 != 22 )
                                                      goto LABEL_892;
                                                    *((_QWORD *)v1432 + v662) = v710;
                                                    v711 = -1;
                                                    do
                                                      v55 = *(_BYTE *)(v710 + v711++ + 1) == 0;
                                                    while ( !v55 );
                                                    v712 = v710 + v711 + 1;
                                                    goto LABEL_778;
                                                  }
LABEL_766:
                                                  v705 = -1;
                                                  do
                                                    v55 = *(_BYTE *)(v704 + v705++ + 1) == 0;
                                                  while ( !v55 );
                                                  v706 = v704 + v705 + 1;
                                                  if ( v1388 != 20 )
                                                    goto LABEL_886;
                                                  *((_QWORD *)v1432 + v662) = v706;
                                                  v707 = -1;
                                                  do
                                                    v55 = *(_BYTE *)(v706 + v707++ + 1) == 0;
                                                  while ( !v55 );
                                                  v708 = v706 + v707 + 1;
                                                  goto LABEL_772;
                                                }
LABEL_760:
                                                v701 = -1;
                                                do
                                                  v55 = *(_BYTE *)(v700 + v701++ + 1) == 0;
                                                while ( !v55 );
                                                v702 = v700 + v701 + 1;
                                                if ( v1388 != 18 )
                                                  goto LABEL_880;
                                                *((_QWORD *)v1432 + v662) = v702;
                                                v703 = -1;
                                                do
                                                  v55 = *(_BYTE *)(v702 + v703++ + 1) == 0;
                                                while ( !v55 );
                                                v704 = v702 + v703 + 1;
                                                goto LABEL_766;
                                              }
LABEL_754:
                                              v697 = -1;
                                              do
                                                v55 = *(_BYTE *)(v696 + v697++ + 1) == 0;
                                              while ( !v55 );
                                              v698 = v696 + v697 + 1;
                                              if ( v1388 != 16 )
                                                goto LABEL_874;
                                              *((_QWORD *)v1432 + v662) = v698;
                                              v699 = -1;
                                              do
                                                v55 = *(_BYTE *)(v698 + v699++ + 1) == 0;
                                              while ( !v55 );
                                              v700 = v698 + v699 + 1;
                                              goto LABEL_760;
                                            }
LABEL_748:
                                            v693 = -1;
                                            do
                                              v55 = *(_BYTE *)(v692 + v693++ + 1) == 0;
                                            while ( !v55 );
                                            v694 = v692 + v693 + 1;
                                            if ( v1388 != 14 )
                                              goto LABEL_868;
                                            *((_QWORD *)v1432 + v662) = v694;
                                            v695 = -1;
                                            do
                                              v55 = *(_BYTE *)(v694 + v695++ + 1) == 0;
                                            while ( !v55 );
                                            v696 = v694 + v695 + 1;
                                            goto LABEL_754;
                                          }
LABEL_742:
                                          v689 = -1;
                                          do
                                            v55 = *(_BYTE *)(v688 + v689++ + 1) == 0;
                                          while ( !v55 );
                                          v690 = v688 + v689 + 1;
                                          if ( v1388 != 12 )
                                            goto LABEL_862;
                                          *((_QWORD *)v1432 + v662) = v690;
                                          v691 = -1;
                                          do
                                            v55 = *(_BYTE *)(v690 + v691++ + 1) == 0;
                                          while ( !v55 );
                                          v692 = v690 + v691 + 1;
                                          goto LABEL_748;
                                        }
LABEL_736:
                                        v685 = -1;
                                        do
                                          v55 = *(_BYTE *)(v684 + v685++ + 1) == 0;
                                        while ( !v55 );
                                        v686 = v684 + v685 + 1;
                                        if ( v1388 != 10 )
                                          goto LABEL_856;
                                        *((_QWORD *)v1432 + v662) = v686;
                                        v687 = -1;
                                        do
                                          v55 = *(_BYTE *)(v686 + v687++ + 1) == 0;
                                        while ( !v55 );
                                        v688 = v686 + v687 + 1;
                                        goto LABEL_742;
                                      }
LABEL_730:
                                      v681 = -1;
                                      do
                                        ++v681;
                                      while ( *(_BYTE *)(v680 + v681) );
                                      v682 = v681 + v680 + 1;
                                      if ( v1388 != 8 )
                                        goto LABEL_850;
                                      *((_QWORD *)v1432 + v662) = v682;
                                      v683 = -1;
                                      do
                                        v55 = *(_BYTE *)(v682 + v683++ + 1) == 0;
                                      while ( !v55 );
                                      v684 = v682 + v683 + 1;
                                      goto LABEL_736;
                                    }
                                  }
                                  else
                                  {
LABEL_714:
                                    v666 = 8 * v664;
                                    v667 = -1;
                                    do
                                      ++v667;
                                    while ( v665[v667] );
                                    v668 = (__int64)&v665[v667 + 1];
                                    if ( v1388 != 2 )
                                      goto LABEL_826;
                                    *(_QWORD *)((char *)v1432 + v666) = v668;
                                    v669 = -1;
                                    do
                                      v55 = *(_BYTE *)(v668 + v669++ + 1) == 0;
                                    while ( !v55 );
                                    v670 = v669 + 1;
                                    v671 = -1;
                                    v672 = v668 + v670;
                                    do
                                      v55 = *(_BYTE *)(v672 + v671++ + 1) == 0;
                                    while ( !v55 );
                                    v673 = v671 + 1;
                                    v674 = -1;
                                    v675 = v672 + v673;
                                    do
                                      ++v674;
                                    while ( *(_BYTE *)(v675 + v674) );
LABEL_723:
                                    v676 = v675 + v674 + 1;
                                  }
                                  break;
                                }
                                v677 = -1;
                                do
                                  v55 = *(_BYTE *)(v676 + v677++ + 1) == 0;
                                while ( !v55 );
                                v678 = v676 + v677 + 1;
                                if ( v1388 != 6 )
                                  goto LABEL_844;
                                *((_QWORD *)v1432 + v662) = v678;
                                v679 = -1;
                                do
                                  v55 = *(_BYTE *)(v678 + v679++ + 1) == 0;
                                while ( !v55 );
                                v680 = v678 + v679 + 1;
                                goto LABEL_730;
                              }
LABEL_1743:
                              v1326 = v1399;
                              goto LABEL_1744;
                            }
LABEL_510:
                            v1330 = -1073425151;
LABEL_511:
                            v102 = Src;
                            goto LABEL_512;
                          }
                        }
                      }
                    }
LABEL_498:
                    v1330 = -1073741675;
                    goto LABEL_511;
                  }
                }
                v1330 = -1073741675;
LABEL_506:
                if ( v1330 >= 0 )
                  goto LABEL_507;
                goto LABEL_511;
              }
              v145 = 0;
              v146 = v1409;
              do
              {
                v147 = *v146 + 4;
                if ( *v146 >= 0xFFFFFFFC || (_DWORD *)((char *)v146 + v147) < v146 )
                  goto LABEL_146;
                ++v145;
                v146 = (_DWORD *)((char *)v146 + v147);
              }
              while ( v145 < v114 );
              if ( v146 + 1 >= v146 )
              {
                if ( v146 + 2 > (_DWORD *)((char *)v1409 + (unsigned int)v137) )
                {
                  v1330 = -1073741789;
LABEL_505:
                  v389 = 0;
                  goto LABEL_506;
                }
                v148 = v1406;
                *v146 = 4;
                v149 = 0;
                v146[1] = v148;
                v150 = v142;
                v151 = v114 + 1;
                if ( v151 )
                {
                  while ( 1 )
                  {
                    v152 = *v150 + 4;
                    if ( v152 < 4 || (_DWORD *)((char *)v150 + v152) < v150 )
                      break;
                    ++v149;
                    v150 = (_DWORD *)((char *)v150 + v152);
                    if ( v149 >= v151 )
                      goto LABEL_203;
                  }
                }
                else
                {
                  Size = v137;
LABEL_203:
                  if ( v150 + 1 >= v150 )
                  {
                    if ( v150 + 2 <= (_DWORD *)((char *)v142 + (unsigned int)v137) )
                    {
                      *v150 = 4;
                      v144 = v151 + 1;
                      v150[1] = 4;
                      goto LABEL_207;
                    }
                    v1330 = -1073741789;
                    goto LABEL_505;
                  }
                }
              }
              goto LABEL_146;
            }
LABEL_173:
            v138 = -1073741675;
          }
        }
        else
        {
          v138 = -1073741811;
        }
        v137 = Size;
        goto LABEL_184;
      }
LABEL_73:
      v80 = off_1800AC158[0];
      CurrentThreadId = GetCurrentThreadId();
      v82 = ((__int64 (__fastcall *)(_QWORD))v80)(CurrentThreadId);
      if ( !v82 )
      {
        v83 = GetLastError();
        v76 = v83;
        if ( v83 > 0 )
          v76 = (unsigned __int16)v83 | 0x80070000;
        if ( v76 >= 0 )
          v76 = -2147467259;
        goto LABEL_116;
      }
      v84 = 0;
      v1431[0] = 0;
      for ( i10 = 0; ; i10 = v1431[0] )
      {
        if ( ((unsigned int (__fastcall *)(__int64, __int64, _WORD *, __int64, _DWORD *))off_1800AC160[0])(
               v82,
               2,
               v84,
               i10,
               v1431) )
        {
          v70 = v84;
          v76 = 0;
          goto LABEL_96;
        }
        v86 = GetLastError();
        v76 = v86;
        if ( v86 != 122 )
          break;
        if ( v84 )
        {
          v76 = -2147467259;
          goto LABEL_92;
        }
        v87 = v1431[0];
        v88 = GetProcessHeap();
        v84 = HeapAlloc(v88, 0, v87);
        if ( !v84 )
          goto LABEL_85;
      }
      if ( v86 )
      {
        if ( v86 > 0 )
          v76 = (unsigned __int16)v86 | 0x80070000;
      }
      else
      {
        v76 = -2147467259;
      }
      if ( v84 )
      {
LABEL_92:
        v89 = GetProcessHeap();
        HeapFree(v89, 0, v84);
      }
      if ( v76 < 0 )
        goto LABEL_114;
LABEL_96:
      if ( v69 )
      {
        v90 = 0;
        do
        {
          v91 = *((_WORD *)v69 + v90++);
          if ( v91 != aWinsta0[v90 - 1] )
            goto LABEL_113;
        }
        while ( v90 != 8 );
        if ( v70 )
        {
          v92 = 0;
          do
          {
            v93 = v70[v92++];
            if ( v93 != aDefault[v92 - 1] )
              goto LABEL_113;
          }
          while ( v92 != 8 );
          v1433 = 0;
          CurrentProcess = GetCurrentProcess();
          if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1433, 4) )
          {
            v95 = GetLastError();
            v76 = v95;
            if ( v95 > 0 )
              v76 = (unsigned __int16)v95 | 0x80070000;
            if ( v76 >= 0 )
              v76 = -2147467259;
LABEL_115:
            v96 = GetProcessHeap();
            HeapFree(v96, 0, v70);
            goto LABEL_116;
          }
          if ( (v1433 & 0xF) == 0 )
            v71 = 1;
        }
      }
    }
    else
    {
      v76 = 0;
    }
LABEL_113:
    LODWORD(v1406) = v71;
LABEL_114:
    if ( !v70 )
      goto LABEL_116;
    goto LABEL_115;
  }
  v2 = -2147024809;
LABEL_1769:
  SP_HLOCAL<unsigned char>::~SP_HLOCAL<unsigned char>(&v1434);
  return v2;
}

```

## disassembly

```asm
0x180067160  push    rbp
0x180067162  push    rdi
0x180067163  lea     rbp, [rsp-0DC8h]
0x18006716b  sub     rsp, 0EC8h
0x180067172  mov     rax, cs:__security_cookie
0x180067179  xor     rax, rsp
0x18006717c  mov     [rbp+0DD0h+var_40], rax
0x180067183  mov     [rbp+0DD0h+var_C90], rdx
0x18006718a  mov     [rbp+0DD0h+psz], rcx
0x18006718e  mov     [rbp+0DD0h+var_D08], 0
0x180067199  test    rcx, rcx
0x18006719c  jnz     short loc_1800671A8
0x18006719e  mov     edi, 80070057h
0x1800671a3  jmp     loc_180073420
0x1800671a8  test    rdx, rdx
0x1800671ab  jz      short loc_18006719E
0x1800671ad  mov     [rsp+0ED0h+var_10], rsi
0x1800671b5  mov     ecx, 1
0x1800671ba  mov     [rsp+0ED0h+var_18], r12
0x1800671c2  xor     eax, eax
0x1800671c4  mov     [rsp+0ED0h+var_20], r13
0x1800671cc  mov     dword ptr [rbp+0DD0h+var_E3C], 0
0x1800671d3  mov     qword ptr [rbp+0DD0h+var_D4C+4], 0
0x1800671de  lock cmpxchg cs:g_WarbirdSecureFunctionsLock, ecx
0x1800671e6  jz      short loc_1800671FC
0x1800671e8  nop     dword ptr [rax+rax+00000000h]
0x1800671f0  xor     eax, eax
0x1800671f2  lock cmpxchg cs:g_WarbirdSecureFunctionsLock, ecx
0x1800671fa  jnz     short loc_1800671F0
0x1800671fc  cmp     cs:g_WarbirdSecureFunctionsRefCount, 0
0x180067203  mov     esi, 0FFFFFFFFh
0x180067208  mov     [rsp+0ED0h+arg_10], rbx
0x180067210  mov     [rsp+0ED0h+var_28], r14
0x180067218  mov     [rsp+0ED0h+var_30], r15
0x180067220  mov     [rbp+0DD0h+var_D88], esi
0x180067223  jnz     loc_180067B44
0x180067229  mov     ecx, 338h
0x18006722e  call    ??$MemoryAllocT@K@@YAPEAK_K@Z; MemoryAllocT<ulong>(unsigned __int64)
0x180067233  mov     [rbp+0DD0h+lpMem], rax
0x180067237  mov     r13, rax
0x18006723a  test    rax, rax
0x18006723d  jz      loc_18006782B
0x180067243  xor     r14d, r14d
0x180067246  lea     rbx, qword_18009D240
0x18006724d  xor     r9d, r9d
0x180067250  mov     r15d, esi
0x180067253  xor     edx, edx
0x180067255  mov     rdi, rax
0x180067258  mov     esi, 67h ; 'g'
0x18006725d  nop     dword ptr [rax]
0x180067260  movzx   eax, byte ptr [rbx+1]
0x180067264  movzx   r11d, byte ptr [rbx]
0x180067268  movzx   r10d, byte ptr [rbx+4]
0x18006726d  lea     rbx, [rbx+8]
0x180067271  shl     r11d, 8
0x180067275  or      r11d, eax
0x180067278  shl     r10d, 8
0x18006727c  movzx   eax, byte ptr [rbx-6]
0x180067280  shl     r11d, 8
0x180067284  or      r11d, eax
0x180067287  movzx   eax, byte ptr [rbx-5]
0x18006728b  shl     r11d, 8
0x18006728f  or      r11d, eax
0x180067292  movzx   eax, byte ptr [rbx-3]
0x180067296  or      r10d, eax
0x180067299  mov     ecx, r11d
0x18006729c  movzx   eax, byte ptr [rbx-2]
0x1800672a0  xor     ecx, edx
0x1800672a2  mov     edx, ecx
0x1800672a4  shl     r10d, 8
0x1800672a8  or      r10d, eax
0x1800672ab  movzx   eax, byte ptr [rbx-1]
0x1800672af  shl     r10d, 8
0x1800672b3  or      r10d, eax
0x1800672b6  xor     edx, r10d
0x1800672b9  xor     edx, r9d
0x1800672bc  xor     edx, 0AC987321h
0x1800672c2  lea     eax, [rdx+54969FA2h]
0x1800672c8  ror     eax, 1Bh
0x1800672cb  imul    r8d, eax, 137Fh
0x1800672d2  mov     eax, edx
0x1800672d4  ror     eax, 16h
0x1800672d7  add     r8d, eax
0x1800672da  xor     r8d, ecx
0x1800672dd  lea     eax, [r8+7F1137Fh]
0x1800672e4  ror     eax, 9
0x1800672e7  imul    ecx, eax, 0AB69h
0x1800672ed  mov     eax, r8d
0x1800672f0  ror     eax, 1Eh
0x1800672f3  sub     ecx, eax
0x1800672f5  xor     ecx, edx
0x1800672f7  imul    r9d, ecx, 605Eh
0x1800672fe  mov     eax, ecx
0x180067300  shr     eax, 0Dh
0x180067303  sub     r9d, eax
0x180067306  sub     r9d, 756C8A2h
0x18006730d  xor     r9d, r8d
0x180067310  mov     r8d, 7F1137Fh
0x180067316  mov     eax, r9d
0x180067319  xor     eax, 0AB69h
0x18006731e  ror     eax, 1Ah
0x180067321  imul    edx, eax, 7F1h
0x180067327  mov     eax, r9d
0x18006732a  ror     eax, 1Eh
0x18006732d  sub     edx, eax
0x18006732f  xor     edx, ecx
0x180067331  mov     eax, edx
0x180067333  xor     eax, 0AB69605Eh
0x180067338  sub     r8d, eax
0x18006733b  xor     r8d, r9d
0x18006733e  mov     eax, r8d
0x180067341  mov     r9d, r8d
0x180067344  xor     eax, 137Fh
0x180067349  ror     r9d, 6
0x18006734d  imul    ecx, eax, 0AB69h
0x180067353  xor     r9d, ecx
0x180067356  xor     r9d, edx
0x180067359  lea     eax, [r9+7F1137Fh]
0x180067360  ror     eax, 0Fh
0x180067363  imul    ecx, eax, 605Eh
0x180067369  mov     eax, r9d
0x18006736c  ror     eax, 1Eh
0x18006736f  add     ecx, eax
0x180067371  xor     ecx, r8d
0x180067374  lea     eax, [rcx+54969FA2h]
0x18006737a  ror     eax, 0Eh
0x18006737d  imul    edx, eax, 7F1h
0x180067383  mov     eax, ecx
0x180067385  ror     eax, 18h
0x180067388  sub     edx, eax
0x18006738a  xor     edx, r9d
0x18006738d  mov     eax, edx
0x18006738f  xor     eax, 0AB69605Eh
0x180067394  ror     eax, 0Ch
0x180067397  imul    r8d, eax, 137Fh
0x18006739e  mov     eax, edx
0x1800673a0  ror     eax, 0Ah
0x1800673a3  xor     r8d, eax
0x1800673a6  xor     r8d, ecx
0x1800673a9  mov     eax, r8d
0x1800673ac  xor     eax, 7F1h
0x1800673b1  imul    ecx, eax, 0AB69h
0x1800673b7  mov     eax, r8d
0x1800673ba  shr     eax, 0Ah
0x1800673bd  xor     ecx, eax
0x1800673bf  xor     ecx, edx
0x1800673c1  mov     eax, ecx
0x1800673c3  not     eax
0x1800673c5  ror     eax, 5
0x1800673c8  add     eax, 605Eh
0x1800673cd  imul    edx, eax, 7F1h
0x1800673d3  xor     edx, r8d
0x1800673d6  lea     r8d, [rdx-7F1h]
0x1800673dd  xor     r8d, ecx
0x1800673e0  xor     r8d, 0AB69605Eh
0x1800673e7  mov     eax, r8d
0x1800673ea  xor     eax, 7F1h
0x1800673ef  ror     eax, 1Eh
0x1800673f2  imul    r9d, eax, 137Fh
0x1800673f9  mov     eax, r8d
0x1800673fc  shr     eax, 2
0x1800673ff  add     r9d, eax
0x180067402  xor     r9d, edx
0x180067405  lea     eax, [r9-7F1137Fh]
0x18006740c  ror     eax, 6
0x18006740f  imul    edx, eax, 0AB69h
0x180067415  mov     eax, r9d
0x180067418  ror     eax, 19h
0x18006741b  add     edx, eax
0x18006741d  xor     edx, r8d
0x180067420  mov     eax, edx
0x180067422  mov     r8d, edx
0x180067425  xor     eax, 137Fh
0x18006742a  ror     r8d, 9
0x18006742e  imul    ecx, eax, 605Eh
0x180067434  add     r8d, ecx
0x180067437  xor     r8d, r9d
0x18006743a  mov     eax, r8d
0x18006743d  xor     eax, 0AB69h
0x180067442  ror     eax, 1Bh
0x180067445  imul    ecx, eax, 7F1h
0x18006744b  mov     eax, r8d
0x18006744e  ror     eax, 19h
0x180067451  add     ecx, eax
0x180067453  xor     ecx, edx
0x180067455  mov     edx, ecx
0x180067457  xor     edx, r8d
0x18006745a  xor     edx, 0AC987321h
0x180067460  mov     eax, edx
0x180067462  ror     eax, 3
0x180067465  imul    r8d, eax, 137Fh
0x18006746c  sub     r8d, 0D0DD417h
0x180067473  xor     r8d, ecx
0x180067476  lea     eax, [r8-7F1137Fh]
0x18006747d  ror     eax, 1
0x18006747f  imul    ecx, eax, 605Eh
0x180067485  mov     eax, r8d
0x180067488  ror     eax, 6
0x18006748b  sub     ecx, eax
0x18006748d  xor     ecx, edx
0x18006748f  lea     eax, [rcx-54969FA2h]
0x180067495  ror     eax, 1Dh
0x180067498  imul    edx, eax, 7F1h
0x18006749e  mov     eax, ecx
0x1800674a0  ror     eax, 12h
0x1800674a3  add     edx, eax
0x1800674a5  xor     edx, r8d
0x1800674a8  lea     eax, [rdx-54969FA2h]
0x1800674ae  ror     eax, 11h
0x1800674b1  imul    r8d, eax, 137Fh
0x1800674b8  mov     eax, edx
0x1800674ba  ror     eax, 0Eh
0x1800674bd  sub     r8d, eax
0x1800674c0  lea     rdi, [rdi+8]
0x1800674c4  xor     r8d, ecx
0x1800674c7  mov     eax, r8d
0x1800674ca  xor     eax, 605Eh
0x1800674cf  imul    r9d, eax, 0AB69h
0x1800674d6  mov     eax, r8d
0x1800674d9  shr     eax, 3
0x1800674dc  xor     r9d, eax
0x1800674df  xor     r9d, edx
0x1800674e2  mov     eax, r9d
0x1800674e5  xor     eax, 7F1137Fh
0x1800674ea  ror     eax, 1Ch
0x1800674ed  imul    edx, eax, 605Eh
0x1800674f3  mov     eax, r9d
0x1800674f6  ror     eax, 1Eh
0x1800674f9  xor     r9d, r15d
0x1800674fc  mov     r15d, r10d
0x1800674ff  xor     edx, eax
0x180067501  xor     edx, r8d
0x180067504  xor     edx, r14d
0x180067507  mov     r14d, r11d
0x18006750a  mov     [rdi-5], dl
0x18006750d  mov     eax, edx
0x18006750f  ror     eax, 8
0x180067512  mov     [rdi-1], r9b
0x180067516  mov     [rdi-6], al
0x180067519  mov     eax, r9d
0x18006751c  ror     eax, 8
0x18006751f  mov     [rdi-2], al
0x180067522  mov     eax, edx
0x180067524  ror     eax, 10h
0x180067527  mov     [rdi-7], al
0x18006752a  mov     eax, r9d
0x18006752d  ror     eax, 10h
0x180067530  mov     [rdi-3], al
0x180067533  mov     eax, edx
0x180067535  ror     eax, 18h
0x180067538  mov     [rdi-8], al
0x18006753b  mov     eax, r9d
0x18006753e  ror     eax, 18h
0x180067541  mov     [rdi-4], al
0x180067544  sub     rsi, 1
0x180067548  jnz     loc_180067260
0x18006754e  xor     eax, eax
0x180067550  xorps   xmm2, xmm2
0x180067553  xorps   xmm1, xmm1
0x180067556  nop     word ptr [rax+rax+00000000h]
0x180067560  movdqu  xmm0, xmmword ptr [rax+r13]
0x180067566  xorps   xmm2, xmm0
0x180067569  movdqu  xmm0, xmmword ptr [rax+r13+10h]
0x180067570  add     rax, 20h ; ' '
0x180067574  xorps   xmm1, xmm0
0x180067577  cmp     rax, 320h
0x18006757d  jb      short loc_180067560
0x18006757f  xorps   xmm1, xmm2
0x180067582  movdqa  xmm0, xmm1
0x180067586  psrldq  xmm0, 8
0x18006758b  xorps   xmm1, xmm0
0x18006758e  movdqa  xmm0, xmm1
0x180067592  psrldq  xmm0, 4
0x180067597  xorps   xmm1, xmm0
0x18006759a  movdqa  xmm0, xmm1
0x18006759e  psrldq  xmm0, 2
0x1800675a3  xorps   xmm1, xmm0
0x1800675a6  movdqa  xmm0, xmm1
0x1800675aa  psrldq  xmm0, 1
0x1800675af  xorps   xmm1, xmm0
0x1800675b2  movd    ecx, xmm1
0x1800675b6  cmp     rax, 338h
0x1800675bc  jnb     short loc_1800675CF
0x1800675be  xchg    ax, ax
0x1800675c0  xor     cl, [rax+r13]
0x1800675c4  inc     rax
0x1800675c7  cmp     rax, 338h
0x1800675cd  jb      short loc_1800675C0
0x1800675cf  movzx   eax, cl
0x1800675d2  cmp     rax, cs:qword_18009D578
0x1800675d9  jnz     loc_18006780B
0x1800675df  xorps   xmm0, xmm0
0x1800675e2  xor     eax, eax
0x1800675e4  mov     [r13+337h], al
0x1800675eb  xor     r14d, r14d
0x1800675ee  xor     r15d, r15d
0x1800675f1  mov     [rbp+0DD0h+var_E50], eax
0x1800675f4  movups  cs:?g_arModuleInfo@WARBIRD@@3PAU_MODULE_INFO@1@A, xmm0; WARBIRD::_MODULE_INFO near * WARBIRD::g_arModuleInfo
0x1800675fb  mov     rdi, r13
0x1800675fe  movups  cs:xmmword_1800AD870, xmm0
  ... truncated ...
```
