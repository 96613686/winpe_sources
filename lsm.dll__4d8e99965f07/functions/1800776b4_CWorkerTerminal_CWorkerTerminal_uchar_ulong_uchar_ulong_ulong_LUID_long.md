# CWorkerTerminal::CWorkerTerminal(uchar *,ulong,uchar *,ulong,ulong,_LUID,long *)

- ea: `0x1800776b4`
- end: `0x18007d702`
- name: `??0CWorkerTerminal@@QEAA@PEAEK0KKU_LUID@@PEAJ@Z`
- size: `24654`
- prototype: `CWorkerTerminal *__usercall@<rax>(CWorkerTerminal *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, SIZE_T uBytes, unsigned int, struct _LUID, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x18007dab4`

## callees

- `0x1800077a0`
- `0x180016740`
- `0x1800212cc`
- `0x180026dd8`
- `0x18002872c`
- `0x18002888c`
- `0x180029b9c`
- `0x180029bcc`
- `0x18002ed3c`
- `0x180031650`
- `0x180047128`
- `0x18004dabc`
- `0x18007761c`
- `0x1800776b4`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079a1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c25a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079a1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c25a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800799c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007c217`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800799c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007c217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077d0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077d32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077d57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078fc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079034`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079061`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800790c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800790fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079135`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007916f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007919c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800792d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079308`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007933e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007939c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800793c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800793ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079421`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800794ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800794d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079672`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079e3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079e76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079eb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079edd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079f80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079ff6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007a025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b382`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007baff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bb39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bb73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bba0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bc02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bc3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bc77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bcb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bf34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c65e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c698`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c6d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c6ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c7a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c7dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c847`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d14d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d17f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d1b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d1e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d232`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d257`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d28e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d2bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d2f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d318`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d33d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d442`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d46f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d4b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077d0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077d32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180077d57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078fc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079034`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079061`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800790c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800790fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079135`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007916f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007919c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800792d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079308`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007933e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007939c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800793c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800793ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079421`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800794ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800794d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079672`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079e3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079e76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079eb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079edd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079f80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079fbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079ff6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007a025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b382`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007baff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bb39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bb73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bba0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bc02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bc3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bc77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bcb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bf34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c65e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c698`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c6d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c6ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c7a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c7dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c818`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c847`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d14d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d17f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d1b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d1e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d232`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d257`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d28e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d2bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d2f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d318`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d33d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d442`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d46f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d4b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007780e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800778e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077b96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077d9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077e3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078767`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078dd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078e4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078eae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078f5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800797e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079c7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079cf7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079d64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079dd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a83c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ae10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b2bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b944`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b987`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b9e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ba9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007bdbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c06c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c4aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c51a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c58d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c5ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007d085`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007780e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800778e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077b96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077d9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077e3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078767`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078dd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078e4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078eae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078f5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800797e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079c7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079cf7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079d64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079dd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a83c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ae10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b2bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b944`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b987`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b9e9`

## string_xrefs

- `0x1800799ba`: `ntdll.dll`
- `0x18007c20b`: `ntdll.dll`
- `0x180077a63`: `TerminalServices-RemoteConnectionManager-b7857721-7a62-4a37-aff3-253fe2b8b0e8-MaxSessions`
- `0x1800781cc`: `TerminalServices-RemoteConnectionManager-b7857721-7a62-4a37-aff3-253fe2b8b0e8-MaxSessions`
- `0x180078321`: `TerminalServices-RemoteConnectionManager-b7857721-7a62-4a37-aff3-253fe2b8b0e8-MaxSessions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CWorkerTerminal *__fastcall CWorkerTerminal::CWorkerTerminal(
        CWorkerTerminal *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        SIZE_T uBytes,
        unsigned int a6,
        struct _LUID a7,
        int *a8)
{
  unsigned int v8; // r12d
  CWorkerTerminal *v9; // r15
  unsigned int v10; // r13d
  int v11; // eax
  signed int v12; // ebx
  int v13; // edi
  unsigned int v14; // ebx
  HLOCAL v15; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v17; // rax
  void *v18; // r15
  int v19; // r14d
  void *v20; // r12
  HANDLE v21; // rax
  _QWORD *v22; // rax
  int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // r10d
  int v26; // eax
  unsigned int v27; // r10d
  int v28; // eax
  unsigned int v29; // r10d
  int v30; // eax
  size_t v31; // rdx
  int v32; // eax
  unsigned int v33; // r10d
  int v34; // eax
  unsigned int v35; // r10d
  int v36; // eax
  unsigned int v37; // esi
  HANDLE v38; // rax
  void *v39; // r9
  _DWORD *v40; // r9
  unsigned int v41; // r10d
  unsigned int v42; // r11d
  int v43; // r10d
  int v44; // eax
  void *v45; // r13
  HANDLE v46; // rax
  void *v47; // r13
  HANDLE v48; // rax
  HANDLE v49; // rax
  HANDLE v50; // rax
  void *v51; // r12
  unsigned __int64 v52; // r13
  HANDLE v53; // rax
  _OWORD *v54; // rax
  void *v55; // r15
  HANDLE v56; // rax
  _QWORD *v57; // rax
  void *v58; // r13
  unsigned int *v59; // r9
  __int64 v60; // r9
  unsigned int v61; // r10d
  unsigned int *v62; // r9
  unsigned int v63; // r11d
  int v64; // r10d
  unsigned int v65; // r11d
  unsigned int *v66; // r9
  __int64 v67; // r9
  unsigned int v68; // r10d
  unsigned int *v69; // r9
  unsigned int v70; // r11d
  int v71; // r9d
  unsigned int *v72; // r10
  size_t v73; // rdx
  __int64 v74; // r10
  unsigned int v75; // r9d
  int v76; // r11d
  _DWORD *v77; // r10
  int v78; // r11d
  unsigned int *v79; // r9
  unsigned int v80; // r11d
  __int64 v81; // r9
  unsigned int v82; // r11d
  _DWORD *v83; // r9
  __int64 v84; // r10
  int v85; // r10d
  unsigned int *v86; // r9
  unsigned int v87; // r11d
  __int64 v88; // r9
  unsigned int v89; // r10d
  int v90; // r11d
  unsigned int *v91; // r9
  int v92; // r10d
  unsigned int *v93; // r9
  unsigned int v94; // r11d
  __int64 v95; // r9
  unsigned int v96; // r10d
  int v97; // r11d
  unsigned int *v98; // r9
  __int64 v99; // rcx
  unsigned int v100; // r9d
  unsigned int v101; // r11d
  unsigned int v102; // r11d
  unsigned int v103; // r11d
  unsigned int v104; // r11d
  unsigned int v105; // r9d
  int v106; // r14d
  unsigned int v107; // eax
  unsigned int v108; // esi
  HANDLE v109; // rax
  _DWORD *v110; // rax
  int v111; // r9d
  void *v112; // r10
  unsigned int v113; // r11d
  __int64 v114; // rcx
  __int64 v115; // r10
  HANDLE v116; // rax
  unsigned int *v117; // rsi
  unsigned int *v118; // r13
  unsigned __int8 *v119; // r14
  void *v120; // rdx
  unsigned __int8 v121; // al
  SIZE_T v122; // rcx
  SIZE_T v123; // r10
  unsigned __int8 *v124; // r11
  unsigned int v125; // edx
  unsigned int v126; // r9d
  unsigned int v127; // edi
  int v128; // ebx
  int v129; // r8d
  unsigned int v130; // r8d
  unsigned int v131; // r9d
  unsigned int v132; // ecx
  int v133; // r11d
  _BYTE *v134; // rdi
  char v135; // bl
  int v136; // r9d
  int v137; // r15d
  _BYTE *v138; // rdi
  SIZE_T v139; // r14
  unsigned int v140; // r13d
  int v141; // eax
  unsigned int v142; // r12d
  int v143; // esi
  int v144; // r11d
  int v145; // edx
  int v146; // r9d
  int v147; // r10d
  int v148; // r8d
  int v149; // r9d
  unsigned int v150; // edx
  int v151; // r8d
  int v152; // ecx
  int v153; // edx
  int v154; // r9d
  int v155; // edx
  unsigned int v156; // r8d
  unsigned int v157; // r9d
  int v158; // edx
  int v159; // r8d
  int v160; // r9d
  int v161; // edx
  int v162; // r8d
  int v163; // r9d
  int v164; // r10d
  int v165; // r8d
  unsigned int v166; // edx
  int v167; // r9d
  HANDLE v168; // rax
  _DWORD *v169; // rax
  int v170; // r14d
  HANDLE v171; // rax
  void *v172; // rcx
  _DWORD *v173; // r14
  HANDLE v174; // rax
  _OWORD *v175; // rcx
  _DWORD *v176; // rax
  HANDLE v177; // rax
  _QWORD *v178; // rax
  _QWORD *v179; // rax
  HANDLE v180; // rax
  HANDLE v181; // rax
  HANDLE v182; // rax
  HANDLE v183; // rax
  unsigned int *v184; // rcx
  HANDLE v185; // rax
  _QWORD *v186; // rax
  HANDLE v187; // rax
  HANDLE v188; // rax
  HANDLE v189; // rax
  HANDLE v190; // rax
  unsigned int v191; // r9d
  int v192; // r14d
  unsigned int v193; // r9d
  unsigned int v194; // esi
  HANDLE v195; // rax
  _DWORD *v196; // rax
  LPVOID v197; // rax
  HANDLE v198; // rax
  HANDLE v199; // rax
  HANDLE v200; // rax
  HANDLE v201; // rax
  HANDLE v202; // rax
  void *v203; // rsi
  HANDLE v204; // rax
  HANDLE v205; // rax
  _QWORD *v206; // rsi
  void *v207; // r13
  HANDLE v208; // rax
  void *v209; // r13
  HANDLE v210; // rax
  void *v211; // r13
  HANDLE v212; // rax
  HANDLE v213; // rax
  void *v214; // rsi
  HANDLE v215; // rax
  void *v216; // rcx
  void *v217; // r9
  int v218; // r10d
  void *v219; // rcx
  unsigned int *v220; // r9
  void *v221; // rcx
  unsigned int *v222; // r9
  HANDLE v223; // rax
  int v224; // eax
  __int64 v225; // rcx
  void *v226; // r9
  LPVOID v227; // rcx
  unsigned int v228; // r9d
  int v229; // r11d
  LPVOID v230; // rcx
  unsigned int v231; // esi
  HANDLE v232; // rax
  unsigned int *v233; // rax
  unsigned int v234; // r11d
  int v235; // r9d
  unsigned int v236; // r10d
  unsigned int v237; // r11d
  unsigned int v238; // r11d
  unsigned int v239; // r11d
  unsigned int v240; // r9d
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  int v243; // eax
  unsigned int v244; // r9d
  SIZE_T v245; // rsi
  unsigned int v246; // r10d
  int v247; // r14d
  unsigned int *v248; // rcx
  int v249; // r9d
  int v250; // r9d
  __int64 v251; // r10
  unsigned int v252; // r10d
  int v253; // r9d
  void *v254; // r11
  unsigned int v255; // r11d
  int v256; // r9d
  unsigned int v257; // r10d
  int v258; // r9d
  unsigned int v259; // r10d
  int v260; // r9d
  int v261; // r10d
  int v262; // r11d
  HANDLE v263; // rax
  _DWORD *v264; // rcx
  HANDLE v265; // rax
  void *v266; // rcx
  HANDLE v267; // rax
  void *v268; // rcx
  void *v269; // rax
  void *v270; // rax
  unsigned int v271; // r14d
  HANDLE v272; // rax
  void *v273; // rcx
  _QWORD *v274; // rax
  HANDLE v275; // rax
  HANDLE v276; // rax
  HANDLE v277; // rax
  HANDLE v278; // rax
  unsigned int *v279; // rdx
  HANDLE v280; // rax
  HANDLE v281; // rax
  HANDLE v282; // rax
  HANDLE v283; // rax
  unsigned __int64 v284; // r14
  void *v285; // r11
  unsigned __int8 v286; // al
  unsigned int v287; // r9d
  unsigned int v288; // r10d
  unsigned __int8 *v289; // rbx
  int v290; // edi
  int v291; // eax
  int v292; // r8d
  unsigned int v293; // r8d
  unsigned int v294; // r10d
  int v295; // ecx
  int v296; // edx
  unsigned int v297; // esi
  _BYTE *v298; // rdi
  char v299; // bl
  int v300; // r10d
  int v301; // r11d
  unsigned __int8 *v302; // rbx
  _BYTE *v303; // rax
  SIZE_T v304; // r13
  int v305; // r12d
  int v306; // r15d
  int v307; // r14d
  int v308; // esi
  int v309; // edx
  unsigned int v310; // r8d
  int v311; // r9d
  unsigned int v312; // edx
  int v313; // r8d
  int v314; // r9d
  unsigned int v315; // edx
  int v316; // r8d
  int v317; // r10d
  int v318; // r11d
  unsigned int v319; // r9d
  int v320; // r8d
  unsigned int v321; // r9d
  int v322; // r10d
  int v323; // r11d
  int v324; // edx
  int v325; // r8d
  unsigned int v326; // r9d
  int v327; // edx
  int v328; // r10d
  int v329; // r8d
  unsigned int v330; // edx
  int v331; // r10d
  unsigned __int64 i; // rcx
  int v333; // r14d
  void *v334; // r9
  void *v335; // r10
  unsigned int *v336; // r11
  void *v337; // rcx
  void *v338; // r11
  void *v339; // r10
  void *v340; // r9
  SIZE_T v341; // rax
  void *v342; // r9
  void *v343; // r10
  void *v344; // r11
  LPVOID v345; // rcx
  void *v346; // rcx
  unsigned int v347; // edx
  HANDLE v348; // rax
  unsigned int v349; // eax
  __int64 v350; // rcx
  _DWORD *v351; // r9
  int v352; // r10d
  int *v353; // r14
  int v354; // r13d
  unsigned int v355; // r11d
  int v356; // r10d
  void *v357; // r9
  int v358; // r10d
  LPVOID *v359; // rdx
  void *v360; // rcx
  unsigned int v361; // r11d
  int v362; // r10d
  void *v363; // r9
  int v364; // r10d
  unsigned int *v365; // rdx
  void *v366; // rcx
  unsigned int v367; // r11d
  int v368; // r10d
  unsigned int *v369; // r9
  int v370; // r11d
  const void *v371; // r13
  unsigned int *v372; // rcx
  int v373; // r10d
  void *v374; // r9
  int v375; // r10d
  unsigned int *v376; // rdx
  void *v377; // rcx
  unsigned int v378; // r9d
  int v379; // r10d
  int v380; // r9d
  unsigned int v381; // r10d
  size_t v382; // r11
  int *v383; // rcx
  _DWORD *v384; // rcx
  unsigned int v385; // r11d
  int v386; // eax
  unsigned int v387; // r11d
  int v388; // r9d
  int v389; // eax
  unsigned int v390; // r11d
  int v391; // r9d
  int v392; // eax
  int v393; // r9d
  unsigned int v394; // esi
  HANDLE v395; // rax
  LPVOID v396; // rax
  _DWORD *v397; // r9
  int v398; // r10d
  unsigned int v399; // r11d
  int v400; // r10d
  unsigned int *v401; // r9
  unsigned int v402; // r11d
  __int64 v403; // r9
  unsigned int v404; // r10d
  unsigned int *v405; // r9
  unsigned int v406; // r11d
  int v407; // r10d
  unsigned int *v408; // r9
  unsigned int v409; // r11d
  __int64 v410; // r9
  unsigned int v411; // r10d
  int v412; // r11d
  _DWORD *v413; // r9
  int v414; // r9d
  unsigned int *v415; // r10
  unsigned int v416; // r11d
  __int64 v417; // r10
  unsigned int v418; // r9d
  int v419; // r11d
  _DWORD *v420; // r10
  __int64 v421; // rcx
  unsigned int v422; // r9d
  unsigned int v423; // r13d
  int v424; // ecx
  size_t v425; // r9
  unsigned int v426; // r10d
  unsigned int v427; // eax
  unsigned int v428; // esi
  HANDLE v429; // rax
  _DWORD *v430; // rax
  size_t v431; // r9
  unsigned int v432; // r10d
  __int64 v433; // rcx
  __int64 v434; // r9
  HANDLE v435; // rax
  unsigned int *v436; // rsi
  unsigned int *v437; // r13
  int v438; // ecx
  void *v439; // r8
  unsigned __int8 v440; // al
  SIZE_T v441; // rcx
  SIZE_T v442; // r11
  unsigned int v443; // r8d
  unsigned int v444; // r10d
  unsigned __int8 *v445; // rdi
  unsigned int v446; // ebx
  int v447; // esi
  int v448; // r9d
  unsigned int v449; // r10d
  unsigned int v450; // r9d
  int v451; // ecx
  int v452; // edx
  _BYTE *v453; // rbx
  char v454; // di
  int v455; // r9d
  int v456; // r8d
  unsigned __int8 *v457; // rdi
  _BYTE *v458; // r13
  SIZE_T v459; // rax
  unsigned int v460; // r14d
  int v461; // r12d
  unsigned int v462; // r15d
  int v463; // esi
  int v464; // r11d
  int v465; // edx
  int v466; // r9d
  int v467; // r10d
  int v468; // r8d
  int v469; // r9d
  unsigned int v470; // edx
  int v471; // r8d
  int v472; // ecx
  int v473; // edx
  int v474; // r8d
  int v475; // r9d
  int v476; // edx
  unsigned int v477; // r8d
  unsigned int v478; // r9d
  int v479; // edx
  int v480; // r8d
  int v481; // r9d
  int v482; // edx
  int v483; // r8d
  int v484; // r10d
  int v485; // edx
  int v486; // r9d
  unsigned int v487; // r8d
  int v488; // edx
  HANDLE v489; // rax
  _DWORD *v490; // rax
  void *v491; // rbx
  unsigned int v492; // ebx
  HANDLE v493; // rax
  void *v494; // rcx
  HANDLE v495; // rax
  _OWORD *v496; // rcx
  _DWORD *v497; // rax
  HANDLE v498; // rax
  _QWORD *v499; // rax
  _QWORD *v500; // rax
  HANDLE v501; // rax
  HANDLE v502; // rax
  HANDLE v503; // rax
  HANDLE v504; // rax
  void *v505; // rcx
  HANDLE v506; // rax
  _QWORD *v507; // rax
  HANDLE v508; // rax
  HANDLE v509; // rax
  HANDLE v510; // rax
  HANDLE v511; // rax
  unsigned int v512; // r9d
  unsigned int v513; // r9d
  unsigned int v514; // ebx
  HANDLE v515; // rax
  _DWORD *v516; // rax
  void *v517; // rdi
  void *v518; // rcx
  int v519; // r9d
  LPVOID v520; // rcx
  unsigned int *v521; // r9
  LPVOID v522; // rcx
  unsigned int *v523; // r9
  int v524; // eax
  HANDLE v525; // rax
  int v526; // eax
  int v527; // eax
  int v528; // r9d
  __int64 v529; // rcx
  size_t v530; // rcx
  unsigned int v531; // r11d
  int v532; // r10d
  unsigned int v533; // ebx
  size_t v534; // rcx
  unsigned int v535; // ebx
  HANDLE v536; // rax
  unsigned int *v537; // rax
  unsigned int v538; // r11d
  int v539; // r10d
  unsigned int v540; // r9d
  unsigned int v541; // r11d
  unsigned int v542; // r11d
  unsigned int v543; // r11d
  unsigned int v544; // r10d
  bool v545; // sf
  FARPROC v546; // rax
  unsigned int v547; // r9d
  SIZE_T v548; // rbx
  int v549; // ecx
  unsigned int v550; // r10d
  int v551; // r9d
  int v552; // r9d
  __int64 v553; // r10
  unsigned int v554; // r10d
  int v555; // r9d
  SIZE_T v556; // r11
  unsigned int v557; // r11d
  int v558; // r9d
  unsigned int v559; // r10d
  int v560; // r9d
  unsigned int v561; // r10d
  int v562; // r9d
  int v563; // r10d
  int v564; // r11d
  HANDLE v565; // rax
  _QWORD *v566; // rax
  _DWORD *v567; // rcx
  HANDLE v568; // rax
  void *v569; // rcx
  _QWORD *v570; // rax
  HANDLE v571; // rax
  void *v572; // rcx
  SIZE_T v573; // rax
  HANDLE v574; // rax
  void *v575; // rcx
  HANDLE v576; // rax
  HANDLE v577; // rax
  HANDLE v578; // rax
  HANDLE v579; // rax
  unsigned int *v580; // rdx
  unsigned int *v581; // rax
  HANDLE v582; // rax
  HANDLE v583; // rax
  HANDLE v584; // rax
  HANDLE v585; // rax
  void *v586; // r10
  unsigned __int8 v587; // al
  unsigned __int8 *v588; // r11
  size_t v589; // r8
  int v590; // edi
  unsigned int v591; // r8d
  unsigned int v592; // eax
  unsigned int v593; // edx
  _BYTE *v594; // rcx
  unsigned int v595; // r9d
  unsigned int v596; // r11d
  int v597; // ebx
  int v598; // edi
  unsigned int v599; // eax
  char v600; // r10
  int v601; // r11d
  int v602; // r14d
  int v603; // r10d
  unsigned __int8 *v604; // rax
  _BYTE *v605; // r13
  unsigned int v606; // r12d
  SIZE_T v607; // r15
  int v608; // esi
  int v609; // ebx
  unsigned int v610; // r8d
  int v611; // r9d
  unsigned int v612; // edx
  int v613; // r8d
  int v614; // r9d
  unsigned int v615; // edx
  int v616; // r8d
  int v617; // r10d
  int v618; // r11d
  unsigned int v619; // r9d
  int v620; // r8d
  unsigned int v621; // r9d
  int v622; // edx
  int v623; // r8d
  int v624; // r9d
  int v625; // edx
  int v626; // r8d
  int v627; // r9d
  int v628; // r10d
  int v629; // edx
  unsigned int v630; // r8d
  int v631; // r11d
  size_t j; // rcx
  void *v633; // r9
  void *v634; // rdi
  int v635; // ecx
  unsigned int *v636; // r10
  int v637; // r11d
  __int64 v638; // rbx
  int v639; // r11d
  unsigned int v640; // r11d
  __int64 v641; // rdx
  unsigned int *v642; // r11
  void *v643; // r10
  unsigned int *v644; // rbx
  LPVOID v645; // rax
  void *v646; // r15
  unsigned int *v647; // r12
  void *v648; // r13
  void *v649; // rcx
  unsigned int v650; // edx
  HANDLE v651; // rax
  int v652; // eax
  HANDLE v653; // rax
  void *v654; // rbx
  HANDLE v655; // rax
  void *v656; // rbx
  HANDLE v657; // rax
  void *v658; // rbx
  HANDLE v659; // rax
  HANDLE v660; // rax
  void *v661; // rbx
  HANDLE v662; // rax
  HANDLE v663; // rax
  _QWORD *v664; // rbx
  void *v665; // rsi
  HANDLE v666; // rax
  void *v667; // rsi
  HANDLE v668; // rax
  void *v669; // rsi
  HANDLE v670; // rax
  HANDLE v671; // rax
  HANDLE v672; // rax
  unsigned int v673; // r9d
  __int64 v674; // r11
  int *v675; // rcx
  unsigned __int64 v676; // rcx
  unsigned int v677; // r10d
  int v678; // r9d
  void *v679; // rbx
  HANDLE v680; // rax
  HANDLE v681; // rax
  HANDLE v682; // rax
  HANDLE v683; // rax
  HLOCAL v684; // rax
  signed int v685; // eax
  int v686; // ecx
  int v687; // r8d
  int v688; // r9d
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v691; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v692[3]; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v693; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v694; // [rsp+50h] [rbp-B0h]
  unsigned int v695; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v696; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int8 v697; // [rsp+60h] [rbp-A0h]
  LPVOID v698; // [rsp+68h] [rbp-98h]
  unsigned int *v699; // [rsp+70h] [rbp-90h]
  LPVOID v700; // [rsp+78h] [rbp-88h]
  unsigned __int64 v701; // [rsp+80h] [rbp-80h]
  LPVOID v702; // [rsp+88h] [rbp-78h]
  SIZE_T v703; // [rsp+90h] [rbp-70h]
  LPVOID v704; // [rsp+98h] [rbp-68h]
  void *v705; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v706; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v707; // [rsp+B0h] [rbp-50h]
  unsigned int *v708; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v709; // [rsp+C0h] [rbp-40h]
  LPVOID v710; // [rsp+C8h] [rbp-38h] BYREF
  size_t pcchLength; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID lpMem[2]; // [rsp+D8h] [rbp-28h] BYREF
  SIZE_T v713; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID v714; // [rsp+F0h] [rbp-10h]
  void *v715; // [rsp+F8h] [rbp-8h] BYREF
  SIZE_T v716; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v717; // [rsp+108h] [rbp+8h] BYREF
  void *Src; // [rsp+110h] [rbp+10h]
  size_t v719[2]; // [rsp+118h] [rbp+18h] BYREF
  SIZE_T v720; // [rsp+128h] [rbp+28h] BYREF
  void *v721; // [rsp+130h] [rbp+30h] BYREF
  SIZE_T Size; // [rsp+138h] [rbp+38h]
  unsigned int v723; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v724; // [rsp+144h] [rbp+44h] BYREF
  LPVOID v725; // [rsp+148h] [rbp+48h]
  unsigned int v726; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v727; // [rsp+154h] [rbp+54h] BYREF
  void *v728; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v729; // [rsp+160h] [rbp+60h] BYREF
  int v730; // [rsp+164h] [rbp+64h]
  unsigned int v731; // [rsp+168h] [rbp+68h] BYREF
  unsigned int v732; // [rsp+16Ch] [rbp+6Ch]
  int v733; // [rsp+170h] [rbp+70h]
  unsigned int v734; // [rsp+174h] [rbp+74h]
  unsigned int v735; // [rsp+178h] [rbp+78h]
  int *v736; // [rsp+180h] [rbp+80h] BYREF
  HMODULE hModule; // [rsp+188h] [rbp+88h] BYREF
  void *v738; // [rsp+190h] [rbp+90h]
  CWorkerTerminal *v739; // [rsp+198h] [rbp+98h]
  HMODULE phModule; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v741; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v742; // [rsp+1C0h] [rbp+C0h]
  __int128 v743; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v744; // [rsp+1E0h] [rbp+E0h]
  void *v745; // [rsp+1F0h] [rbp+F0h]
  const char *v746; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v747; // [rsp+200h] [rbp+100h] BYREF
  int *v748; // [rsp+208h] [rbp+108h]
  void *v749; // [rsp+210h] [rbp+110h]
  CWorkerTerminal *v750; // [rsp+220h] [rbp+120h]

  v749 = a4;
  v8 = a3;
  v734 = a3;
  v745 = a2;
  v9 = this;
  v739 = this;
  v750 = this;
  v10 = uBytes;
  v735 = uBytes;
  v748 = a8;
  CTSPrivateObject<IWorkerTerminal>::CTSPrivateObject<IWorkerTerminal>();
  *((_QWORD *)v9 + 199) = v9;
  *(_QWORD *)v9 = &CWorkerTerminal::`vftable';
  *((_DWORD *)v9 + 400) = -1;
  *((_QWORD *)v9 + 201) = 0;
  *((_QWORD *)v9 + 203) = 0;
  *((_DWORD *)v9 + 434) = 0;
  *((_DWORD *)v9 + 436) = -1;
  *((_DWORD *)v9 + 437) = a6;
  *((struct _LUID *)v9 + 219) = a7;
  _InterlockedIncrement((volatile signed __int32 *)&CWorkerTerminal::WorkerTerminalCount);
  v11 = CResource::Initialize((CWorkerTerminal *)((char *)v9 + 1640));
  v12 = v11;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "Lock.Initialize failed: 0x%x in %s", (unsigned int)v11, "CWorkerTerminal::CWorkerTerminal");
LABEL_885:
    CWorkerTerminal::CleanupWorkerTerminal(v9);
    goto LABEL_889;
  }
  v13 = 0;
  v733 = 0;
  v736 = 0;
  v14 = 0;
  LODWORD(v698) = 0;
  v728 = 0;
  v15 = LocalAlloc(0x40u, 4u);
  SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v728, v15);
  v738 = v728;
  if ( !v728 )
  {
    v19 = -2147024882;
    goto LABEL_863;
  }
  v732 = 0;
  v730 = 0;
  *(_OWORD *)lpMem = 0;
  v706 = 0;
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v18 = v17;
  LODWORD(v701) = -805306345;
  v717 = -1;
  v19 = -1073741801;
  if ( !v17 )
  {
    v20 = 0;
    LODWORD(dwBytes) = -1073741801;
    goto LABEL_37;
  }
  *v17 = xmmword_1800DF540;
  v17[1] = xmmword_1800DF550;
  v17[2] = xmmword_1800DF560;
  v17[3] = xmmword_1800DF570;
  v17[4] = xmmword_1800DF580;
  v17[5] = xmmword_1800DF590;
  v17[6] = xmmword_1800DF5A0;
  v17[7] = xmmword_1800DF5B0;
  v17[8] = xmmword_1800DF5C0;
  v17[9] = xmmword_1800DF5D0;
  v21 = GetProcessHeap();
  v22 = HeapAlloc(v21, 8u, 8u);
  v20 = v22;
  if ( !v22 )
  {
    LODWORD(dwBytes) = -1073741801;
    goto LABEL_37;
  }
  *v22 = qword_1800DF480;
  v720 = __rdtsc();
  v691 = 0;
  v19 = RtlUIntAdd(4, 4, &v691);
  dwBytes = (unsigned int)v19;
  if ( v19 >= 0 )
  {
    v23 = RtlUIntAdd(0, v691, (char *)&dwBytes + 4);
    v19 = v23 | 0x10000000;
    LODWORD(dwBytes) = v23 | 0x10000000;
    if ( v23 >= 0 )
    {
      v691 = v24;
      v19 = RtlUIntAdd(v25, 160, &v691);
      LODWORD(dwBytes) = v19;
      if ( v19 >= 0 )
      {
        v26 = RtlUIntAdd(HIDWORD(dwBytes), v691, (char *)&dwBytes + 4);
        v19 = v26 | 0x10000000;
        LODWORD(dwBytes) = v26 | 0x10000000;
        if ( v26 >= 0 )
        {
          v691 = 0;
          v19 = RtlUIntAdd(v27, 8, &v691);
          LODWORD(dwBytes) = v19;
          if ( v19 >= 0 )
          {
            v28 = RtlUIntAdd(HIDWORD(dwBytes), v691, (char *)&dwBytes + 4);
            v19 = v28 | 0x10000000;
            LODWORD(dwBytes) = v28 | 0x10000000;
            if ( v28 >= 0 )
            {
              v691 = 0;
              v19 = RtlUIntAdd(v29, 8, &v691);
              LODWORD(dwBytes) = v19;
              if ( v19 >= 0 )
              {
                v30 = RtlUIntAdd(HIDWORD(dwBytes), v691, (char *)&dwBytes + 4);
                v19 = v30 | 0x10000000;
                LODWORD(dwBytes) = v30 | 0x10000000;
                if ( v30 >= 0 )
                {
                  pcchLength = 0;
                  if ( StringCchLengthW(
                         L"TerminalServices-RemoteConnectionManager-b7857721-7a62-4a37-aff3-253fe2b8b0e8-MaxSessions",
                         v31,
                         &pcchLength) < 0 )
                  {
                    v19 = -1073741762;
LABEL_240:
                    LODWORD(dwBytes) = v19;
                    goto LABEL_37;
                  }
                  v691 = 0;
                  v19 = RtlUIntAdd(4, (unsigned int)(2 * (pcchLength + 1)), &v691);
                  LODWORD(dwBytes) = v19;
                  if ( v19 >= 0 )
                  {
                    v32 = RtlUIntAdd(HIDWORD(dwBytes), v691, (char *)&dwBytes + 4);
                    v19 = v32 | 0x10000000;
                    LODWORD(dwBytes) = v32 | 0x10000000;
                    if ( v32 >= 0 )
                    {
                      v691 = 0;
                      v19 = RtlUIntAdd(v33, v33, &v691);
                      LODWORD(dwBytes) = v19;
                      if ( v19 >= 0 )
                      {
                        v34 = RtlUIntAdd(HIDWORD(dwBytes), v691, (char *)&dwBytes + 4);
                        v19 = v34 | 0x10000000;
                        LODWORD(dwBytes) = v34 | 0x10000000;
                        if ( v34 >= 0 )
                        {
                          v691 = 0;
                          v19 = RtlUIntAdd(v35, v35, &v691);
                          LODWORD(dwBytes) = v19;
                          if ( v19 >= 0 )
                          {
                            v36 = RtlUIntAdd(HIDWORD(dwBytes), v691, (char *)&dwBytes + 4);
                            v19 = v36 | 0x10000000;
                            LODWORD(dwBytes) = v36 | 0x10000000;
                            if ( v36 >= 0 )
                            {
                              HIDWORD(lpMem[0]) = HIDWORD(dwBytes);
                              v37 = HIDWORD(dwBytes);
                              v38 = GetProcessHeap();
                              v39 = HeapAlloc(v38, 8u, v37);
                              if ( !v39 )
                              {
                                v19 = -1073741801;
                                goto LABEL_240;
                              }
                              v692[0] = 0;
                              lpMem[1] = v39;
                              LODWORD(lpMem[0]) = 0;
                              LODWORD(v708) = 0;
                              v707 = 0;
                              *(_QWORD *)&v692[1] = v39;
                              v691 = 8;
                              v19 = RtlULongLongAdd(v39, 4, &v708);
                              LODWORD(dwBytes) = v19;
                              if ( v19 >= 0 )
                              {
                                if ( v40 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                {
LABEL_28:
                                  v19 = -1073741789;
LABEL_32:
                                  LODWORD(dwBytes) = v19;
                                  goto LABEL_37;
                                }
                                *v40 = 4;
                                *v708 = v41;
                                v43 = ++LODWORD(lpMem[0]);
                                LODWORD(v708) = 0;
                                v707 = 0;
                                if ( v18 )
                                {
                                  if ( !v42 )
                                    goto LABEL_31;
                                }
                                else if ( v42 )
                                {
                                  goto LABEL_31;
                                }
                                v59 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  *(LPVOID *)&v692[1] = lpMem[1];
                                  LODWORD(v703) = 0;
                                  if ( v43 )
                                  {
                                    do
                                    {
                                      v696 = 0;
                                      v19 = RtlUIntAdd(4, *v59, &v696);
                                      LODWORD(dwBytes) = v19;
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      v19 = RtlULongLongAdd(v60, v696, &v692[1]);
                                      LODWORD(dwBytes) = v19;
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      LODWORD(v703) = v703 + 1;
                                      v59 = *(unsigned int **)&v692[1];
                                    }
                                    while ( (unsigned int)v703 < v61 );
                                  }
                                  v19 = RtlULongLongAdd(v59, 4, &v708);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  if ( (char *)v62 + v63 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                    goto LABEL_28;
                                  *v62 = v63;
                                  if ( v18 )
                                    memcpy_0(v708, v18, v63);
                                }
                                else
                                {
                                  v696 = 0;
                                  v19 = RtlUIntAdd(4, v42, &v696);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(HIDWORD(lpMem[0]), v696, (char *)lpMem + 4);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                }
                                v64 = ++LODWORD(lpMem[0]);
                                LODWORD(v708) = 0;
                                v707 = 0;
                                v65 = v691;
                                if ( v20 )
                                {
                                  if ( !v691 )
                                    goto LABEL_31;
                                }
                                else if ( v691 )
                                {
                                  goto LABEL_31;
                                }
                                v66 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  *(LPVOID *)&v692[1] = lpMem[1];
                                  v696 = 0;
                                  if ( v64 )
                                  {
                                    do
                                    {
                                      v691 = 0;
                                      v19 = RtlUIntAdd(4, *v66, &v691);
                                      LODWORD(dwBytes) = v19;
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      v19 = RtlULongLongAdd(v67, v691, &v692[1]);
                                      LODWORD(dwBytes) = v19;
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      ++v696;
                                      v66 = *(unsigned int **)&v692[1];
                                    }
                                    while ( v696 < v68 );
                                  }
                                  v19 = RtlULongLongAdd(v66, 4, &v708);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  if ( (char *)v69 + v70 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                    goto LABEL_28;
                                  *v69 = v70;
                                  if ( v20 )
                                    memcpy_0(v708, v20, v70);
                                }
                                else
                                {
                                  v691 = 0;
                                  v19 = RtlUIntAdd(4, v65, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(HIDWORD(lpMem[0]), v691, (char *)lpMem + 4);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                }
                                v71 = ++LODWORD(lpMem[0]);
                                LODWORD(v708) = 0;
                                v707 = 0;
                                v72 = (unsigned int *)lpMem[1];
                                if ( lpMem[1] )
                                {
                                  *(LPVOID *)&v692[1] = lpMem[1];
                                  if ( v71 )
                                  {
                                    do
                                    {
                                      v691 = 0;
                                      v19 = RtlUIntAdd(4, *v72, &v691);
                                      LODWORD(dwBytes) = v19;
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      v19 = RtlULongLongAdd(v74, v691, &v692[1]);
                                      LODWORD(dwBytes) = v19;
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      v72 = *(unsigned int **)&v692[1];
                                    }
                                    while ( v76 + 1 < v75 );
                                  }
                                  v19 = RtlULongLongAdd(v72, 4, &v708);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  if ( v77 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                    goto LABEL_28;
                                  *v77 = 8;
                                  *(_QWORD *)v708 = v720;
                                }
                                else
                                {
                                  v691 = 0;
                                  v19 = RtlUIntAdd(4, 8, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(HIDWORD(lpMem[0]), v691, (char *)lpMem + 4);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                }
                                ++LODWORD(lpMem[0]);
                                *(_QWORD *)&v692[1] = 0;
                                if ( StringCchLengthW(
                                       L"TerminalServices-RemoteConnectionManager-b7857721-7a62-4a37-aff3-253fe2b8b0e8-MaxSessions",
                                       v73,
                                       (size_t *)&v692[1]) < 0 )
                                {
                                  v19 = -1073741762;
                                  goto LABEL_32;
                                }
                                v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 1, &v692[1]);
                                LODWORD(dwBytes) = v19;
                                if ( v19 >= 0 )
                                {
                                  LODWORD(v708) = 0;
                                  v707 = 0;
                                  if ( !(2 * v692[1]) )
                                    goto LABEL_31;
                                  v79 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    *(LPVOID *)&v692[1] = lpMem[1];
                                    v696 = 0;
                                    if ( v78 )
                                    {
                                      do
                                      {
                                        v691 = 0;
                                        v19 = RtlUIntAdd(4, *v79, &v691);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 < 0 )
                                          goto LABEL_37;
                                        v19 = RtlULongLongAdd(v81, v691, &v692[1]);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 < 0 )
                                          goto LABEL_37;
                                        ++v696;
                                        v79 = *(unsigned int **)&v692[1];
                                      }
                                      while ( v696 < v82 );
                                    }
                                    v19 = RtlULongLongAdd(v79, 4, &v708);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                    if ( (char *)v83 + v84 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                                      goto LABEL_28;
                                    *v83 = v84;
                                    memcpy_0(
                                      v708,
                                      L"TerminalServices-RemoteConnectionManager-b7857721-7a62-4a37-aff3-253fe2b8b0e8-MaxSessions",
                                      (unsigned int)v84);
                                    v80 = 4;
                                  }
                                  else
                                  {
                                    v691 = 0;
                                    v19 = RtlUIntAdd(4, (unsigned int)(2 * v692[1]), &v691);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                    v19 = RtlUIntAdd(HIDWORD(lpMem[0]), v691, (char *)lpMem + 4);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                  }
                                  v85 = ++LODWORD(lpMem[0]);
                                  LODWORD(v708) = 0;
                                  v707 = 0;
                                  v86 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    *(LPVOID *)&v692[1] = lpMem[1];
                                    if ( v85 )
                                    {
                                      do
                                      {
                                        v691 = 0;
                                        v19 = RtlUIntAdd(4, *v86, &v691);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 < 0 )
                                          goto LABEL_37;
                                        v19 = RtlULongLongAdd(v88, v691, &v692[1]);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 < 0 )
                                          goto LABEL_37;
                                        v86 = *(unsigned int **)&v692[1];
                                      }
                                      while ( v90 + 1 < v89 );
                                    }
                                    v19 = RtlULongLongAdd(v86, 4, &v708);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                    if ( v91 + 2 > (unsigned int *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                      goto LABEL_28;
                                    *v91 = v87;
                                    *v708 = 0;
                                  }
                                  else
                                  {
                                    v691 = 0;
                                    v19 = RtlUIntAdd(v80, v80, &v691);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                    v19 = RtlUIntAdd(HIDWORD(lpMem[0]), v691, (char *)lpMem + 4);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                  }
                                  v92 = ++LODWORD(lpMem[0]);
                                  LODWORD(v708) = 0;
                                  v707 = 0;
                                  v93 = (unsigned int *)lpMem[1];
                                  if ( lpMem[1] )
                                  {
                                    *(LPVOID *)&v692[1] = lpMem[1];
                                    if ( v92 )
                                    {
                                      do
                                      {
                                        v691 = 0;
                                        v19 = RtlUIntAdd(4, *v93, &v691);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 < 0 )
                                          goto LABEL_37;
                                        v19 = RtlULongLongAdd(v95, v691, &v692[1]);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 < 0 )
                                          goto LABEL_37;
                                        v93 = *(unsigned int **)&v692[1];
                                      }
                                      while ( v97 + 1 < v96 );
                                    }
                                    v19 = RtlULongLongAdd(v93, 4, &v708);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                    if ( v98 + 2 > (unsigned int *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                                      goto LABEL_28;
                                    *v98 = v94;
                                    *v708 = v94;
                                  }
                                  else
                                  {
                                    v691 = 0;
                                    v19 = RtlUIntAdd(v87, v87, &v691);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                    v19 = RtlUIntAdd(HIDWORD(lpMem[0]), v691, (char *)lpMem + 4);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_37;
                                  }
                                  ++LODWORD(lpMem[0]);
                                  v691 = 0;
                                  v19 = RtlUIntAdd(v94, v94, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v695 = v691;
                                  v691 = 0;
                                  v19 = RtlUIntAdd(v99, 8, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(v100, v691, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v691 = 0;
                                  v19 = RtlUIntAdd(v101, v101, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(v695, v691, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v691 = 0;
                                  v19 = RtlUIntAdd(v102, v102, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(v695, v691, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v691 = 0;
                                  v19 = RtlUIntAdd(v103, v103, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(v695, v691, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v691 = 0;
                                  v19 = RtlUIntAdd(v104, v104, &v691);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v19 = RtlUIntAdd(v695, v691, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_37;
                                  v696 = 0;
                                  HIDWORD(dwBytes) = v695;
                                  v694 = 0;
                                  v713 = __rdtsc();
                                  v693 = 0;
                                  v723 = 8;
                                  v106 = RtlUIntAdd(8, HIDWORD(lpMem[0]), &v723);
                                  if ( v106 < 0 )
                                  {
                                    v702 = v20;
                                    v715 = v18;
                                  }
                                  else
                                  {
                                    v107 = (v723 + 7) & 0xFFFFFFF8;
                                    if ( v107 < v723 )
                                    {
                                      v19 = -805306219;
                                      goto LABEL_240;
                                    }
                                    v723 = (v723 + 7) & 0xFFFFFFF8;
                                    v108 = v107;
                                    v109 = GetProcessHeap();
                                    v110 = HeapAlloc(v109, 8u, v108);
                                    v710 = v110;
                                    if ( !v110 )
                                    {
                                      v19 = -805306345;
                                      LODWORD(dwBytes) = -805306345;
LABEL_237:
                                      if ( v19 < 0 )
                                        goto LABEL_37;
                                      if ( !v696 )
                                        goto LABEL_239;
                                      if ( !v706 )
                                        goto LABEL_31;
                                      v713 = (SIZE_T)v706;
                                      v19 = RtlULongLongAdd(v706, 4, &v713);
                                      LODWORD(dwBytes) = v19;
                                      v706 = v351;
                                      if ( v19 >= 0 )
                                      {
                                        v353 = (int *)v713;
                                        if ( !*v351 )
                                          v353 = 0;
                                        if ( *v351 != 4 )
                                          goto LABEL_28;
                                        v19 = *v353;
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 == -805306333 )
                                        {
                                          v354 = -2147024774;
                                          v692[0] = -2147024774;
                                        }
                                        else
                                        {
                                          v354 = v19;
                                          v692[0] = v19;
                                          if ( v19 != -2147024774 && v19 < 0 )
                                            goto LABEL_37;
                                        }
                                        v706 = v351;
                                        if ( v352 != 6 )
                                        {
LABEL_239:
                                          v19 = -1073425151;
                                          goto LABEL_240;
                                        }
                                        *(_QWORD *)&v692[1] = v350;
                                        do
                                        {
                                          v19 = RtlULongLongAdd(v350, 4, &v692[1]);
                                          LODWORD(dwBytes) = v19;
                                          if ( v19 < 0 )
                                            goto LABEL_37;
                                          v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v355, &v692[1]);
                                          LODWORD(dwBytes) = v19;
                                          if ( v19 < 0 )
                                            goto LABEL_37;
                                          v350 = *(_QWORD *)&v692[1];
                                        }
                                        while ( v356 == -1 );
                                        v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                        LODWORD(dwBytes) = v19;
                                        if ( v19 >= 0 )
                                        {
                                          v359 = *(LPVOID **)&v692[1];
                                          if ( !v358 )
                                            v359 = 0;
                                          if ( v358 != 8 )
                                            goto LABEL_28;
                                          v692[0] = v354;
                                          v706 = v357;
                                          if ( !v357 )
                                            goto LABEL_31;
                                          v360 = v357;
                                          *(_QWORD *)&v692[1] = v357;
                                          v707 = *v359;
                                          do
                                          {
                                            v19 = RtlULongLongAdd(v360, 4, &v692[1]);
                                            LODWORD(dwBytes) = v19;
                                            if ( v19 < 0 )
                                              goto LABEL_37;
                                            v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v361, &v692[1]);
                                            LODWORD(dwBytes) = v19;
                                            if ( v19 < 0 )
                                              goto LABEL_37;
                                            v360 = *(void **)&v692[1];
                                          }
                                          while ( (unsigned int)(v362 + 1) < 2 );
                                          v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                          LODWORD(dwBytes) = v19;
                                          if ( v19 < 0 )
                                            goto LABEL_37;
                                          v365 = *(unsigned int **)&v692[1];
                                          if ( !v364 )
                                            v365 = 0;
                                          if ( v364 != 4 )
                                            goto LABEL_28;
                                          v692[0] = v354;
                                          v706 = v363;
                                          if ( !v363 )
                                          {
LABEL_31:
                                            v19 = -1073741811;
                                            goto LABEL_32;
                                          }
                                          v366 = v363;
                                          *(_QWORD *)&v692[1] = v363;
                                          v693 = *v365;
                                          do
                                          {
                                            v19 = RtlULongLongAdd(v366, 4, &v692[1]);
                                            LODWORD(dwBytes) = v19;
                                            if ( v19 < 0 )
                                              goto LABEL_37;
                                            v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v367, &v692[1]);
                                            LODWORD(dwBytes) = v19;
                                            if ( v19 < 0 )
                                              goto LABEL_37;
                                            v366 = *(void **)&v692[1];
                                          }
                                          while ( (unsigned int)(v368 + 1) < 3 );
                                          v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                          LODWORD(dwBytes) = v19;
                                          if ( v19 >= 0 )
                                          {
                                            v371 = 0;
                                            if ( v370 )
                                              v371 = *(const void **)&v692[1];
                                            v372 = v369;
                                            *(_QWORD *)&v692[1] = v369;
                                            do
                                            {
                                              v709 = *v372;
                                              v19 = RtlULongLongAdd(v372, 4, &v692[1]);
                                              LODWORD(dwBytes) = v19;
                                              if ( v19 < 0 )
                                                goto LABEL_37;
                                              v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v709, &v692[1]);
                                              LODWORD(dwBytes) = v19;
                                              if ( v19 < 0 )
                                                goto LABEL_37;
                                              v372 = *(unsigned int **)&v692[1];
                                            }
                                            while ( (unsigned int)(v373 + 1) < 4 );
                                            v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                            LODWORD(dwBytes) = v19;
                                            if ( v19 >= 0 )
                                            {
                                              v376 = *(unsigned int **)&v692[1];
                                              if ( !v375 )
                                                v376 = 0;
                                              if ( v375 != 4 )
                                                goto LABEL_28;
                                              v706 = v374;
                                              if ( !v374 )
                                              {
                                                v19 = -1073741811;
                                                goto LABEL_240;
                                              }
                                              v377 = v374;
                                              *(_QWORD *)&v692[1] = v374;
                                              v709 = *v376;
                                              do
                                              {
                                                v19 = RtlULongLongAdd(v377, 4, &v692[1]);
                                                LODWORD(dwBytes) = v19;
                                                if ( v19 < 0 )
                                                  goto LABEL_37;
                                                v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v378, &v692[1]);
                                                LODWORD(dwBytes) = v19;
                                                if ( v19 < 0 )
                                                  goto LABEL_37;
                                                v377 = *(void **)&v692[1];
                                              }
                                              while ( (unsigned int)(v379 + 1) < 5 );
                                              v44 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                              v19 = v44;
                                              LODWORD(dwBytes) = v44;
                                              if ( v44 < 0 )
                                              {
LABEL_36:
                                                LODWORD(dwBytes) = v44;
                                                goto LABEL_37;
                                              }
                                              v383 = *(int **)&v692[1];
                                              if ( !v380 )
                                                v383 = 0;
                                              if ( v380 != v381 )
                                              {
                                                v19 = -1073741789;
                                                goto LABEL_240;
                                              }
                                              if ( (LPVOID)v720 != v707 )
                                                goto LABEL_239;
                                              v730 = *v383;
                                              v732 = v693;
                                              if ( v709 > v381 || (unsigned int)v382 > v381 )
                                              {
                                                v19 = -2147024774;
                                                goto LABEL_240;
                                              }
                                              memcpy_0(v738, v371, v382);
                                              v44 = v692[0];
                                              if ( v692[0] )
                                              {
                                                v19 = v692[0];
                                                goto LABEL_36;
                                              }
                                            }
                                          }
                                        }
                                      }
                                      goto LABEL_37;
                                    }
                                    v715 = v18;
                                    v702 = v20;
                                    *(_QWORD *)&v692[1] = v110;
                                    *v110 = lpMem[0];
                                    v106 = RtlULongLongAdd(v110, 4, &v692[1]);
                                    if ( v106 < 0 )
                                    {
                                      v710 = v112;
                                    }
                                    else
                                    {
                                      v114 = *(_QWORD *)&v692[1];
                                      **(_DWORD **)&v692[1] = HIDWORD(lpMem[0]);
                                      v106 = RtlULongLongAdd(v114, v113, &v692[1]);
                                      if ( v106 >= 0 )
                                      {
                                        *(_QWORD *)(v723 + v115 - 8) = v713;
                                        memcpy_0(*(void **)&v692[1], lpMem[1], HIDWORD(lpMem[0]));
                                        v694 = v710;
                                        v105 = v723;
                                        goto LABEL_149;
                                      }
                                    }
                                    v715 = v18;
                                    v702 = v20;
                                    HIDWORD(dwBytes) = v111;
                                    v116 = GetProcessHeap();
                                    HeapFree(v116, 0, v710);
                                    v105 = v693;
                                  }
LABEL_149:
                                  v117 = 0;
                                  pcchLength = 0;
                                  v118 = 0;
                                  v705 = 0;
                                  v700 = 0;
                                  v714 = 0;
                                  v19 = v106 | 0x10000000;
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                  {
LABEL_212:
                                    v197 = v694;
                                    goto LABEL_213;
                                  }
                                  v119 = (unsigned __int8 *)v694;
                                  if ( !v694 )
                                  {
                                    v19 = -805306355;
                                    LODWORD(dwBytes) = -805306355;
                                    goto LABEL_37;
                                  }
                                  v713 = v105;
                                  if ( !v105 || (Size = v105 + 8LL, v120 = MemoryAlloc(Size), (Src = v120) == 0) )
                                  {
                                    v19 = -805306367;
                                    LODWORD(dwBytes) = -805306367;
                                    goto LABEL_214;
                                  }
                                  v710 = 0;
                                  v121 = 0;
                                  v697 = 0;
                                  v122 = 0;
                                  v123 = v713;
                                  if ( v713 )
                                  {
                                    do
                                      v121 ^= v119[v122++];
                                    while ( v122 < v713 );
                                    v697 = v121;
                                  }
                                  v704 = (LPVOID)0xC81ECB17B1B54A58LL;
                                  v124 = v119;
                                  *(_QWORD *)&v692[1] = v119;
                                  v725 = v120;
                                  v125 = v713 & 7;
                                  if ( (v713 & 7) != 0 )
                                  {
                                    v695 = 0;
                                    LODWORD(dwBytes) = 0;
                                    v126 = 0;
                                    v127 = 0;
                                    v128 = 0;
                                    do
                                    {
                                      v129 = *v124++;
                                      v691 = 8 * v126;
                                      if ( v126 >= 4 )
                                        v127 |= v129 << (56 - v691);
                                      else
                                        v128 |= v129 << (24 - v691);
                                      ++v126;
                                    }
                                    while ( (int)v126 < (int)v125 );
                                    LODWORD(dwBytes) = v128;
                                    v695 = v127;
                                    *(_QWORD *)&v692[1] = v124;
                                    v694 = v119;
                                    v702 = v20;
                                    v715 = v18;
                                    v130 = v128 ^ 0xB17A307A;
                                    v131 = v127 ^ 0x42F6B18D;
                                    v132 = v128 ^ 0xB17A307A;
                                    v133 = v127 ^ 0x42F6B18D;
                                    v691 = 0;
                                    if ( (v713 & 7) != 0 )
                                    {
                                      v134 = v725;
                                      do
                                      {
                                        v716 = (SIZE_T)(v134 + 1);
                                        if ( v691 >= 4 )
                                        {
                                          v133 = __ROR4__(v133, 24);
                                          v135 = v133;
                                        }
                                        else
                                        {
                                          v132 = __ROR4__(v132, 24);
                                          v135 = v132;
                                        }
                                        *v134 = v135;
                                        ++v691;
                                        v134 = (_BYTE *)v716;
                                      }
                                      while ( (int)v691 < (int)v125 );
                                      v725 = (LPVOID)v716;
                                    }
                                    if ( v125 <= 4 )
                                    {
                                      v136 = 0;
                                      if ( v125 < 4 )
                                        v130 = v130 >> (8 * (4 - v125)) << (8 * (4 - v125));
                                    }
                                    else
                                    {
                                      v136 = v131 >> (8 * (8 - v125)) << (8 * (8 - v125));
                                    }
                                    v124 = *(unsigned __int8 **)&v692[1];
                                  }
                                  else
                                  {
                                    v130 = 0;
                                    v136 = -1;
                                    LODWORD(dwBytes) = 0;
                                    v695 = 0;
                                  }
                                  if ( v123 >> 3 )
                                  {
                                    v716 = 0;
                                    v691 = 19032;
                                    v693 = WORD1(v704);
                                    v137 = WORD2(v704);
                                    LODWORD(v703) = HIWORD(v704);
                                    v709 = HIDWORD(v704) ^ 0xB1B54A58;
                                    v138 = v725;
                                    v139 = v123 >> 3;
                                    v140 = v695;
                                    v141 = dwBytes;
                                    v142 = HIDWORD(v704) ^ 0xB1B54A58;
                                    do
                                    {
                                      v143 = v124[3] | ((v124[2] | (((*v124 << 8) | v124[1]) << 8)) << 8);
                                      v144 = *(unsigned __int8 *)(*(_QWORD *)&v692[1] + 7LL)
                                           | ((*(unsigned __int8 *)(*(_QWORD *)&v692[1] + 6LL)
                                             | ((*(unsigned __int8 *)(*(_QWORD *)&v692[1] + 5LL) | (v124[4] << 8)) << 8)) << 8);
                                      v145 = v136 ^ v144;
                                      *(_QWORD *)&v692[1] += 8LL;
                                      v146 = v130 ^ v143 ^ HIDWORD(v704) ^ ((v136 ^ v144) - v691);
                                      v147 = v145
                                           ^ (__ROR4__(v146, 7) + WORD1(v704) * __ROR4__(HIDWORD(v704) ^ v146, 15));
                                      v148 = v146 ^ (v137 * __ROR4__(v147 - 1313519016, 9) - __ROR4__(v147, 10));
                                      v149 = v147 ^ (__ROR4__(v148, 27) + HIWORD(v704) * __ROR4__(v137 ^ v148, 28));
                                      v150 = v148 ^ (HIDWORD(v704) - (v149 ^ 0xB1B54A58));
                                      v151 = v149 ^ (WORD1(v704) * (v150 - v691) - (v150 >> 6));
                                      v152 = v150 ^ (v691 * (v137 ^ __ROR4__(v151, 15)));
                                      v153 = v151 ^ (v137 * (HIWORD(v704) + __ROR4__(~v152, 3)));
                                      v154 = v153
                                           ^ (v693 * (v703 ^ v152 ^ (v153 - v691 - HIDWORD(v704))))
                                           ^ __ROR4__(v152 ^ (v153 - v691 - HIDWORD(v704)), 10);
                                      v155 = v152
                                           ^ (v153 - v691 - HIDWORD(v704))
                                           ^ __ROR4__(v154, 3)
                                           ^ (v137 * __ROR4__(v691 ^ v154, 26));
                                      v156 = v154 ^ (v691 * (__ROR4__(v155, 15) - HIWORD(v704)));
                                      v157 = v155
                                           ^ (v691 * (v703 ^ v156))
                                           ^ ((v156 ^ (v156 >> 14)) >> 1)
                                           ^ (v691 * (((v156 - v137) >> 29) | (8 * (v156 - v137))));
                                      v158 = v156 ^ (WORD1(v704) * (v157 - v137) - (v157 >> 13));
                                      v159 = v157 ^ __ROR4__(v158, 11) ^ (v137 * __ROR4__(-1313519016 - v158, 9));
                                      v160 = v158 ^ (v159 - HIWORD(v704) + 1313519016);
                                      v161 = v159 ^ (v691 * (v693 ^ v160) - __ROR4__(v160, 7));
                                      v162 = v160
                                           ^ (WORD1(v704) * __ROR4__(HIWORD(v704) ^ v161, 28) - __ROR4__(v161, 16));
                                      v163 = v161 ^ (__ROR4__(v162, 4) + v137 * __ROR4__(-1313519016 - v162, 10));
                                      v164 = v162 ^ __ROR4__(v163, 9) ^ (HIWORD(v704) * __ROR4__(v163 + 1313519016, 4));
                                      v165 = v163 ^ (v691 * __ROR4__(HIDWORD(v704) ^ v164, 24) - __ROR4__(v164, 30));
                                      v166 = v164
                                           ^ (WORD1(v704) * __ROR4__(HIDWORD(v704) - v165, 11) - __ROR4__(v165, 12));
                                      v167 = v165 ^ (v166 >> 8) ^ (v137 * (v166 ^ WORD1(v704)));
                                      v130 = v141 ^ v167;
                                      v136 = v166 ^ v142 ^ v140 ^ v167;
                                      v138[3] = v130;
                                      v138[7] = v136;
                                      v138[2] = __ROR4__(v130, 8);
                                      v138[6] = __ROR4__(v136, 8);
                                      v138[1] = __ROR4__(v130, 16);
                                      v138[5] = __ROR4__(v136, 16);
                                      *v138 = __ROR4__(v130, 24);
                                      v138[4] = __ROR4__(v136, 24);
                                      v141 = v143;
                                      v140 = v144;
                                      v138 += 8;
                                      ++v716;
                                      v124 = *(unsigned __int8 **)&v692[1];
                                    }
                                    while ( v716 < v139 );
                                    v121 = v697;
                                    v18 = v715;
                                    v20 = v702;
                                    v118 = (unsigned int *)v705;
                                    v117 = (unsigned int *)v705;
                                    v119 = (unsigned __int8 *)v694;
                                    v123 = v713;
                                  }
                                  *(_QWORD *)((char *)Src + v123) = v121;
                                  v168 = GetProcessHeap();
                                  v169 = HeapAlloc(v168, 8u, 0x30u);
                                  v702 = v169;
                                  if ( !v169 )
                                  {
                                    v170 = -1073741801;
                                    goto LABEL_195;
                                  }
                                  *v169 = Size;
                                  v171 = GetProcessHeap();
                                  v172 = HeapAlloc(v171, 8u, (unsigned int)Size);
                                  if ( v172 )
                                  {
                                    v694 = v119;
                                    v173 = v702;
                                    *((_QWORD *)v702 + 1) = v172;
                                    memcpy_0(v172, Src, (unsigned int)Size);
                                    v173[4] = 160;
                                    v174 = GetProcessHeap();
                                    v175 = HeapAlloc(v174, 8u, 0xA0u);
                                    v176 = v702;
                                    if ( v175 )
                                    {
                                      *((_QWORD *)v702 + 3) = v175;
                                      *v175 = xmmword_1800DF490;
                                      v175[1] = xmmword_1800DF4A0;
                                      v175[2] = xmmword_1800DF4B0;
                                      v175[3] = xmmword_1800DF4C0;
                                      v175[4] = xmmword_1800DF4D0;
                                      v175[5] = xmmword_1800DF4E0;
                                      v175[6] = xmmword_1800DF4F0;
                                      v175[7] = xmmword_1800DF500;
                                      v175[8] = xmmword_1800DF510;
                                      v175[9] = xmmword_1800DF520;
                                      v176[8] = 8;
                                      v177 = GetProcessHeap();
                                      v178 = HeapAlloc(v177, 8u, 8u);
                                      if ( v178 )
                                      {
                                        v184 = (unsigned int *)v702;
                                        *((_QWORD *)v702 + 5) = v178;
                                        *v178 = qword_1800DF530;
                                        v170 = 0;
                                        v117 = v184;
                                        v710 = 0;
                                        goto LABEL_195;
                                      }
                                      v176 = v702;
                                    }
                                    v702 = v176;
                                  }
                                  v170 = -1073741801;
                                  v179 = v702;
                                  v707 = (LPVOID)*((_QWORD *)v702 + 1);
                                  if ( v707 )
                                  {
                                    v180 = GetProcessHeap();
                                    HeapFree(v180, 0, v707);
                                    v179 = v702;
                                    *((_QWORD *)v702 + 1) = 0;
                                  }
                                  v707 = (LPVOID)v179[3];
                                  if ( v707 )
                                  {
                                    v181 = GetProcessHeap();
                                    HeapFree(v181, 0, v707);
                                    v179 = v702;
                                    *((_QWORD *)v702 + 3) = 0;
                                  }
                                  v707 = (LPVOID)v179[5];
                                  if ( v707 )
                                  {
                                    v182 = GetProcessHeap();
                                    HeapFree(v182, 0, v707);
                                    *((_QWORD *)v702 + 5) = 0;
                                  }
                                  v183 = GetProcessHeap();
                                  HeapFree(v183, 0, v702);
LABEL_195:
                                  v185 = GetProcessHeap();
                                  HeapFree(v185, 0, Src);
                                  v186 = v710;
                                  if ( v710 )
                                  {
                                    v707 = (LPVOID)*((_QWORD *)v710 + 1);
                                    if ( v707 )
                                    {
                                      v187 = GetProcessHeap();
                                      HeapFree(v187, 0, v707);
                                      v186 = v710;
                                      *((_QWORD *)v710 + 1) = 0;
                                    }
                                    v707 = (LPVOID)v186[3];
                                    if ( v707 )
                                    {
                                      v188 = GetProcessHeap();
                                      HeapFree(v188, 0, v707);
                                      v186 = v710;
                                      *((_QWORD *)v710 + 3) = 0;
                                    }
                                    v707 = (LPVOID)v186[5];
                                    if ( v707 )
                                    {
                                      v189 = GetProcessHeap();
                                      HeapFree(v189, 0, v707);
                                      *((_QWORD *)v710 + 5) = 0;
                                    }
                                    v190 = GetProcessHeap();
                                    HeapFree(v190, 0, v710);
                                  }
                                  v19 = v170 | 0x10000000;
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                  {
                                    v197 = v694;
LABEL_213:
                                    if ( !v197 )
                                    {
LABEL_215:
                                      if ( v117 )
                                      {
                                        v707 = (LPVOID)*((_QWORD *)v117 + 1);
                                        if ( v707 )
                                        {
                                          v199 = GetProcessHeap();
                                          HeapFree(v199, 0, v707);
                                          *((_QWORD *)v117 + 1) = 0;
                                        }
                                        v707 = (LPVOID)*((_QWORD *)v117 + 3);
                                        if ( v707 )
                                        {
                                          v200 = GetProcessHeap();
                                          HeapFree(v200, 0, v707);
                                          *((_QWORD *)v117 + 3) = 0;
                                        }
                                        v707 = (LPVOID)*((_QWORD *)v117 + 5);
                                        if ( v707 )
                                        {
                                          v201 = GetProcessHeap();
                                          HeapFree(v201, 0, v707);
                                          *((_QWORD *)v117 + 5) = 0;
                                        }
                                        v202 = GetProcessHeap();
                                        HeapFree(v202, 0, v117);
                                      }
                                      v203 = (void *)pcchLength;
                                      if ( pcchLength )
                                      {
                                        v204 = GetProcessHeap();
                                        HeapFree(v204, 0, v203);
                                      }
                                      if ( v118 )
                                      {
                                        v205 = GetProcessHeap();
                                        HeapFree(v205, 0, v118);
                                      }
                                      v206 = v700;
                                      if ( v700 )
                                      {
                                        v207 = (void *)*((_QWORD *)v700 + 1);
                                        if ( v207 )
                                        {
                                          v208 = GetProcessHeap();
                                          HeapFree(v208, 0, v207);
                                          v206[1] = 0;
                                        }
                                        v209 = (void *)v206[3];
                                        if ( v209 )
                                        {
                                          v210 = GetProcessHeap();
                                          HeapFree(v210, 0, v209);
                                          v206[3] = 0;
                                        }
                                        v211 = (void *)v206[5];
                                        if ( v211 )
                                        {
                                          v212 = GetProcessHeap();
                                          HeapFree(v212, 0, v211);
                                          v206[5] = 0;
                                        }
                                        v213 = GetProcessHeap();
                                        HeapFree(v213, 0, v206);
                                      }
                                      v214 = v714;
                                      if ( v714 )
                                      {
                                        v215 = GetProcessHeap();
                                        HeapFree(v215, 0, v214);
                                      }
                                      goto LABEL_237;
                                    }
LABEL_214:
                                    v198 = GetProcessHeap();
                                    HeapFree(v198, 0, v694);
                                    goto LABEL_215;
                                  }
                                  v693 = 0;
                                  LODWORD(dwBytes) = 4;
                                  v192 = RtlUIntAdd(4, *v117, &dwBytes);
                                  if ( v192 >= 0 )
                                  {
                                    v192 = RtlUIntAdd((unsigned int)dwBytes, v191, &dwBytes);
                                    if ( v192 >= 0 )
                                    {
                                      v713 = (SIZE_T)(v117 + 4);
                                      v192 = RtlUIntAdd((unsigned int)dwBytes, v117[4], &dwBytes);
                                      if ( v192 >= 0 )
                                      {
                                        v192 = RtlUIntAdd((unsigned int)dwBytes, v193, &dwBytes);
                                        if ( v192 >= 0 )
                                        {
                                          v716 = (SIZE_T)(v117 + 8);
                                          v192 = RtlUIntAdd((unsigned int)dwBytes, v117[8], &dwBytes);
                                          if ( v192 >= 0 )
                                          {
                                            v699 = v117;
                                            v194 = dwBytes;
                                            v195 = GetProcessHeap();
                                            v196 = HeapAlloc(v195, 8u, v194);
                                            v702 = v196;
                                            v117 = v699;
                                            if ( !v196 )
                                            {
                                              v19 = -805306345;
LABEL_211:
                                              LODWORD(dwBytes) = v19;
                                              goto LABEL_212;
                                            }
                                            v705 = v196;
                                            *v196 = *v699;
                                            v192 = RtlULongLongAdd(v196, 4, &v705);
                                            if ( v192 < 0 )
                                            {
                                              v694 = v217;
                                              HIDWORD(dwBytes) = v218;
                                              v702 = v216;
                                            }
                                            else
                                            {
                                              memcpy_0(v705, *((const void **)v117 + 1), *v117);
                                              v192 = RtlULongLongAdd(v705, *v117, &v705);
                                              if ( v192 >= 0 )
                                              {
                                                v219 = v705;
                                                *(_DWORD *)v705 = *(_DWORD *)v713;
                                                v192 = RtlULongLongAdd(v219, 4, &v705);
                                                if ( v192 >= 0 )
                                                {
                                                  memcpy_0(v705, *((const void **)v117 + 3), *v220);
                                                  v192 = RtlULongLongAdd(v705, *(unsigned int *)v713, &v705);
                                                  if ( v192 >= 0 )
                                                  {
                                                    v221 = v705;
                                                    *(_DWORD *)v705 = *(_DWORD *)v716;
                                                    v192 = RtlULongLongAdd(v221, 4, &v705);
                                                    if ( v192 >= 0 )
                                                    {
                                                      memcpy_0(v705, *((const void **)v117 + 5), *v222);
                                                      v192 = RtlULongLongAdd(v705, *(unsigned int *)v716, &v705);
                                                      if ( v192 >= 0 )
                                                      {
                                                        pcchLength = (size_t)v702;
                                                        v693 = dwBytes;
                                                        goto LABEL_252;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                            v223 = GetProcessHeap();
                                            HeapFree(v223, 0, v702);
                                          }
                                        }
                                      }
                                    }
                                  }
LABEL_252:
                                  v19 = v192 | 0x10000000;
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v726 = 8;
                                  v224 = RtlUIntAdd(8, HIDWORD(dwBytes), &v726);
                                  v19 = v224 | 0x10000000;
                                  LODWORD(dwBytes) = v224 | 0x10000000;
                                  if ( v224 < 0 )
                                    goto LABEL_212;
                                  v225 = (v726 + 7) & 0xFFFFFFF8;
                                  if ( (unsigned int)v225 < v726 )
                                  {
                                    v19 = -1073741675;
                                    goto LABEL_211;
                                  }
                                  v729 = (v726 + 7) & 0xFFFFFFF8;
                                  v19 = RtlUIntAdd(v225, 8, &v729);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v715 = v18;
                                  v702 = v20;
                                  v694 = v226;
                                  v699 = v117;
                                  v691 = 0;
                                  v227 = lpMem[1];
                                  if ( !lpMem[1] )
                                    goto LABEL_265;
                                  v699 = v117;
                                  v694 = v226;
                                  v702 = v20;
                                  v715 = v18;
                                  if ( LODWORD(lpMem[0]) <= 1 )
                                    goto LABEL_265;
                                  *(LPVOID *)&v692[1] = lpMem[1];
                                  do
                                  {
                                    v19 = RtlULongLongAdd(v227, 4, &v692[1]);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_212;
                                    v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v228, &v692[1]);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_212;
                                    v227 = *(LPVOID *)&v692[1];
                                  }
                                  while ( v229 == -1 );
                                  v709 = **(_DWORD **)&v692[1];
                                  v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v230 = lpMem[1];
                                  if ( !lpMem[1] || LODWORD(lpMem[0]) <= 2 )
                                  {
LABEL_265:
                                    v19 = -1073741811;
                                    LODWORD(dwBytes) = -1073741811;
                                    goto LABEL_212;
                                  }
                                  *(LPVOID *)&v692[1] = lpMem[1];
                                  do
                                  {
                                    v19 = RtlULongLongAdd(v230, 4, &v692[1]);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_212;
                                    v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], v234, &v692[1]);
                                    LODWORD(dwBytes) = v19;
                                    if ( v19 < 0 )
                                      goto LABEL_212;
                                    v230 = *(LPVOID *)&v692[1];
                                  }
                                  while ( (unsigned int)(v235 + 1) < 2 );
                                  v19 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v691 = v236;
                                  v695 = v237;
                                  v19 = RtlUIntAdd(v237, v729, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v19 = RtlUIntAdd(v695, v238, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v19 = RtlUIntAdd(v695, v709, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v19 = RtlUIntAdd(v695, v239, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v19 = RtlUIntAdd(v695, v240, &v695);
                                  LODWORD(dwBytes) = v19;
                                  if ( v19 < 0 )
                                    goto LABEL_212;
                                  v691 = v695;
                                  if ( v695 > 0x400000 )
                                  {
                                    v19 = -2147418113;
                                    goto LABEL_211;
                                  }
                                  v231 = v695;
                                  v232 = GetProcessHeap();
                                  v233 = (unsigned int *)HeapAlloc(v232, 8u, v231);
                                  v118 = v233;
                                  if ( !v233 )
                                  {
                                    v19 = -805306345;
LABEL_269:
                                    LODWORD(dwBytes) = v19;
LABEL_270:
                                    v117 = v699;
                                    goto LABEL_212;
                                  }
                                  v743 = 0;
                                  v744 = 0;
                                  phModule = 0;
                                  if ( !pcchLength )
                                  {
                                    v19 = -2147024809;
                                    goto LABEL_269;
                                  }
                                  *(_QWORD *)&v743 = pcchLength;
                                  LODWORD(v744) = v693;
                                  *((_QWORD *)&v743 + 1) = v233;
                                  *(_QWORD *)((char *)&v744 + 4) = v691;
                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                    && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                  {
                                    v243 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v743);
                                    v19 = v243 | 0x10000000;
                                    LODWORD(dwBytes) = v243 | 0x10000000;
                                    if ( v243 >= 0 )
                                    {
                                      v244 = DWORD1(v744);
                                      goto LABEL_300;
                                    }
                                  }
                                  else
                                  {
                                    LastError = GetLastError();
                                    LODWORD(dwBytes) = LastError;
                                    v19 = LastError;
                                    if ( LastError > 0 )
                                    {
                                      v19 = (unsigned __int16)LastError | 0x80070000;
                                      LODWORD(dwBytes) = v19;
                                    }
                                    if ( v19 >= 0 )
                                    {
                                      v19 = -2147467259;
                                      goto LABEL_269;
                                    }
                                  }
                                  if ( v19 == -805306333 )
                                  {
                                    v19 = -2147024774;
                                    goto LABEL_269;
                                  }
                                  if ( v19 < 0 )
                                    goto LABEL_270;
                                  v244 = v691;
LABEL_300:
                                  HIDWORD(dwBytes) = 0;
                                  v705 = v118;
                                  if ( v244 < 4 )
                                  {
LABEL_301:
                                    v19 = -805306306;
                                    goto LABEL_269;
                                  }
                                  v245 = *v118;
                                  v709 = *v118;
                                  v247 = RtlULongLongAdd(v118, 4, &v705);
                                  if ( v247 >= 0 )
                                  {
                                    v247 = RtlUIntAdd(0, v246, (char *)&dwBytes + 4);
                                    if ( v247 < 0 )
                                    {
LABEL_354:
                                      v705 = v118;
                                      v117 = v699;
                                      goto LABEL_355;
                                    }
                                    if ( v249 - HIDWORD(dwBytes) < (unsigned int)v245 )
                                      goto LABEL_301;
                                    v716 = (SIZE_T)v705;
                                    v713 = v245;
                                    v247 = RtlULongLongAdd(v705, (unsigned int)v245, &v705);
                                    if ( v247 >= 0 )
                                    {
                                      v247 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v245, (char *)&dwBytes + 4);
                                      if ( v247 >= 0 )
                                      {
                                        if ( v250 - HIDWORD(dwBytes) < (unsigned int)v251 )
                                          goto LABEL_301;
                                        v693 = *(_DWORD *)v705;
                                        v247 = RtlULongLongAdd(v705, v251, &v705);
                                        if ( v247 >= 0 )
                                        {
                                          v247 = RtlUIntAdd(HIDWORD(dwBytes), v252, (char *)&dwBytes + 4);
                                          if ( v247 >= 0 )
                                          {
                                            if ( v253 - HIDWORD(dwBytes) < (unsigned int)v254 )
                                              goto LABEL_301;
                                            Size = (SIZE_T)v705;
                                            Src = v254;
                                            v247 = RtlULongLongAdd(v705, (unsigned int)v254, &v705);
                                            if ( v247 >= 0 )
                                            {
                                              v247 = RtlUIntAdd(HIDWORD(dwBytes), v255, (char *)&dwBytes + 4);
                                              if ( v247 >= 0 )
                                              {
                                                if ( v256 - HIDWORD(dwBytes) < v257 )
                                                  goto LABEL_301;
                                                v691 = *(_DWORD *)v705;
                                                v247 = RtlULongLongAdd(v705, 4, &v705);
                                                if ( v247 >= 0 )
                                                {
                                                  v247 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                  if ( v247 >= 0 )
                                                  {
                                                    if ( v258 - HIDWORD(dwBytes) < v259 )
                                                      goto LABEL_301;
                                                    v247 = RtlUIntAdd(HIDWORD(dwBytes), v259, (char *)&dwBytes + 4);
                                                    if ( v247 >= 0 )
                                                    {
                                                      if ( v260 != HIDWORD(dwBytes)
                                                        || (unsigned int)(v261 + v262 + v245) + 12LL != v260 )
                                                      {
                                                        goto LABEL_301;
                                                      }
                                                      v263 = GetProcessHeap();
                                                      v264 = HeapAlloc(v263, 8u, 0x30u);
                                                      v704 = v264;
                                                      v117 = v699;
                                                      v197 = v694;
                                                      if ( !v264 )
                                                      {
                                                        v700 = 0;
                                                        v19 = -805306345;
                                                        LODWORD(dwBytes) = -805306345;
                                                        goto LABEL_213;
                                                      }
                                                      v715 = v18;
                                                      v702 = v20;
                                                      *(_QWORD *)&v692[1] = 0;
                                                      if ( v716 )
                                                      {
                                                        *v264 = v709;
                                                        v265 = GetProcessHeap();
                                                        v266 = HeapAlloc(v265, 8u, v713);
                                                        if ( !v266 )
                                                        {
LABEL_333:
                                                          v247 = -1073741801;
                                                          v705 = v118;
                                                          v274 = v704;
                                                          v707 = (LPVOID)*((_QWORD *)v704 + 1);
                                                          if ( v707 )
                                                          {
                                                            v275 = GetProcessHeap();
                                                            HeapFree(v275, 0, v707);
                                                            v274 = v704;
                                                            *((_QWORD *)v704 + 1) = 0;
                                                          }
                                                          v707 = (LPVOID)v274[3];
                                                          if ( v707 )
                                                          {
                                                            v276 = GetProcessHeap();
                                                            HeapFree(v276, 0, v707);
                                                            v274 = v704;
                                                            *((_QWORD *)v704 + 3) = 0;
                                                          }
                                                          v707 = (LPVOID)v274[5];
                                                          if ( v707 )
                                                          {
                                                            v277 = GetProcessHeap();
                                                            HeapFree(v277, 0, v707);
                                                            *((_QWORD *)v704 + 5) = 0;
                                                          }
                                                          v278 = GetProcessHeap();
                                                          HeapFree(v278, 0, v704);
                                                          v279 = *(unsigned int **)&v692[1];
                                                          goto LABEL_343;
                                                        }
                                                        *((_QWORD *)v704 + 1) = v266;
                                                        v247 = 0;
                                                        memcpy_0(v266, (const void *)v716, v713);
                                                        v264 = v704;
                                                      }
                                                      else
                                                      {
                                                        *v264 = 0;
                                                        *((_QWORD *)v264 + 1) = 0;
                                                        v247 = 0;
                                                      }
                                                      if ( Size )
                                                      {
                                                        v264[4] = v693;
                                                        v267 = GetProcessHeap();
                                                        v268 = HeapAlloc(v267, 8u, (SIZE_T)Src);
                                                        v269 = v704;
                                                        if ( !v268 )
                                                        {
LABEL_332:
                                                          v704 = v269;
                                                          v715 = v18;
                                                          v702 = v20;
                                                          v699 = v117;
                                                          goto LABEL_333;
                                                        }
                                                        *((_QWORD *)v704 + 3) = v268;
                                                        v247 = 0;
                                                        memcpy_0(v268, (const void *)Size, (size_t)Src);
                                                        v264 = v704;
                                                      }
                                                      else
                                                      {
                                                        v264[4] = 0;
                                                        *((_QWORD *)v264 + 3) = 0;
                                                      }
                                                      if ( v705 )
                                                      {
                                                        v270 = (void *)v691;
                                                        v264[8] = v691;
                                                        v271 = (unsigned int)v270;
                                                        v707 = v270;
                                                        v272 = GetProcessHeap();
                                                        v273 = HeapAlloc(v272, 8u, v271);
                                                        v269 = v704;
                                                        if ( !v273 )
                                                          goto LABEL_332;
                                                        *((_QWORD *)v704 + 5) = v273;
                                                        v247 = 0;
                                                        memcpy_0(v273, v705, (size_t)v707);
                                                        v264 = v704;
                                                      }
                                                      else
                                                      {
                                                        v264[8] = 0;
                                                        *((_QWORD *)v264 + 5) = 0;
                                                      }
                                                      v279 = v264;
                                                      *(_QWORD *)&v692[1] = v264;
                                                      v705 = v118;
                                                      v699 = v117;
                                                      v702 = v20;
                                                      v715 = v18;
LABEL_343:
                                                      if ( v247 < 0 )
                                                      {
                                                        v248 = 0;
                                                        v700 = 0;
                                                        if ( v279 )
                                                        {
                                                          v707 = (LPVOID)*((_QWORD *)v279 + 1);
                                                          if ( v707 )
                                                          {
                                                            v280 = GetProcessHeap();
                                                            HeapFree(v280, 0, v707);
                                                            v279 = *(unsigned int **)&v692[1];
                                                            *(_QWORD *)(*(_QWORD *)&v692[1] + 8LL) = 0;
                                                          }
                                                          v707 = (LPVOID)*((_QWORD *)v279 + 3);
                                                          if ( v707 )
                                                          {
                                                            v281 = GetProcessHeap();
                                                            HeapFree(v281, 0, v707);
                                                            v279 = *(unsigned int **)&v692[1];
                                                            *(_QWORD *)(*(_QWORD *)&v692[1] + 24LL) = 0;
                                                          }
                                                          v707 = (LPVOID)*((_QWORD *)v279 + 5);
                                                          if ( v707 )
                                                          {
                                                            v282 = GetProcessHeap();
                                                            HeapFree(v282, 0, v707);
                                                            *(_QWORD *)(*(_QWORD *)&v692[1] + 40LL) = 0;
                                                          }
                                                          v283 = GetProcessHeap();
                                                          HeapFree(v283, 0, *(LPVOID *)&v692[1]);
                                                          v248 = 0;
                                                          v700 = 0;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v248 = v279;
                                                        v700 = v279;
                                                      }
LABEL_355:
                                                      v19 = v247 | 0x10000000;
                                                      LODWORD(dwBytes) = v19;
                                                      if ( v19 < 0 )
                                                        goto LABEL_212;
                                                      if ( !v248 || (Size = *((_QWORD *)v248 + 1)) == 0 || !*v248 )
                                                      {
                                                        v19 = -805306355;
                                                        goto LABEL_269;
                                                      }
                                                      v284 = *v248 - 8LL;
                                                      v710 = (LPVOID)v284;
                                                      v285 = MemoryAlloc(v284);
                                                      v714 = v285;
                                                      if ( !v285 )
                                                      {
LABEL_387:
                                                        v714 = 0;
                                                        v19 = -805306367;
                                                        goto LABEL_269;
                                                      }
                                                      v286 = 0;
                                                      v697 = 0;
                                                      v704 = (LPVOID)0x7F1137FAB69605ELL;
                                                      Src = (void *)Size;
                                                      v713 = (SIZE_T)v285;
                                                      v287 = v284 & 7;
                                                      if ( (v284 & 7) != 0 )
                                                      {
                                                        LODWORD(dwBytes) = 0;
                                                        LODWORD(v703) = 0;
                                                        v288 = 0;
                                                        v289 = (unsigned __int8 *)Src;
                                                        v290 = 0;
                                                        v291 = 0;
                                                        do
                                                        {
                                                          v292 = *v289++;
                                                          v693 = 8 * v288;
                                                          if ( v288 >= 4 )
                                                            v290 |= v292 << (56 - v693);
                                                          else
                                                            v291 |= v292 << (24 - v693);
                                                          ++v288;
                                                        }
                                                        while ( (int)v288 < (int)v287 );
                                                        LODWORD(v703) = v291;
                                                        LODWORD(dwBytes) = v290;
                                                        Src = v289;
                                                        v705 = v118;
                                                        v699 = v117;
                                                        v702 = v20;
                                                        v715 = v18;
                                                        v286 = v697;
                                                        v293 = v703 ^ 0x92F65A5;
                                                        v294 = v290 ^ 0x699A899C;
                                                        v295 = v703 ^ 0x92F65A5;
                                                        v296 = v290 ^ 0x699A899C;
                                                        v297 = 0;
                                                        if ( (v284 & 7) != 0 )
                                                        {
                                                          v298 = v285;
                                                          do
                                                          {
                                                            v707 = v298 + 1;
                                                            if ( v297 >= 4 )
                                                            {
                                                              v296 = __ROR4__(v296, 24);
                                                              v299 = v296;
                                                            }
                                                            else
                                                            {
                                                              v295 = __ROR4__(v295, 24);
                                                              v299 = v295;
                                                            }
                                                            *v298 = v299;
                                                            ++v297;
                                                            v298 = v707;
                                                          }
                                                          while ( (int)v297 < (int)v287 );
                                                          v713 = (SIZE_T)v707;
                                                        }
                                                        if ( v287 <= 4 )
                                                        {
                                                          v300 = 0;
                                                          if ( v287 < 4 )
                                                            v293 = v293 >> (8 * (4 - v287)) << (8 * (4 - v287));
                                                        }
                                                        else
                                                        {
                                                          v300 = v294 >> (8 * (8 - v287)) << (8 * (8 - v287));
                                                        }
                                                      }
                                                      else
                                                      {
                                                        LODWORD(v703) = 0;
                                                        LODWORD(dwBytes) = -1;
                                                        v300 = 0;
                                                        v293 = 0;
                                                      }
                                                      if ( v284 >> 3 )
                                                      {
                                                        v716 = 0;
                                                        v301 = HIDWORD(v704);
                                                        v695 = WORD2(v704);
                                                        HIDWORD(dwBytes) = 24670;
                                                        v302 = (unsigned __int8 *)Src;
                                                        v303 = (_BYTE *)v713;
                                                        v304 = v284 >> 3;
                                                        v305 = dwBytes;
                                                        v306 = v703;
                                                        do
                                                        {
                                                          v307 = v302[3]
                                                               | ((v302[2] | ((v302[1] | (*v302 << 8)) << 8)) << 8);
                                                          v308 = v302[7]
                                                               | ((v302[6] | ((v302[5] | (v302[4] << 8)) << 8)) << 8);
                                                          v302 += 8;
                                                          v309 = v293 ^ v307;
                                                          v310 = v300 ^ v308 ^ v301 ^ v293 ^ v307 ^ 0xAB69605E;
                                                          v311 = v309
                                                               ^ (__ROR4__(v310, 22)
                                                                + v695 * __ROR4__(v310 + 1419157410, 27));
                                                          v312 = v310
                                                               ^ (WORD1(v704) * __ROR4__(v301 + v311, 9)
                                                                - __ROR4__(v311, 30));
                                                          v313 = v311
                                                               ^ (HIDWORD(dwBytes) * (v312 - v695) - (v312 >> 13));
                                                          v314 = v312
                                                               ^ (HIWORD(v704) * __ROR4__(v313 ^ WORD1(v704), 26)
                                                                - __ROR4__(v313, 30));
                                                          v315 = v313 ^ (v301 - (v314 ^ 0xAB69605E));
                                                          v316 = v314
                                                               ^ (WORD1(v704) * (v315 ^ v695))
                                                               ^ __ROR4__(v315, 6);
                                                          v317 = v315
                                                               ^ (__ROR4__(v316, 30)
                                                                + HIDWORD(dwBytes) * __ROR4__(v316 + v301, 15));
                                                          v318 = v316
                                                               ^ (HIWORD(v704) * __ROR4__(v317 + 1419157410, 14)
                                                                - __ROR4__(v317, 24));
                                                          v319 = v317
                                                               ^ __ROR4__(v318, 10)
                                                               ^ (v695 * __ROR4__(v318 ^ 0xAB69605E, 12));
                                                          v320 = v319
                                                               ^ (HIWORD(v704)
                                                                * (HIDWORD(dwBytes)
                                                                 + __ROR4__(
                                                                     ~(v318
                                                                     ^ (v319 >> 10)
                                                                     ^ (WORD1(v704) * (v319 ^ HIWORD(v704)))),
                                                                     5)));
                                                          v321 = v318
                                                               ^ (v319 >> 10)
                                                               ^ (WORD1(v704) * (v319 ^ HIWORD(v704)))
                                                               ^ (v320 - HIWORD(v704))
                                                               ^ 0xAB69605E;
                                                          v322 = v320
                                                               ^ ((v321 >> 2) + v695 * __ROR4__(v321 ^ HIWORD(v704), 30));
                                                          v323 = v321
                                                               ^ (__ROR4__(v322, 25)
                                                                + WORD1(v704) * __ROR4__(v322 - HIDWORD(v704), 6));
                                                          v324 = v322
                                                               ^ (HIDWORD(dwBytes) * (v323 ^ v695) + __ROR4__(v323, 9));
                                                          v325 = v323
                                                               ^ (__ROR4__(v324, 25)
                                                                + HIWORD(v704) * __ROR4__(v324 ^ WORD1(v704), 27));
                                                          v301 = HIDWORD(v704);
                                                          v326 = HIDWORD(v704) ^ v324 ^ v325 ^ 0xAB69605E;
                                                          v327 = v325 ^ (v695 * (__ROR4__(v326, 3) - WORD1(v704)));
                                                          v328 = v326
                                                               ^ (HIDWORD(dwBytes) * __ROR4__(v327 - HIDWORD(v704), 1)
                                                                - __ROR4__(v327, 6));
                                                          v329 = v327
                                                               ^ (__ROR4__(v328, 18)
                                                                + HIWORD(v704) * __ROR4__(v328 - 1419157410, 29));
                                                          v330 = v328
                                                               ^ (v695 * __ROR4__(v329 - 1419157410, 17)
                                                                - __ROR4__(v329, 14));
                                                          v331 = v329
                                                               ^ (v330 >> 3)
                                                               ^ (WORD1(v704) * (v330 ^ HIDWORD(dwBytes)));
                                                          v293 = v306
                                                               ^ v330
                                                               ^ __ROR4__(v331, 30)
                                                               ^ (HIDWORD(dwBytes) * __ROR4__(HIDWORD(v704) ^ v331, 28));
                                                          v300 = v305 ^ v331;
                                                          v303[3] = v293;
                                                          v303[7] = v300;
                                                          v303[2] = __ROR4__(v293, 8);
                                                          v303[6] = __ROR4__(v300, 8);
                                                          v303[1] = __ROR4__(v293, 16);
                                                          v303[5] = __ROR4__(v300, 16);
                                                          *v303 = __ROR4__(v293, 24);
                                                          v303[4] = __ROR4__(v300, 24);
                                                          v306 = v307;
                                                          v305 = v308;
                                                          v303 += 8;
                                                          ++v716;
                                                        }
                                                        while ( v716 < v304 );
                                                        v286 = v697;
                                                        v18 = v715;
                                                        v20 = v702;
                                                        v118 = (unsigned int *)v705;
                                                        v285 = v714;
                                                        v284 = (unsigned __int64)v710;
                                                      }
                                                      for ( i = 0; i < v284; ++i )
                                                        v286 ^= *((_BYTE *)v285 + i);
                                                      if ( v286 != *(_QWORD *)(v284 + Size) )
                                                      {
                                                        MemoryFree(v285);
                                                        goto LABEL_387;
                                                      }
                                                      v117 = v699;
                                                      v695 = 0;
                                                      *(_QWORD *)&v692[1] = v285;
                                                      if ( (unsigned int)v284 < 4 )
                                                      {
LABEL_389:
                                                        v333 = -1073741762;
LABEL_426:
                                                        v19 = v333 | 0x10000000;
                                                        goto LABEL_211;
                                                      }
                                                      v333 = RtlULongLongAdd(v285, 4, &v692[1]);
                                                      if ( v333 >= 0 )
                                                      {
                                                        v333 = RtlUIntAdd(0, 4, &v695);
                                                        if ( v333 >= 0 )
                                                        {
                                                          if ( (unsigned int)v710 - v695 < 4 )
                                                            goto LABEL_424;
                                                          LODWORD(v703) = **(_DWORD **)&v692[1];
                                                          v333 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                                                          if ( v333 < 0 )
                                                            goto LABEL_425;
                                                          v333 = RtlUIntAdd(v695, 4, &v695);
                                                          if ( v333 < 0 )
                                                            goto LABEL_425;
                                                          if ( (unsigned int)v710 - v695 < (unsigned int)v703 )
                                                            goto LABEL_424;
                                                          v333 = RtlUIntAdd(v695, (unsigned int)v703, &v695);
                                                          if ( v333 >= 0 )
                                                          {
                                                            if ( (unsigned __int64)v336 + (unsigned int)v710 >= (unsigned __int64)(unsigned int)v703 + *(_QWORD *)&v692[1]
                                                              && (unsigned __int64)v336
                                                               + (unsigned int)v710
                                                               - (unsigned __int64)(unsigned int)v703
                                                               - *(_QWORD *)&v692[1] < 8 )
                                                            {
                                                              v709 = *v336;
                                                              v710 = 0;
                                                              v713 = 0;
                                                              v716 = 0;
                                                              v691 = 0;
                                                              if ( *(_QWORD *)&v692[1] )
                                                              {
                                                                v333 = RtlULongLongAdd(
                                                                         *(_QWORD *)&v692[1],
                                                                         (unsigned int)v703,
                                                                         &v710);
                                                                v714 = v338;
                                                                v700 = v339;
                                                                v694 = v340;
                                                                if ( v333 < 0 )
                                                                {
LABEL_420:
                                                                  v349 = v696;
LABEL_421:
                                                                  if ( v333 < 0 || v709 == v349 )
                                                                    goto LABEL_426;
                                                                  goto LABEL_389;
                                                                }
                                                                v341 = (SIZE_T)v337;
                                                                Src = v337;
                                                                if ( v337 < v710 )
                                                                {
                                                                  while ( 1 )
                                                                  {
                                                                    v333 = RtlULongLongAdd(v341, 4, &v713);
                                                                    if ( v333 < 0 )
                                                                      goto LABEL_420;
                                                                    if ( v713 > (unsigned __int64)v710 )
                                                                      goto LABEL_411;
                                                                    v693 = 0;
                                                                    v333 = RtlUIntAdd(4, *(unsigned int *)Src, &v693);
                                                                    if ( v333 < 0 )
                                                                      goto LABEL_426;
                                                                    v333 = RtlULongLongAdd(Src, v693, &v716);
                                                                    v714 = v344;
                                                                    v700 = v343;
                                                                    v694 = v342;
                                                                    if ( v333 < 0 )
                                                                      goto LABEL_420;
                                                                    v341 = v716;
                                                                    Src = (void *)v716;
                                                                    v345 = v710;
                                                                    v714 = v344;
                                                                    v700 = v343;
                                                                    v694 = v342;
                                                                    if ( v716 > (unsigned __int64)v710 )
                                                                      goto LABEL_411;
                                                                    ++v691;
                                                                    if ( v716 >= (unsigned __int64)v710 )
                                                                    {
                                                                      v714 = v344;
                                                                      v700 = v343;
                                                                      v694 = v342;
                                                                      goto LABEL_410;
                                                                    }
                                                                  }
                                                                }
                                                                v345 = v710;
LABEL_410:
                                                                if ( (LPVOID)v341 != v345 )
                                                                {
LABEL_411:
                                                                  v333 = -1073741811;
                                                                  goto LABEL_426;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v333 = 0;
                                                                v714 = v336;
                                                                v700 = v335;
                                                                v694 = v334;
                                                              }
                                                              v346 = 0;
                                                              v713 = 0;
                                                              v347 = v703;
                                                              if ( (_DWORD)v703 )
                                                              {
                                                                v348 = GetProcessHeap();
                                                                v346 = HeapAlloc(v348, 8u, (unsigned int)v703);
                                                                v713 = (SIZE_T)v346;
                                                                if ( !v346 )
                                                                {
                                                                  v333 = -1073741801;
                                                                  goto LABEL_426;
                                                                }
                                                                v333 = 0;
                                                                v347 = v703;
                                                              }
                                                              if ( *(_QWORD *)&v692[1] )
                                                                memcpy_0(v346, *(const void **)&v692[1], v347);
                                                              v706 = (LPVOID)v713;
                                                              v349 = v691;
                                                              v696 = v691;
                                                              goto LABEL_421;
                                                            }
LABEL_424:
                                                            v333 = -1073741762;
                                                          }
                                                        }
                                                      }
LABEL_425:
                                                      v714 = v336;
                                                      v694 = v334;
                                                      v700 = v335;
                                                      goto LABEL_426;
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v248 = (unsigned int *)v700;
                                  goto LABEL_354;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_37:
  lpMem[0] = 0;
  v45 = lpMem[1];
  if ( lpMem[1] )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v45);
    lpMem[1] = 0;
  }
  v47 = v706;
  if ( v706 )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, v47);
  }
  if ( v18 )
  {
    v49 = GetProcessHeap();
    HeapFree(v49, 0, v18);
  }
  if ( v20 )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v20);
  }
  if ( v19 < 0 )
  {
    v14 = (unsigned int)v698;
    v13 = (int)v698;
    goto LABEL_862;
  }
  if ( v730 )
  {
    v51 = 0;
    *(_OWORD *)v719 = 0;
    v52 = 0;
    v699 = 0;
    v53 = GetProcessHeap();
    v54 = HeapAlloc(v53, 8u, 0xA0u);
    v55 = v54;
    if ( !v54 )
    {
LABEL_851:
      v719[0] = 0;
      v679 = (void *)v719[1];
      if ( v719[1] )
      {
        v680 = GetProcessHeap();
        HeapFree(v680, 0, v679);
        v719[1] = 0;
      }
      if ( v52 )
      {
        v681 = GetProcessHeap();
        HeapFree(v681, 0, (LPVOID)v52);
      }
      if ( v55 )
      {
        v682 = GetProcessHeap();
        HeapFree(v682, 0, v55);
      }
      if ( v51 )
      {
        v683 = GetProcessHeap();
        HeapFree(v683, 0, v51);
      }
      goto LABEL_859;
    }
    *v54 = xmmword_1800DF540;
    v54[1] = xmmword_1800DF550;
    v54[2] = xmmword_1800DF560;
    v54[3] = xmmword_1800DF570;
    v54[4] = xmmword_1800DF580;
    v54[5] = xmmword_1800DF590;
    v54[6] = xmmword_1800DF5A0;
    v54[7] = xmmword_1800DF5B0;
    v54[8] = xmmword_1800DF5C0;
    v54[9] = xmmword_1800DF5D0;
    v56 = GetProcessHeap();
    v57 = HeapAlloc(v56, 8u, 8u);
    v58 = v57;
    if ( !v57 )
    {
      v52 = 0;
      goto LABEL_851;
    }
    *v57 = qword_1800DF480;
    v707 = (LPVOID)__rdtsc();
    v692[0] = 0;
    v693 = 0;
    if ( (int)RtlUIntAdd(4, 4, &v693) < 0 )
      goto LABEL_849;
    if ( (int)RtlUIntAdd(0, v693, v692) < 0 )
    {
      v51 = v58;
      v52 = (unsigned __int64)v384;
      goto LABEL_851;
    }
    v693 = (unsigned int)v384;
    if ( (int)RtlUIntAdd(v385, 160, &v693) < 0 )
      goto LABEL_849;
    v386 = RtlUIntAdd(v692[0], v693, v692);
    if ( (v388 | v386) < 0 )
      goto LABEL_849;
    v693 = 0;
    if ( (int)RtlUIntAdd(v387, 8, &v693) < 0
      || (v389 = RtlUIntAdd(v692[0], v693, v692), (v391 | v389) < 0)
      || (v693 = 0, (int)RtlUIntAdd(v390, 8, &v693) < 0)
      || (v392 = RtlUIntAdd(v692[0], v693, v692), (v393 | v392) < 0)
      || (HIDWORD(v719[0]) = v692[0], v394 = v692[0], v395 = GetProcessHeap(), (v396 = HeapAlloc(v395, 8u, v394)) == 0) )
    {
LABEL_849:
      v51 = v58;
      goto LABEL_850;
    }
    v719[1] = (size_t)v396;
    LODWORD(v719[0]) = 0;
    LODWORD(v721) = 0;
    v720 = 0;
    pcchLength = (size_t)v396;
    v51 = v58;
    if ( (int)RtlULongLongAdd(v396, 4, &v721) < 0 || (unsigned __int64)(v397 + 2) > v719[1] + HIDWORD(v719[0]) )
      goto LABEL_850;
    *v397 = v398;
    *(_DWORD *)v721 = v398;
    v400 = ++LODWORD(v719[0]);
    LODWORD(v721) = 0;
    v720 = 0;
    if ( v55 )
    {
      if ( !v399 )
        goto LABEL_850;
    }
    else if ( v399 )
    {
LABEL_501:
      v52 = 0;
      goto LABEL_851;
    }
    v401 = (unsigned int *)v719[1];
    if ( v719[1] )
    {
      pcchLength = v719[1];
      v691 = 0;
      if ( v400 )
      {
        do
        {
          v693 = 0;
          if ( (int)RtlUIntAdd(4, *v401, &v693) < 0 || (int)RtlULongLongAdd(v403, v693, &pcchLength) < 0 )
            goto LABEL_850;
          ++v691;
          v401 = (unsigned int *)pcchLength;
        }
        while ( v691 < v404 );
      }
      if ( (int)RtlULongLongAdd(v401, 4, &v721) < 0 || (unsigned __int64)v405 + v406 + 4 > v719[1] + HIDWORD(v719[0]) )
        goto LABEL_850;
      *v405 = v406;
      if ( v55 )
        memcpy_0(v721, v55, v406);
      v402 = 4;
    }
    else
    {
      v693 = 0;
      if ( (int)RtlUIntAdd(4, v399, &v693) < 0 || (int)RtlUIntAdd(HIDWORD(v719[0]), v693, (char *)v719 + 4) < 0 )
        goto LABEL_850;
    }
    v407 = ++LODWORD(v719[0]);
    LODWORD(v721) = 0;
    v720 = 0;
    if ( !v58 )
      goto LABEL_501;
    v408 = (unsigned int *)v719[1];
    if ( v719[1] )
    {
      pcchLength = v719[1];
      if ( v407 )
      {
        do
        {
          v693 = 0;
          if ( (int)RtlUIntAdd(4, *v408, &v693) < 0 || (int)RtlULongLongAdd(v410, v693, &pcchLength) < 0 )
            goto LABEL_850;
          v408 = (unsigned int *)pcchLength;
        }
        while ( v412 + 1 < v411 );
      }
      if ( (int)RtlULongLongAdd(v408, 4, &v721) < 0 || (unsigned __int64)(v413 + 3) > v719[1] + HIDWORD(v719[0]) )
        goto LABEL_850;
      *v413 = 8;
      memcpy_0(v721, v58, 8u);
      v409 = 4;
    }
    else
    {
      v693 = 0;
      if ( (int)RtlUIntAdd(v402, 8, &v693) < 0 || (int)RtlUIntAdd(HIDWORD(v719[0]), v693, (char *)v719 + 4) < 0 )
        goto LABEL_850;
    }
    v414 = ++LODWORD(v719[0]);
    LODWORD(v721) = 0;
    v720 = 0;
    v415 = (unsigned int *)v719[1];
    if ( !v719[1] )
    {
      v693 = 0;
      if ( (int)RtlUIntAdd(v409, 8, &v693) < 0 || (int)RtlUIntAdd(HIDWORD(v719[0]), v693, (char *)v719 + 4) < 0 )
        goto LABEL_850;
LABEL_539:
      ++LODWORD(v719[0]);
      v693 = 0;
      if ( (int)RtlUIntAdd(v416, v416, &v693) < 0 )
        goto LABEL_850;
      v696 = v693;
      v693 = 0;
      if ( (int)RtlUIntAdd(v421, 8, &v693) < 0 || (int)RtlUIntAdd(v422, v693, &v696) < 0 )
        goto LABEL_850;
      v691 = 0;
      v423 = v696;
      HIDWORD(dwBytes) = v696;
      v698 = 0;
      v707 = (LPVOID)__rdtsc();
      v724 = 8;
      v424 = RtlUIntAdd(8, HIDWORD(v719[0]), &v724);
      if ( v424 < 0 )
      {
        v702 = v51;
        v706 = v55;
      }
      else
      {
        v427 = (v724 + 7) & 0xFFFFFFF8;
        if ( v427 < v724 )
        {
          v52 = (unsigned int)v425;
          goto LABEL_851;
        }
        v724 = (v724 + 7) & 0xFFFFFFF8;
        v428 = v427;
        v429 = GetProcessHeap();
        v430 = HeapAlloc(v429, 8u, v428);
        pcchLength = (size_t)v430;
        if ( !v430 )
          goto LABEL_833;
        v706 = v55;
        v702 = v51;
        HIDWORD(dwBytes) = v423;
        *(_QWORD *)&v692[1] = v430;
        *v430 = v719[0];
        v696 = RtlULongLongAdd(v430, 4, &v692[1]);
        if ( (v696 & 0x80000000) != 0 )
        {
          pcchLength = v431;
        }
        else
        {
          v433 = *(_QWORD *)&v692[1];
          **(_DWORD **)&v692[1] = HIDWORD(v719[0]);
          v696 = RtlULongLongAdd(v433, v432, &v692[1]);
          if ( (v696 & 0x80000000) == 0 )
          {
            *(_QWORD *)(v724 + v434 - 8) = v707;
            memcpy_0(*(void **)&v692[1], (const void *)v719[1], HIDWORD(v719[0]));
            v425 = pcchLength;
            v698 = (LPVOID)pcchLength;
            v426 = v724;
            v424 = v696;
            goto LABEL_552;
          }
        }
        v706 = v55;
        v702 = v51;
        HIDWORD(dwBytes) = v423;
        v435 = GetProcessHeap();
        HeapFree(v435, 0, (LPVOID)pcchLength);
        v425 = (size_t)v698;
        v424 = v696;
        v426 = (unsigned int)v698;
      }
LABEL_552:
      v436 = 0;
      v725 = 0;
      v437 = 0;
      v705 = 0;
      v700 = 0;
      v694 = 0;
      v438 = v424 | 0x10000000;
      if ( v438 < 0 )
      {
        LODWORD(v701) = v438;
        v517 = 0;
        goto LABEL_808;
      }
      if ( v425 )
      {
        v713 = v426;
        if ( !v426 || (v716 = v426 + 8LL, v439 = MemoryAlloc(v716), (Size = (SIZE_T)v439) == 0) )
        {
          LODWORD(v701) = -805306367;
          v491 = v698;
          v517 = 0;
          goto LABEL_810;
        }
        v710 = 0;
        v440 = 0;
        v697 = 0;
        v441 = 0;
        v442 = v713;
        if ( v713 )
        {
          do
            v440 ^= *((_BYTE *)v698 + v441++);
          while ( v441 < v713 );
          v697 = v440;
        }
        v701 = 0xC81ECB17B1B54A58uLL;
        pcchLength = (size_t)v698;
        Src = v439;
        v443 = v713 & 7;
        if ( (v713 & 7) != 0 )
        {
          v696 = 0;
          LODWORD(v703) = 0;
          v444 = 0;
          v445 = (unsigned __int8 *)v698;
          v446 = 0;
          v447 = 0;
          do
          {
            v448 = *v445++;
            v693 = 8 * v444;
            if ( v444 >= 4 )
              v446 |= v448 << (56 - v693);
            else
              v447 |= v448 << (24 - v693);
            ++v444;
          }
          while ( (int)v444 < (int)v443 );
          LODWORD(v703) = v447;
          v696 = v446;
          pcchLength = (size_t)v445;
          v702 = v51;
          v706 = v55;
          v436 = 0;
          v449 = v703 ^ 0xB17A307A;
          v450 = v446 ^ 0x42F6B18D;
          v451 = v703 ^ 0xB17A307A;
          v452 = v446 ^ 0x42F6B18D;
          v692[0] = 0;
          if ( (v713 & 7) != 0 )
          {
            v453 = Src;
            do
            {
              v707 = v453 + 1;
              if ( v692[0] >= 4u )
              {
                v452 = __ROR4__(v452, 24);
                v454 = v452;
              }
              else
              {
                v451 = __ROR4__(v451, 24);
                v454 = v451;
              }
              *v453 = v454;
              ++v692[0];
              v453 = v707;
            }
            while ( v692[0] < (int)v443 );
            Src = v707;
          }
          if ( v443 <= 4 )
          {
            v455 = 0;
            if ( v443 < 4 )
              v449 = v449 >> (8 * (4 - v443)) << (8 * (4 - v443));
          }
          else
          {
            v455 = v450 >> (8 * (8 - v443)) << (8 * (8 - v443));
          }
        }
        else
        {
          v449 = 0;
          v455 = -1;
          LODWORD(v703) = 0;
          v696 = 0;
        }
        if ( v442 >> 3 )
        {
          v720 = 0;
          v456 = 19032;
          v692[0] = 19032;
          v695 = WORD1(v701);
          v693 = HIWORD(v701);
          v709 = HIDWORD(v701) ^ 0xB1B54A58;
          v457 = (unsigned __int8 *)pcchLength;
          v458 = Src;
          v459 = v442 >> 3;
          v460 = v696;
          v461 = v703;
          v462 = HIDWORD(v701) ^ 0xB1B54A58;
          do
          {
            v463 = v457[3] | ((v457[2] | ((v457[1] | (*v457 << 8)) << 8)) << 8);
            v464 = v457[7] | ((v457[6] | ((v457[5] | (v457[4] << 8)) << 8)) << 8);
            v465 = v455 ^ v464;
            v457 += 8;
            v466 = v449 ^ v463 ^ HIDWORD(v701) ^ ((v455 ^ v464) - v456);
            v467 = v465 ^ (__ROR4__(v466, 7) + WORD1(v701) * __ROR4__(v466 ^ HIDWORD(v701), 15));
            v468 = v466 ^ (WORD2(v701) * __ROR4__(v467 - 1313519016, 9) - __ROR4__(v467, 10));
            v469 = v467 ^ (__ROR4__(v468, 27) + HIWORD(v701) * __ROR4__(v468 ^ WORD2(v701), 28));
            v470 = v468 ^ (HIDWORD(v701) - (v469 ^ 0xB1B54A58));
            v471 = v469 ^ (WORD1(v701) * (v470 - v692[0]) - (v470 >> 6));
            v472 = v470 ^ (v692[0] * (WORD2(v701) ^ __ROR4__(v471, 15)));
            v473 = v471 ^ (WORD2(v701) * (v693 + __ROR4__(~v472, 3)));
            v474 = v472 ^ (v473 - HIDWORD(v701) - v692[0]);
            v475 = v473 ^ (v695 * (v474 ^ HIWORD(v701))) ^ __ROR4__(v474, 10);
            v476 = v474 ^ __ROR4__(v475, 3) ^ (WORD2(v701) * __ROR4__(v475 ^ v692[0], 26));
            v477 = v475 ^ (v692[0] * (__ROR4__(v476, 15) - HIWORD(v701)));
            v478 = v476
                 ^ (v692[0] * (v477 ^ HIWORD(v701)))
                 ^ ((v477 ^ (v477 >> 14)) >> 1)
                 ^ (v692[0] * (((v477 - WORD2(v701)) >> 29) | (8 * (v477 - WORD2(v701)))));
            v479 = v477 ^ (WORD1(v701) * (v478 - WORD2(v701)) - (v478 >> 13));
            v480 = v478 ^ __ROR4__(v479, 11) ^ (WORD2(v701) * __ROR4__(-1313519016 - v479, 9));
            v481 = v479 ^ (v480 + 1313519016 - HIWORD(v701));
            v482 = v480 ^ (v692[0] * (v481 ^ WORD1(v701)) - __ROR4__(v481, 7));
            v483 = v481 ^ (WORD1(v701) * __ROR4__(v482 ^ HIWORD(v701), 28) - __ROR4__(v482, 16));
            v484 = v482 ^ (__ROR4__(v483, 4) + WORD2(v701) * __ROR4__(-1313519016 - v483, 10));
            v485 = v483 ^ __ROR4__(v484, 9) ^ (HIWORD(v701) * __ROR4__(v484 + 1313519016, 4));
            v486 = v484 ^ (v692[0] * __ROR4__(v485 ^ HIDWORD(v701), 24) - __ROR4__(v485, 30));
            v487 = v485 ^ (WORD1(v701) * __ROR4__(HIDWORD(v701) - v486, 11) - __ROR4__(v486, 12));
            v488 = v486 ^ (v487 >> 8) ^ (WORD2(v701) * (v487 ^ WORD1(v701)));
            v449 = v461 ^ v488;
            v455 = v487 ^ v460 ^ v488 ^ v462;
            v458[3] = v461 ^ v488;
            v458[7] = v487 ^ v460 ^ v488 ^ v462;
            v458[2] = __ROR4__(v461 ^ v488, 8);
            v458[6] = __ROR4__(v455, 8);
            v458[1] = __ROR4__(v461 ^ v488, 16);
            v458[5] = __ROR4__(v455, 16);
            *v458 = __ROR4__(v461 ^ v488, 24);
            v458[4] = __ROR4__(v455, 24);
            v461 = v463;
            v460 = v464;
            v458 += 8;
            ++v720;
            v456 = v692[0];
          }
          while ( v720 < v459 );
          v440 = v697;
          v19 = dwBytes;
          v55 = v706;
          v51 = v702;
          v437 = (unsigned int *)v705;
          v436 = (unsigned int *)v705;
          v442 = v713;
        }
        *(_QWORD *)(Size + v442) = v440;
        v489 = GetProcessHeap();
        v490 = HeapAlloc(v489, 8u, 0x30u);
        v706 = v490;
        if ( !v490 )
        {
          v692[0] = -1073741801;
          v491 = v698;
          goto LABEL_598;
        }
        v492 = v716;
        *v490 = v716;
        v493 = GetProcessHeap();
        v494 = HeapAlloc(v493, 8u, v492);
        v491 = v698;
        if ( v494 )
        {
          *((_QWORD *)v706 + 1) = v494;
          memcpy_0(v494, (const void *)Size, (unsigned int)v716);
          *((_DWORD *)v706 + 4) = 160;
          v495 = GetProcessHeap();
          v496 = HeapAlloc(v495, 8u, 0xA0u);
          v497 = v706;
          if ( v496 )
          {
            *((_QWORD *)v706 + 3) = v496;
            *v496 = xmmword_1800DF490;
            v496[1] = xmmword_1800DF4A0;
            v496[2] = xmmword_1800DF4B0;
            v496[3] = xmmword_1800DF4C0;
            v496[4] = xmmword_1800DF4D0;
            v496[5] = xmmword_1800DF4E0;
            v496[6] = xmmword_1800DF4F0;
            v496[7] = xmmword_1800DF500;
            v496[8] = xmmword_1800DF510;
            v496[9] = xmmword_1800DF520;
            v497[8] = 8;
            v498 = GetProcessHeap();
            v499 = HeapAlloc(v498, 8u, 8u);
            if ( v499 )
            {
              v505 = v706;
              *((_QWORD *)v706 + 5) = v499;
              *v499 = qword_1800DF530;
              v710 = v505;
              v692[0] = 0;
              v698 = v491;
              goto LABEL_597;
            }
            v497 = v706;
          }
          v706 = v497;
        }
        v692[0] = -1073741801;
        v698 = v491;
        v500 = v706;
        v707 = (LPVOID)*((_QWORD *)v706 + 1);
        if ( v707 )
        {
          v501 = GetProcessHeap();
          HeapFree(v501, 0, v707);
          v500 = v706;
          *((_QWORD *)v706 + 1) = 0;
        }
        v707 = (LPVOID)v500[3];
        if ( v707 )
        {
          v502 = GetProcessHeap();
          HeapFree(v502, 0, v707);
          v500 = v706;
          *((_QWORD *)v706 + 3) = 0;
        }
        v707 = (LPVOID)v500[5];
        if ( v707 )
        {
          v503 = GetProcessHeap();
          HeapFree(v503, 0, v707);
          *((_QWORD *)v706 + 5) = 0;
        }
        v504 = GetProcessHeap();
        HeapFree(v504, 0, v706);
        if ( v692[0] < 0 )
        {
LABEL_598:
          v506 = GetProcessHeap();
          HeapFree(v506, 0, (LPVOID)Size);
          v507 = v710;
          if ( v710 )
          {
            v707 = (LPVOID)*((_QWORD *)v710 + 1);
            if ( v707 )
            {
              v508 = GetProcessHeap();
              HeapFree(v508, 0, v707);
              v507 = v710;
              *((_QWORD *)v710 + 1) = 0;
            }
            v707 = (LPVOID)v507[3];
            if ( v707 )
            {
              v509 = GetProcessHeap();
              HeapFree(v509, 0, v707);
              v507 = v710;
              *((_QWORD *)v710 + 3) = 0;
            }
            v707 = (LPVOID)v507[5];
            if ( v707 )
            {
              v510 = GetProcessHeap();
              HeapFree(v510, 0, v707);
              *((_QWORD *)v710 + 5) = 0;
            }
            v511 = GetProcessHeap();
            HeapFree(v511, 0, v710);
          }
          if ( v692[0] < 0 )
          {
            LODWORD(v701) = v692[0] | 0x10000000;
            goto LABEL_614;
          }
          v693 = 0;
          v695 = 4;
          LODWORD(v701) = RtlUIntAdd(4, *v436, &v695);
          if ( (v701 & 0x80000000) != 0LL
            || (LODWORD(v701) = RtlUIntAdd(v695, v512, &v695), (v701 & 0x80000000) != 0LL)
            || (v720 = (SIZE_T)(v436 + 4), LODWORD(v701) = RtlUIntAdd(v695, v436[4], &v695), (v701 & 0x80000000) != 0LL)
            || (LODWORD(v701) = RtlUIntAdd(v695, v513, &v695), (v701 & 0x80000000) != 0LL)
            || (v713 = (SIZE_T)(v436 + 8), LODWORD(v701) = RtlUIntAdd(v695, v436[8], &v695), (v701 & 0x80000000) != 0LL) )
          {
            v698 = v491;
          }
          else
          {
            v514 = v695;
            v515 = GetProcessHeap();
            v516 = HeapAlloc(v515, 8u, v514);
            v702 = v516;
            v491 = v698;
            if ( !v516 )
            {
              LODWORD(v701) = -805306345;
LABEL_614:
              v517 = v694;
              goto LABEL_809;
            }
            v706 = v516;
            *v516 = *v436;
            LODWORD(v701) = RtlULongLongAdd(v516, 4, &v706);
            if ( (v701 & 0x80000000) != 0LL )
            {
              HIDWORD(dwBytes) = v519;
              v702 = v518;
            }
            else
            {
              memcpy_0(v706, *((const void **)v436 + 1), *v436);
              LODWORD(v701) = RtlULongLongAdd(v706, *v436, &v706);
              if ( (v701 & 0x80000000) == 0LL )
              {
                v520 = v706;
                *(_DWORD *)v706 = *(_DWORD *)v720;
                LODWORD(v701) = RtlULongLongAdd(v520, 4, &v706);
                if ( (v701 & 0x80000000) == 0LL )
                {
                  memcpy_0(v706, *((const void **)v436 + 3), *v521);
                  LODWORD(v701) = RtlULongLongAdd(v706, *(unsigned int *)v720, &v706);
                  if ( (v701 & 0x80000000) == 0LL )
                  {
                    v522 = v706;
                    *(_DWORD *)v706 = *(_DWORD *)v713;
                    LODWORD(v701) = RtlULongLongAdd(v522, 4, &v706);
                    if ( (v701 & 0x80000000) == 0LL )
                    {
                      memcpy_0(v706, *((const void **)v436 + 5), *v523);
                      v524 = RtlULongLongAdd(v706, *(unsigned int *)v713, &v706);
                      LODWORD(v701) = v524;
                      if ( v524 >= 0 )
                      {
                        v725 = v702;
                        v693 = v695;
LABEL_628:
                        v526 = v524 | 0x10000000;
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v727 = 8;
                        v527 = RtlUIntAdd(8, HIDWORD(dwBytes), &v727);
                        v526 = v528 | v527;
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v529 = (v727 + 7) & 0xFFFFFFF8;
                        if ( (unsigned int)v529 < v727 )
                        {
                          v526 = -1073741675;
LABEL_632:
                          LODWORD(v701) = v526;
LABEL_670:
                          v517 = v694;
LABEL_808:
                          v491 = v698;
LABEL_809:
                          if ( !v491 )
                          {
LABEL_811:
                            if ( v436 )
                            {
                              v654 = (void *)*((_QWORD *)v436 + 1);
                              if ( v654 )
                              {
                                v655 = GetProcessHeap();
                                HeapFree(v655, 0, v654);
                                *((_QWORD *)v436 + 1) = 0;
                              }
                              v656 = (void *)*((_QWORD *)v436 + 3);
                              if ( v656 )
                              {
                                v657 = GetProcessHeap();
                                HeapFree(v657, 0, v656);
                                *((_QWORD *)v436 + 3) = 0;
                              }
                              v658 = (void *)*((_QWORD *)v436 + 5);
                              if ( v658 )
                              {
                                v659 = GetProcessHeap();
                                HeapFree(v659, 0, v658);
                                *((_QWORD *)v436 + 5) = 0;
                              }
                              v660 = GetProcessHeap();
                              HeapFree(v660, 0, v436);
                            }
                            v661 = v725;
                            if ( v725 )
                            {
                              v662 = GetProcessHeap();
                              HeapFree(v662, 0, v661);
                            }
                            if ( v437 )
                            {
                              v663 = GetProcessHeap();
                              HeapFree(v663, 0, v437);
                            }
                            v664 = v700;
                            if ( v700 )
                            {
                              v665 = (void *)*((_QWORD *)v700 + 1);
                              if ( v665 )
                              {
                                v666 = GetProcessHeap();
                                HeapFree(v666, 0, v665);
                                v664[1] = 0;
                              }
                              v667 = (void *)v664[3];
                              if ( v667 )
                              {
                                v668 = GetProcessHeap();
                                HeapFree(v668, 0, v667);
                                v664[3] = 0;
                              }
                              v669 = (void *)v664[5];
                              if ( v669 )
                              {
                                v670 = GetProcessHeap();
                                HeapFree(v670, 0, v669);
                                v664[5] = 0;
                              }
                              v671 = GetProcessHeap();
                              HeapFree(v671, 0, v664);
                            }
                            if ( v517 )
                            {
                              v672 = GetProcessHeap();
                              HeapFree(v672, 0, v517);
                            }
LABEL_833:
                            if ( (v701 & 0x80000000) == 0LL )
                            {
                              v52 = (unsigned __int64)v699;
                              if ( v691 )
                              {
                                if ( v699 )
                                {
                                  v720 = (SIZE_T)v699;
                                  if ( (int)RtlULongLongAdd(v699, 4, &v720) >= 0 )
                                  {
                                    v675 = (int *)v720;
                                    if ( !*(_DWORD *)v52 )
                                      v675 = 0;
                                    if ( *(_DWORD *)v52 == (_DWORD)v674 && *v675 >= 0 && v673 > 1 )
                                    {
                                      v676 = v52;
                                      *(_QWORD *)&v692[1] = v52;
                                      while ( (int)RtlULongLongAdd(v676, v674, &v692[1]) >= 0
                                           && (int)RtlULongLongAdd(*(_QWORD *)&v692[1], v677, &v692[1]) >= 0 )
                                      {
                                        v676 = *(_QWORD *)&v692[1];
                                        if ( v678 != -1 )
                                        {
                                          RtlULongLongAdd(*(_QWORD *)&v692[1], v674, &v692[1]);
                                          goto LABEL_851;
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              goto LABEL_851;
                            }
                            goto LABEL_850;
                          }
LABEL_810:
                          v653 = GetProcessHeap();
                          HeapFree(v653, 0, v491);
                          goto LABEL_811;
                        }
                        v731 = (v727 + 7) & 0xFFFFFFF8;
                        v526 = RtlUIntAdd(v529, 8, &v731);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v706 = v55;
                        v702 = v51;
                        v698 = v491;
                        v704 = v436;
                        v696 = 0;
                        v530 = v719[1];
                        if ( !v719[1] )
                          goto LABEL_642;
                        v704 = v436;
                        v698 = v491;
                        v702 = v51;
                        v706 = v55;
                        if ( LODWORD(v719[0]) <= 1 )
                          goto LABEL_642;
                        *(_QWORD *)&v692[1] = v719[1];
                        do
                        {
                          v526 = RtlULongLongAdd(v530, 4, &v692[1]);
                          if ( v526 < 0 )
                            goto LABEL_632;
                          v526 = RtlULongLongAdd(*(_QWORD *)&v692[1], v531, &v692[1]);
                          if ( v526 < 0 )
                            goto LABEL_632;
                          v530 = *(_QWORD *)&v692[1];
                        }
                        while ( v532 == -1 );
                        v533 = **(_DWORD **)&v692[1];
                        v526 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v534 = v719[1];
                        if ( !v719[1] || LODWORD(v719[0]) <= 2 )
                        {
LABEL_642:
                          v526 = -1073741811;
                          goto LABEL_632;
                        }
                        *(_QWORD *)&v692[1] = v719[1];
                        do
                        {
                          v526 = RtlULongLongAdd(v534, 4, &v692[1]);
                          if ( v526 < 0 )
                            goto LABEL_632;
                          v526 = RtlULongLongAdd(*(_QWORD *)&v692[1], v538, &v692[1]);
                          if ( v526 < 0 )
                            goto LABEL_632;
                          v534 = *(_QWORD *)&v692[1];
                        }
                        while ( (unsigned int)(v539 + 1) < 2 );
                        v526 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v696 = v540;
                        v692[0] = v541;
                        v526 = RtlUIntAdd(v541, v731, v692);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v526 = RtlUIntAdd(v692[0], v542, v692);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v526 = RtlUIntAdd(v692[0], v533, v692);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v526 = RtlUIntAdd(v692[0], v543, v692);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v526 = RtlUIntAdd(v692[0], v544, v692);
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v696 = v692[0];
                        if ( v692[0] > 0x400000u )
                        {
                          v526 = -2147418113;
                          goto LABEL_632;
                        }
                        v535 = v692[0];
                        v536 = GetProcessHeap();
                        v537 = (unsigned int *)HeapAlloc(v536, 8u, v535);
                        v437 = v537;
                        if ( !v537 )
                        {
                          LODWORD(v701) = -805306345;
                          v517 = 0;
                          goto LABEL_808;
                        }
                        v741 = 0;
                        v742 = 0;
                        hModule = 0;
                        if ( !v725 )
                        {
                          LODWORD(v701) = -2147024809;
                          goto LABEL_670;
                        }
                        *(_QWORD *)&v741 = v725;
                        LODWORD(v742) = v693;
                        *((_QWORD *)&v741 + 1) = v537;
                        *(_QWORD *)((char *)&v742 + 4) = v696;
                        if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                          && (v546 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                        {
                          v526 = ((__int64 (__fastcall *)(__int64, __int128 *))v546)(134, &v741) | 0x10000000;
                          if ( v526 >= 0 )
                          {
                            v547 = DWORD1(v742);
                            goto LABEL_673;
                          }
                        }
                        else
                        {
                          v526 = GetLastError();
                          v545 = v526 < 0;
                          if ( v526 > 0 )
                          {
                            v526 = (unsigned __int16)v526 | 0x80070000;
                            v545 = v526 < 0;
                          }
                          if ( !v545 )
                          {
                            LODWORD(v701) = -2147467259;
                            goto LABEL_670;
                          }
                        }
                        if ( v526 == -805306333 )
                        {
                          LODWORD(v701) = -2147024774;
                          goto LABEL_670;
                        }
                        if ( v526 < 0 )
                          goto LABEL_632;
                        v547 = v696;
LABEL_673:
                        HIDWORD(dwBytes) = 0;
                        v715 = v437;
                        if ( v547 < 4 )
                        {
LABEL_674:
                          LODWORD(v701) = -805306306;
                          goto LABEL_670;
                        }
                        v548 = *v437;
                        v709 = *v437;
                        v549 = RtlULongLongAdd(v437, 4, &v715);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        v549 = RtlUIntAdd(0, v550, (char *)&dwBytes + 4);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        if ( v551 - HIDWORD(dwBytes) < (unsigned int)v548 )
                          goto LABEL_674;
                        v713 = (SIZE_T)v715;
                        v720 = v548;
                        v549 = RtlULongLongAdd(v715, (unsigned int)v548, &v715);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        v549 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v548, (char *)&dwBytes + 4);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        if ( v552 - HIDWORD(dwBytes) < (unsigned int)v553 )
                          goto LABEL_674;
                        v693 = *(_DWORD *)v715;
                        v549 = RtlULongLongAdd(v715, v553, &v715);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        v549 = RtlUIntAdd(HIDWORD(dwBytes), v554, (char *)&dwBytes + 4);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        if ( v555 - HIDWORD(dwBytes) < (unsigned int)v556 )
                          goto LABEL_674;
                        pcchLength = (size_t)v715;
                        v716 = v556;
                        v549 = RtlULongLongAdd(v715, (unsigned int)v556, &v715);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        v549 = RtlUIntAdd(HIDWORD(dwBytes), v557, (char *)&dwBytes + 4);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        if ( v558 - HIDWORD(dwBytes) < v559 )
                          goto LABEL_674;
                        v696 = *(_DWORD *)v715;
                        v549 = RtlULongLongAdd(v715, 4, &v715);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        v549 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                        if ( v549 < 0 )
                          goto LABEL_726;
                        if ( v560 - HIDWORD(dwBytes) < v561 )
                          goto LABEL_674;
                        v549 = RtlUIntAdd(HIDWORD(dwBytes), v561, (char *)&dwBytes + 4);
                        if ( v549 < 0 )
                        {
LABEL_726:
                          v705 = v437;
                          v491 = v698;
                          v581 = (unsigned int *)v700;
                          goto LABEL_727;
                        }
                        if ( v562 != HIDWORD(dwBytes) || (unsigned int)(v563 + v564 + v548) + 12LL != v562 )
                          goto LABEL_674;
                        v565 = GetProcessHeap();
                        v566 = HeapAlloc(v565, 8u, 0x30u);
                        v567 = v566;
                        v714 = v566;
                        v491 = v698;
                        if ( !v566 )
                        {
                          v700 = 0;
                          LODWORD(v701) = -805306345;
                          v517 = 0;
                          goto LABEL_809;
                        }
                        v706 = v55;
                        v702 = v51;
                        v704 = v436;
                        *(_QWORD *)&v692[1] = 0;
                        if ( v713 )
                        {
                          *(_DWORD *)v566 = v709;
                          v568 = GetProcessHeap();
                          v569 = HeapAlloc(v568, 8u, v720);
                          v570 = v714;
                          if ( !v569 )
                          {
LABEL_706:
                            v692[0] = -1073741801;
                            v705 = v437;
                            v707 = (LPVOID)v570[1];
                            if ( v707 )
                            {
                              v576 = GetProcessHeap();
                              HeapFree(v576, 0, v707);
                              v570 = v714;
                              *((_QWORD *)v714 + 1) = 0;
                            }
                            v707 = (LPVOID)v570[3];
                            if ( v707 )
                            {
                              v577 = GetProcessHeap();
                              HeapFree(v577, 0, v707);
                              v570 = v714;
                              *((_QWORD *)v714 + 3) = 0;
                            }
                            v707 = (LPVOID)v570[5];
                            if ( v707 )
                            {
                              v578 = GetProcessHeap();
                              HeapFree(v578, 0, v707);
                              *((_QWORD *)v714 + 5) = 0;
                            }
                            v579 = GetProcessHeap();
                            HeapFree(v579, 0, v714);
                            v580 = *(unsigned int **)&v692[1];
                            goto LABEL_716;
                          }
                          *((_QWORD *)v714 + 1) = v569;
                          v692[0] = 0;
                          memcpy_0(v569, (const void *)v713, v720);
                          v567 = v714;
                        }
                        else
                        {
                          *(_DWORD *)v566 = 0;
                          v566[1] = 0;
                          v692[0] = 0;
                        }
                        if ( pcchLength )
                        {
                          v567[4] = v693;
                          v571 = GetProcessHeap();
                          v572 = HeapAlloc(v571, 8u, v716);
                          v570 = v714;
                          if ( !v572 )
                          {
LABEL_705:
                            v706 = v55;
                            v702 = v51;
                            v698 = v491;
                            v704 = v436;
                            v714 = v570;
                            goto LABEL_706;
                          }
                          *((_QWORD *)v714 + 3) = v572;
                          v692[0] = 0;
                          memcpy_0(v572, (const void *)pcchLength, v716);
                          v567 = v714;
                        }
                        else
                        {
                          v567[4] = 0;
                          *((_QWORD *)v567 + 3) = 0;
                        }
                        if ( v715 )
                        {
                          v573 = v696;
                          v567[8] = v696;
                          v720 = v573;
                          v574 = GetProcessHeap();
                          v575 = HeapAlloc(v574, 8u, v720);
                          v570 = v714;
                          if ( !v575 )
                            goto LABEL_705;
                          *((_QWORD *)v714 + 5) = v575;
                          v692[0] = 0;
                          memcpy_0(v575, v715, v720);
                          v567 = v714;
                        }
                        else
                        {
                          v567[8] = 0;
                          *((_QWORD *)v567 + 5) = 0;
                        }
                        v580 = v567;
                        *(_QWORD *)&v692[1] = v567;
                        v705 = v437;
                        v704 = v436;
                        v698 = v491;
                        v702 = v51;
                        v706 = v55;
LABEL_716:
                        v549 = v692[0];
                        if ( v692[0] < 0 )
                        {
                          v581 = 0;
                          v700 = 0;
                          if ( v580 )
                          {
                            v707 = (LPVOID)*((_QWORD *)v580 + 1);
                            if ( v707 )
                            {
                              v582 = GetProcessHeap();
                              HeapFree(v582, 0, v707);
                              v580 = *(unsigned int **)&v692[1];
                              *(_QWORD *)(*(_QWORD *)&v692[1] + 8LL) = 0;
                            }
                            v707 = (LPVOID)*((_QWORD *)v580 + 3);
                            if ( v707 )
                            {
                              v583 = GetProcessHeap();
                              HeapFree(v583, 0, v707);
                              v580 = *(unsigned int **)&v692[1];
                              *(_QWORD *)(*(_QWORD *)&v692[1] + 24LL) = 0;
                            }
                            v707 = (LPVOID)*((_QWORD *)v580 + 5);
                            if ( v707 )
                            {
                              v584 = GetProcessHeap();
                              HeapFree(v584, 0, v707);
                              *(_QWORD *)(*(_QWORD *)&v692[1] + 40LL) = 0;
                            }
                            v585 = GetProcessHeap();
                            HeapFree(v585, 0, *(LPVOID *)&v692[1]);
                            v581 = 0;
                            v700 = 0;
                            v549 = v692[0];
                          }
                        }
                        else
                        {
                          v581 = v580;
                          v700 = v580;
                        }
LABEL_727:
                        LODWORD(v701) = v549 | 0x10000000;
                        if ( v549 < 0 )
                          goto LABEL_670;
                        if ( !v581 || (Src = (void *)*((_QWORD *)v581 + 1)) == 0 || !*v581 )
                        {
                          LODWORD(v701) = -805306355;
                          goto LABEL_670;
                        }
                        pcchLength = *v581 - 8LL;
                        v586 = MemoryAlloc(pcchLength);
                        v694 = v586;
                        if ( !v586 )
                        {
LABEL_759:
                          LODWORD(v701) = -805306367;
                          v517 = 0;
                          goto LABEL_808;
                        }
                        v587 = 0;
                        v697 = 0;
                        v710 = (LPVOID)0x7F1137FAB69605ELL;
                        v588 = (unsigned __int8 *)Src;
                        v713 = (SIZE_T)Src;
                        v716 = (SIZE_T)v586;
                        v589 = pcchLength;
                        v720 = pcchLength & 7;
                        if ( (pcchLength & 7) != 0 )
                        {
                          v717 = 0;
                          v696 = 0;
                          v709 = 0;
                          v590 = 0;
                          v591 = 0;
                          v592 = 0;
                          do
                          {
                            v692[0] = *v588++;
                            v693 = 8 * v590;
                            if ( (unsigned int)v590 >= 4 )
                            {
                              v692[0] <<= 56 - v693;
                              v592 |= v692[0];
                            }
                            else
                            {
                              v692[0] <<= 24 - v693;
                              v591 |= v692[0];
                            }
                            ++v590;
                          }
                          while ( v590 < (int)v720 );
                          v717 = v592;
                          v696 = v591;
                          v713 = (SIZE_T)v588;
                          v705 = v437;
                          v704 = v436;
                          v698 = v491;
                          v702 = v51;
                          v706 = v55;
                          v587 = v697;
                          v589 = pcchLength;
                          v593 = v720;
                          v594 = v586;
                          v595 = v696 ^ 0x92F65A5;
                          v596 = v717 ^ 0x699A899C;
                          v597 = v696 ^ 0x92F65A5;
                          v709 = 0;
                          if ( (_DWORD)v720 )
                          {
                            v598 = v717 ^ 0x699A899C;
                            v599 = v709;
                            do
                            {
                              v707 = v594 + 1;
                              if ( v599 >= 4 )
                              {
                                v598 = __ROR4__(v598, 24);
                                v600 = v598;
                              }
                              else
                              {
                                v597 = __ROR4__(v597, 24);
                                v600 = v597;
                              }
                              *v594 = v600;
                              ++v599;
                              v594 = v707;
                            }
                            while ( (int)v599 < (int)v593 );
                            v716 = (SIZE_T)v707;
                            v587 = v697;
                            v586 = v694;
                          }
                          if ( v593 <= 4 )
                          {
                            v601 = 0;
                            if ( v593 < 4 )
                              v595 = v595 >> (8 * (4 - v593)) << (8 * (4 - v593));
                          }
                          else
                          {
                            v601 = v596 >> (8 * (8 - v593)) << (8 * (8 - v593));
                          }
                        }
                        else
                        {
                          v696 = 0;
                          v601 = 0;
                          v595 = 0;
                        }
                        if ( v589 >> 3 )
                        {
                          v720 = 0;
                          v602 = HIDWORD(v710);
                          v603 = WORD2(v710);
                          LODWORD(v703) = WORD2(v710);
                          v692[0] = 24670;
                          v709 = HIDWORD(v710) ^ 0xAB69605E;
                          v604 = (unsigned __int8 *)v713;
                          v605 = (_BYTE *)v716;
                          v606 = v696;
                          v607 = v589 >> 3;
                          do
                          {
                            v608 = v604[3] | ((v604[2] | (((*v604 << 8) | v604[1]) << 8)) << 8);
                            v609 = v604[7] | ((v604[6] | ((v604[5] | (v604[4] << 8)) << 8)) << 8);
                            v604 += 8;
                            v610 = v601 ^ v609 ^ v602 ^ v595 ^ v608 ^ 0xAB69605E;
                            v611 = v595 ^ v608 ^ (__ROR4__(v610, 22) + v603 * __ROR4__(v610 + 1419157410, 27));
                            v612 = v610 ^ (WORD1(v710) * __ROR4__(v611 + v602, 9) - __ROR4__(v611, 30));
                            v613 = v611 ^ (v692[0] * (v612 - v603) - (v612 >> 13));
                            v614 = v612 ^ (HIWORD(v710) * __ROR4__(WORD1(v710) ^ v613, 26) - __ROR4__(v613, 30));
                            v615 = v613 ^ (v602 - (v614 ^ 0xAB69605E));
                            v616 = v614 ^ (WORD1(v710) * (v603 ^ v615)) ^ __ROR4__(v615, 6);
                            v617 = v615 ^ (__ROR4__(v616, 30) + v692[0] * __ROR4__(v616 + v602, 15));
                            v618 = v616 ^ (HIWORD(v710) * __ROR4__(v617 + 1419157410, 14) - __ROR4__(v617, 24));
                            v619 = v617 ^ __ROR4__(v618, 10) ^ (v703 * __ROR4__(v618 ^ 0xAB69605E, 12));
                            v620 = v619
                                 ^ (HIWORD(v710)
                                  * (v692[0]
                                   + __ROR4__(~(v618 ^ (v619 >> 10) ^ (WORD1(v710) * (v619 ^ HIWORD(v710)))), 5)));
                            v621 = v618
                                 ^ (v619 >> 10)
                                 ^ (WORD1(v710) * (v619 ^ HIWORD(v710)))
                                 ^ (v620 - HIWORD(v710))
                                 ^ 0xAB69605E;
                            v622 = v620 ^ ((v621 >> 2) + v703 * __ROR4__(v621 ^ HIWORD(v710), 30));
                            v623 = v621 ^ (__ROR4__(v622, 25) + WORD1(v710) * __ROR4__(v622 - v602, 6));
                            v624 = v622 ^ (v692[0] * (v623 ^ v703) + __ROR4__(v623, 9));
                            v625 = v623 ^ (__ROR4__(v624, 25) + HIWORD(v710) * __ROR4__(v624 ^ WORD1(v710), 27));
                            v626 = v624 ^ v625 ^ v709;
                            v627 = v625 ^ (v703 * (__ROR4__(v626, 3) - WORD1(v710)));
                            v628 = v626 ^ (v692[0] * __ROR4__(v627 - v602, 1) - __ROR4__(v627, 6));
                            v629 = v627 ^ (__ROR4__(v628, 18) + HIWORD(v710) * __ROR4__(v628 - 1419157410, 29));
                            v630 = v628 ^ (v703 * __ROR4__(v629 - 1419157410, 17) - __ROR4__(v629, 14));
                            v631 = v629 ^ (v630 >> 3) ^ (WORD1(v710) * (v630 ^ v692[0]));
                            v595 = v606 ^ v630 ^ __ROR4__(v631, 30) ^ (v692[0] * __ROR4__(v631 ^ v602, 28));
                            v601 = v717 ^ v631;
                            v605[3] = v595;
                            v605[7] = v601;
                            v605[2] = __ROR4__(v595, 8);
                            v605[6] = __ROR4__(v601, 8);
                            v605[1] = __ROR4__(v595, 16);
                            v605[5] = __ROR4__(v601, 16);
                            *v605 = __ROR4__(v595, 24);
                            v605[4] = __ROR4__(v601, 24);
                            v606 = v608;
                            v717 = v609;
                            v605 += 8;
                            ++v720;
                            v603 = v703;
                          }
                          while ( v720 < v607 );
                          v587 = v697;
                          v19 = dwBytes;
                          v55 = v706;
                          v51 = v702;
                          v437 = (unsigned int *)v705;
                          v436 = (unsigned int *)v704;
                          v586 = v694;
                        }
                        for ( j = 0; j < pcchLength; ++j )
                          v587 ^= *((_BYTE *)v586 + j);
                        if ( v587 != *(_QWORD *)((char *)Src + pcchLength) )
                        {
                          MemoryFree(v586);
                          goto LABEL_759;
                        }
                        v633 = v698;
                        v634 = v700;
                        v717 = 0;
                        *(_QWORD *)&v692[1] = v586;
                        if ( (unsigned int)pcchLength < 4 )
                        {
                          v635 = -1073741762;
                          v517 = v694;
LABEL_803:
                          v491 = v633;
                          goto LABEL_804;
                        }
                        v635 = RtlULongLongAdd(v586, 4, &v692[1]);
                        if ( v635 >= 0 )
                        {
                          v635 = RtlUIntAdd(0, 4, &v717);
                          if ( v635 >= 0 )
                          {
                            if ( v637 - v717 < 4 )
                              goto LABEL_801;
                            v638 = (unsigned int)**(_DWORD **)&v692[1];
                            v696 = **(_DWORD **)&v692[1];
                            v635 = RtlULongLongAdd(*(_QWORD *)&v692[1], 4, &v692[1]);
                            if ( v635 < 0 )
                              goto LABEL_802;
                            v635 = RtlUIntAdd(v717, 4, &v717);
                            if ( v635 < 0 )
                              goto LABEL_802;
                            if ( v639 - v717 < (unsigned int)v638 )
                              goto LABEL_801;
                            v635 = RtlUIntAdd(v717, (unsigned int)v638, &v717);
                            if ( v635 >= 0 )
                            {
                              v641 = v640;
                              v642 = *(unsigned int **)&v692[1];
                              if ( (unsigned __int64)v636 + v641 >= v638 + *(_QWORD *)&v692[1]
                                && (unsigned __int64)v636 + v641 - v638 - *(_QWORD *)&v692[1] < 8 )
                              {
                                v709 = *v636;
                                v710 = 0;
                                v720 = 0;
                                v713 = 0;
                                LODWORD(v703) = 0;
                                if ( *(_QWORD *)&v692[1] )
                                {
                                  v635 = RtlULongLongAdd(*(_QWORD *)&v692[1], (unsigned int)v638, &v710);
                                  LODWORD(v701) = v635;
                                  v700 = v634;
                                  if ( v635 < 0 )
                                  {
                                    v491 = v633;
                                    v517 = v643;
LABEL_797:
                                    v652 = v691;
LABEL_798:
                                    if ( v635 >= 0 && v709 != v652 )
                                      v635 = -1073741762;
                                    goto LABEL_804;
                                  }
                                  v644 = v642;
                                  v728 = v642;
                                  v645 = v710;
                                  if ( v642 < v710 )
                                  {
                                    v694 = v643;
                                    v698 = v633;
                                    while ( 1 )
                                    {
                                      v635 = RtlULongLongAdd(v644, 4, &v720);
                                      if ( v635 < 0 )
                                        break;
                                      if ( v720 > (unsigned __int64)v710 )
                                      {
                                        v635 = -1073741811;
LABEL_786:
                                        v491 = v698;
                                        v517 = v694;
                                        goto LABEL_804;
                                      }
                                      v693 = 0;
                                      v635 = RtlUIntAdd(4, *v644, &v693);
                                      if ( v635 < 0 )
                                        goto LABEL_786;
                                      v707 = v55;
                                      v646 = v51;
                                      v647 = v437;
                                      v648 = v634;
                                      v716 = (SIZE_T)v634;
                                      v635 = RtlULongLongAdd(v644, v693, &v713);
                                      LODWORD(v701) = v635;
                                      v517 = v643;
                                      v700 = v648;
                                      v437 = v647;
                                      v491 = v633;
                                      v51 = v646;
                                      v55 = v707;
                                      if ( v635 < 0 )
                                        goto LABEL_797;
                                      v644 = (unsigned int *)v713;
                                      v728 = (void *)v713;
                                      v645 = v710;
                                      if ( v713 > (unsigned __int64)v710 )
                                      {
                                        v635 = -1073741811;
                                        v700 = (LPVOID)v716;
                                        goto LABEL_803;
                                      }
                                      LODWORD(v703) = v703 + 1;
                                      v694 = v643;
                                      v634 = (void *)v716;
                                      v700 = (LPVOID)v716;
                                      v698 = v633;
                                      if ( v713 >= (unsigned __int64)v710 )
                                      {
                                        v700 = (LPVOID)v716;
                                        goto LABEL_782;
                                      }
                                    }
                                    v491 = v698;
                                    v517 = v694;
                                    goto LABEL_797;
                                  }
LABEL_782:
                                  v517 = v643;
                                  v491 = v633;
                                  if ( v728 != v645 )
                                  {
                                    v635 = -1073741811;
LABEL_804:
                                    LODWORD(v701) = v635 | 0x10000000;
                                    goto LABEL_809;
                                  }
                                }
                                else
                                {
                                  LODWORD(v701) = 0;
                                  v700 = v634;
                                  v491 = v633;
                                  v517 = v636;
                                }
                                v649 = 0;
                                v720 = 0;
                                v650 = v696;
                                if ( v696 )
                                {
                                  v651 = GetProcessHeap();
                                  v649 = HeapAlloc(v651, 8u, v696);
                                  v720 = (SIZE_T)v649;
                                  if ( !v649 )
                                  {
                                    v635 = -1073741801;
                                    goto LABEL_804;
                                  }
                                  LODWORD(v701) = 0;
                                  v642 = *(unsigned int **)&v692[1];
                                  v650 = v696;
                                }
                                if ( v642 )
                                  memcpy_0(v649, v642, v650);
                                v699 = (unsigned int *)v720;
                                v652 = v703;
                                v691 = v703;
                                v635 = v701;
                                goto LABEL_798;
                              }
LABEL_801:
                              v635 = -1073741762;
                            }
                          }
                        }
LABEL_802:
                        v700 = v634;
                        v517 = v636;
                        goto LABEL_803;
                      }
                    }
                  }
                }
              }
            }
            v698 = v491;
            v525 = GetProcessHeap();
            HeapFree(v525, 0, v702);
          }
          v524 = v701;
          goto LABEL_628;
        }
LABEL_597:
        v436 = (unsigned int *)v710;
        v710 = 0;
        goto LABEL_598;
      }
      goto LABEL_850;
    }
    pcchLength = v719[1];
    if ( v414 )
    {
      do
      {
        v693 = 0;
        if ( (int)RtlUIntAdd(4, *v415, &v693) < 0 || (int)RtlULongLongAdd(v417, v693, &pcchLength) < 0 )
          goto LABEL_850;
        v415 = (unsigned int *)pcchLength;
      }
      while ( v419 + 1 < v418 );
    }
    if ( (int)RtlULongLongAdd(v415, 4, &v721) >= 0 && (unsigned __int64)(v420 + 3) <= v719[1] + HIDWORD(v719[0]) )
    {
      *v420 = 8;
      *(_QWORD *)v721 = v707;
      goto LABEL_539;
    }
LABEL_850:
    v52 = (unsigned __int64)v699;
    goto LABEL_851;
  }
LABEL_859:
  v14 = v732;
  v728 = 0;
  v736 = (int *)v738;
  v13 = v733;
LABEL_862:
  v10 = v735;
  v8 = v734;
  v9 = v739;
LABEL_863:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v728);
  if ( v19 >= 0 )
  {
    if ( v14 != 4 )
    {
LABEL_871:
      v19 = -1073418210;
      goto LABEL_875;
    }
    v19 = 0;
    v13 = *v736;
  }
  else
  {
    switch ( v19 )
    {
      case -805306316:
        v19 = -1073418222;
        break;
      case -805306139:
      case -1073425151:
        v19 = -1073418201;
        break;
      case -805306306:
        v19 = -1073418200;
        break;
      case -2147024774:
        goto LABEL_871;
    }
  }
LABEL_875:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v736);
  if ( v19 < 0 )
  {
    _DbgPrintMessage(8, "SLGetWindowsInformationDWORD FAILED with error 0x%x", v19);
    v12 = -2147024891;
    goto LABEL_885;
  }
  if ( !v13 )
  {
    v12 = -2147017842;
    _DbgPrintMessage(
      8,
      "No worker sessions allowed failed: 0x%x in %s",
      2147949454LL,
      "CWorkerTerminal::CWorkerTerminal");
    goto LABEL_885;
  }
  *((_QWORD *)v9 + 201) = LocalAlloc(0x40u, v8);
  v684 = LocalAlloc(0x40u, v10);
  *((_QWORD *)v9 + 203) = v684;
  if ( !*((_QWORD *)v9 + 201) || !v684 )
  {
    v685 = GetLastError();
    v12 = v685;
    if ( v685 > 0 )
      v12 = (unsigned __int16)v685 | 0x80070000;
    if ( v12 < 0 )
    {
      _DbgPrintMessage(8, "Memory Allocation failed: 0x%x in %s", (unsigned int)v12, "CWorkerTerminal::CWorkerTerminal");
      goto LABEL_885;
    }
  }
  memcpy_0(*((void **)v9 + 201), v745, v8);
  memcpy_0(*((void **)v9 + 203), v749, v10);
  *((_DWORD *)v9 + 404) = v8;
  *((_DWORD *)v9 + 408) = v10;
  *((_DWORD *)v9 + 436) = 0;
  v12 = 0;
  if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
  {
    v746 = "Worker";
    v747 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v686,
      (unsigned int)&word_1800CC21E,
      v687,
      v688,
      (__int64)&v747,
      (__int64)&v746);
  }
LABEL_889:
  *v748 = v12;
  return v9;
}

```

## disassembly

```asm
0x1800776b4  push    rbp
0x1800776b6  push    rbx
0x1800776b7  push    rsi
0x1800776b8  push    rdi
0x1800776b9  push    r12
0x1800776bb  push    r13
0x1800776bd  push    r14
0x1800776bf  push    r15
0x1800776c1  lea     rbp, [rsp-188h]
0x1800776c9  sub     rsp, 288h
0x1800776d0  mov     [rbp+1C0h+var_B0], r9
0x1800776d7  mov     r12d, r8d
0x1800776da  mov     [rbp+1C0h+var_14C], r8d
0x1800776de  mov     [rbp+1C0h+var_D0], rdx
0x1800776e5  mov     r15, rcx
0x1800776e8  mov     [rbp+1C0h+var_128], rcx
0x1800776ef  mov     [rbp+1C0h+var_A0], rcx
0x1800776f6  mov     r13d, dword ptr [rbp+1C0h+uBytes]
0x1800776fd  mov     [rbp+1C0h+var_148], r13d
0x180077701  mov     rax, [rbp+1C0h+arg_38]
0x180077708  mov     [rbp+1C0h+var_B8], rax
0x18007770f  call    ??0?$CTSPrivateObject@UIWorkerTerminal@@@@QEAA@PEBD@Z; CTSPrivateObject<IWorkerTerminal>::CTSPrivateObject<IWorkerTerminal>(char const *)
0x180077714  mov     [r15+638h], r15
0x18007771b  lea     rax, ??_7CWorkerTerminal@@6B@; const CWorkerTerminal::`vftable'
0x180077722  mov     [r15], rax
0x180077725  or      eax, 0FFFFFFFFh
0x180077728  mov     [r15+640h], eax
0x18007772f  xor     r14d, r14d
0x180077732  mov     [r15+648h], r14
0x180077739  mov     [r15+658h], r14
0x180077740  lea     rcx, [r15+668h]; this
0x180077747  mov     [rcx+60h], r14d
0x18007774b  mov     [r15+6D0h], eax
0x180077752  mov     eax, [rbp+1C0h+arg_28]
0x180077758  mov     [r15+6D4h], eax
0x18007775f  mov     rax, qword ptr [rbp+1C0h+arg_30.LowPart]
0x180077766  mov     [r15+6D8h], rax
0x18007776d  lock inc cs:?WorkerTerminalCount@CWorkerTerminal@@0JC; long volatile CWorkerTerminal::WorkerTerminalCount
0x180077774  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180077779  mov     ebx, eax
0x18007777b  test    eax, eax
0x18007777d  jns     short loc_180077792
0x18007777f  mov     r8d, eax
0x180077782  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x180077789  lea     ecx, [r14+8]
0x18007778d  jmp     loc_18007D61F
0x180077792  mov     edi, r14d
0x180077795  mov     [rbp+1C0h+var_150], r14d
0x180077799  mov     [rbp+1C0h+var_140], r14
0x1800777a0  mov     ebx, r14d
0x1800777a3  mov     dword ptr [rsp+2C0h+var_258], ebx
0x1800777a7  mov     [rbp+1C0h+var_168], r14
0x1800777ab  mov     edx, 4; uBytes
0x1800777b0  lea     ecx, [rdx+3Ch]; uFlags
0x1800777b3  call    cs:__imp_LocalAlloc
0x1800777ba  nop     dword ptr [rax+rax+00h]
0x1800777bf  mov     rdx, rax
0x1800777c2  lea     rcx, [rbp+1C0h+var_168]
0x1800777c6  call    ??4?$SP@EV?$SP_HLOCAL@E@@@@QEAAAEAV0@V?$CTypeWrapper@PEAE@@@Z; SP<uchar,SP_HLOCAL<uchar>>::operator=(CTypeWrapper<uchar *>)
0x1800777cb  mov     esi, 8
0x1800777d0  mov     rax, [rbp+1C0h+var_168]
0x1800777d4  mov     [rbp+1C0h+var_130], rax
0x1800777db  test    rax, rax
0x1800777de  jz      loc_18007D4E3
0x1800777e4  mov     [rbp+1C0h+var_154], r14d
0x1800777e8  mov     [rbp+1C0h+var_15C], r14d
0x1800777ec  xorps   xmm0, xmm0
0x1800777ef  movups  xmmword ptr [rbp+1C0h+lpMem], xmm0
0x1800777f3  mov     [rbp+1C0h+var_218], r14
0x1800777f7  call    cs:__imp_GetProcessHeap
0x1800777fe  nop     dword ptr [rax+rax+00h]
0x180077803  mov     rcx, rax; hHeap
0x180077806  mov     r8d, 0A0h; dwBytes
0x18007780c  mov     edx, esi; dwFlags
0x18007780e  call    cs:__imp_HeapAlloc
0x180077815  nop     dword ptr [rax+rax+00h]
0x18007781a  mov     r15, rax
0x18007781d  mov     r13d, 0D0000017h
0x180077823  mov     dword ptr [rbp+1C0h+var_240], r13d
0x180077827  mov     rbx, 0C81ECB17B1B54A58h
0x180077831  mov     [rbp+1C0h+var_1B8], 0FFFFFFFFh
0x180077838  mov     rdi, 7F1137FAB69605Eh
0x180077842  mov     r14d, 0C0000017h
0x180077848  test    rax, rax
0x18007784b  jnz     short loc_18007785A
0x18007784d  xor     r12d, r12d
0x180077850  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x180077855  jmp     loc_180077CB7
0x18007785a  movups  xmm0, cs:xmmword_1800DF540
0x180077861  movups  xmmword ptr [rax], xmm0
0x180077864  movups  xmm1, cs:xmmword_1800DF550
0x18007786b  movups  xmmword ptr [rax+10h], xmm1
0x18007786f  movups  xmm0, cs:xmmword_1800DF560
0x180077876  movups  xmmword ptr [rax+20h], xmm0
0x18007787a  movups  xmm1, cs:xmmword_1800DF570
0x180077881  movups  xmmword ptr [rax+30h], xmm1
0x180077885  movups  xmm0, cs:xmmword_1800DF580
0x18007788c  movups  xmmword ptr [rax+40h], xmm0
0x180077890  movups  xmm1, cs:xmmword_1800DF590
0x180077897  movups  xmmword ptr [rax+50h], xmm1
0x18007789b  movups  xmm0, cs:xmmword_1800DF5A0
0x1800778a2  movups  xmmword ptr [rax+60h], xmm0
0x1800778a6  movups  xmm1, cs:xmmword_1800DF5B0
0x1800778ad  movups  xmmword ptr [rax+70h], xmm1
0x1800778b1  movups  xmm0, cs:xmmword_1800DF5C0
0x1800778b8  movups  xmmword ptr [rax+80h], xmm0
0x1800778bf  movups  xmm1, cs:xmmword_1800DF5D0
0x1800778c6  movups  xmmword ptr [rax+90h], xmm1
0x1800778cd  call    cs:__imp_GetProcessHeap
0x1800778d4  nop     dword ptr [rax+rax+00h]
0x1800778d9  mov     rcx, rax; hHeap
0x1800778dc  mov     r8, rsi; dwBytes
0x1800778df  mov     edx, esi; dwFlags
0x1800778e1  call    cs:__imp_HeapAlloc
0x1800778e8  nop     dword ptr [rax+rax+00h]
0x1800778ed  mov     r12, rax
0x1800778f0  test    rax, rax
0x1800778f3  jnz     short loc_1800778FF
0x1800778f5  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x1800778fa  jmp     loc_180077CB7
0x1800778ff  mov     rax, cs:qword_1800DF480
0x180077906  mov     [r12], rax
0x18007790a  rdtsc
0x18007790c  shl     rdx, 20h
0x180077910  or      rax, rdx
0x180077913  mov     [rbp+1C0h+var_198], rax
0x180077917  mov     dword ptr [rsp+2C0h+dwBytes+4], 0
0x18007791f  mov     [rsp+2C0h+var_288], 0
0x180077927  lea     r8, [rsp+2C0h+var_288]
0x18007792c  mov     r10d, 4
0x180077932  mov     edx, r10d
0x180077935  mov     ecx, r10d
0x180077938  call    RtlUIntAdd
0x18007793d  mov     r14d, eax
0x180077940  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077944  test    eax, eax
0x180077946  js      loc_180077CB7
0x18007794c  lea     r8, [rsp+2C0h+dwBytes+4]
0x180077951  mov     edx, [rsp+2C0h+var_288]
0x180077955  xor     ecx, ecx
0x180077957  call    RtlUIntAdd
0x18007795c  mov     r14d, eax
0x18007795f  or      r14d, 10000000h
0x180077966  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x18007796b  jl      loc_180077CB7
0x180077971  mov     [rsp+2C0h+var_288], ecx
0x180077975  lea     r8, [rsp+2C0h+var_288]
0x18007797a  mov     edx, 0A0h
0x18007797f  mov     ecx, r10d
0x180077982  call    RtlUIntAdd
0x180077987  mov     r14d, eax
0x18007798a  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x18007798e  test    eax, eax
0x180077990  js      loc_180077CB7
0x180077996  lea     r8, [rsp+2C0h+dwBytes+4]
0x18007799b  mov     edx, [rsp+2C0h+var_288]
0x18007799f  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x1800779a3  call    RtlUIntAdd
0x1800779a8  mov     r14d, eax
0x1800779ab  or      r14d, 10000000h
0x1800779b2  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x1800779b7  jl      loc_180077CB7
0x1800779bd  mov     [rsp+2C0h+var_288], 0
0x1800779c5  lea     r8, [rsp+2C0h+var_288]
0x1800779ca  mov     edx, esi
0x1800779cc  mov     ecx, r10d
0x1800779cf  call    RtlUIntAdd
0x1800779d4  mov     r14d, eax
0x1800779d7  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x1800779db  test    eax, eax
0x1800779dd  js      loc_180077CB7
0x1800779e3  lea     r8, [rsp+2C0h+dwBytes+4]
0x1800779e8  mov     edx, [rsp+2C0h+var_288]
0x1800779ec  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x1800779f0  call    RtlUIntAdd
0x1800779f5  mov     r14d, eax
0x1800779f8  or      r14d, 10000000h
0x1800779ff  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x180077a04  jl      loc_180077CB7
0x180077a0a  mov     [rsp+2C0h+var_288], 0
0x180077a12  lea     r8, [rsp+2C0h+var_288]
0x180077a17  mov     edx, esi
0x180077a19  mov     ecx, r10d
0x180077a1c  call    RtlUIntAdd
0x180077a21  mov     r14d, eax
0x180077a24  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077a28  test    eax, eax
0x180077a2a  js      loc_180077CB7
0x180077a30  lea     r8, [rsp+2C0h+dwBytes+4]
0x180077a35  mov     edx, [rsp+2C0h+var_288]
0x180077a39  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x180077a3d  call    RtlUIntAdd
0x180077a42  mov     r14d, eax
0x180077a45  or      r14d, 10000000h
0x180077a4c  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x180077a51  jl      loc_180077CB7
0x180077a57  mov     [rbp+1C0h+pcchLength], 0
0x180077a5f  lea     r8, [rbp+1C0h+pcchLength]; pcchLength
0x180077a63  lea     rcx, aTerminalservic_5; "TerminalServices-RemoteConnectionManage"...
0x180077a6a  call    StringCchLengthW
0x180077a6f  test    eax, eax
0x180077a71  jns     short loc_180077A7E
0x180077a73  mov     r14d, 0C000003Eh
0x180077a79  jmp     loc_180079503
0x180077a7e  mov     rdx, [rbp+1C0h+pcchLength]
0x180077a82  inc     rdx
0x180077a85  mov     [rsp+2C0h+var_288], 0
0x180077a8d  add     edx, edx
0x180077a8f  lea     r8, [rsp+2C0h+var_288]
0x180077a94  mov     r10d, 4
0x180077a9a  mov     ecx, r10d
0x180077a9d  call    RtlUIntAdd
0x180077aa2  mov     r14d, eax
0x180077aa5  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077aa9  test    eax, eax
0x180077aab  js      loc_180077CB7
0x180077ab1  lea     r8, [rsp+2C0h+dwBytes+4]
0x180077ab6  mov     edx, [rsp+2C0h+var_288]
0x180077aba  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x180077abe  call    RtlUIntAdd
0x180077ac3  mov     r14d, eax
0x180077ac6  or      r14d, 10000000h
0x180077acd  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x180077ad2  jl      loc_180077CB7
0x180077ad8  mov     [rsp+2C0h+var_288], 0
0x180077ae0  lea     r8, [rsp+2C0h+var_288]
0x180077ae5  mov     edx, r10d
0x180077ae8  mov     ecx, r10d
0x180077aeb  call    RtlUIntAdd
0x180077af0  mov     r14d, eax
0x180077af3  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077af7  test    eax, eax
0x180077af9  js      loc_180077CB7
0x180077aff  lea     r8, [rsp+2C0h+dwBytes+4]
0x180077b04  mov     edx, [rsp+2C0h+var_288]
0x180077b08  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x180077b0c  call    RtlUIntAdd
0x180077b11  mov     r14d, eax
0x180077b14  or      r14d, 10000000h
0x180077b1b  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x180077b20  jl      loc_180077CB7
0x180077b26  mov     [rsp+2C0h+var_288], 0
0x180077b2e  lea     r8, [rsp+2C0h+var_288]
0x180077b33  mov     edx, r10d
0x180077b36  mov     ecx, r10d
0x180077b39  call    RtlUIntAdd
0x180077b3e  mov     r14d, eax
0x180077b41  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077b45  test    eax, eax
0x180077b47  js      loc_180077CB7
0x180077b4d  lea     r8, [rsp+2C0h+dwBytes+4]
0x180077b52  mov     edx, [rsp+2C0h+var_288]
0x180077b56  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x180077b5a  call    RtlUIntAdd
0x180077b5f  mov     r14d, eax
0x180077b62  or      r14d, 10000000h
0x180077b69  mov     dword ptr [rsp+2C0h+dwBytes], r14d
0x180077b6e  jl      loc_180077CB7
0x180077b74  mov     eax, dword ptr [rsp+2C0h+dwBytes+4]
0x180077b78  mov     dword ptr [rbp+1C0h+lpMem+4], eax
0x180077b7b  mov     esi, eax
0x180077b7d  call    cs:__imp_GetProcessHeap
0x180077b84  nop     dword ptr [rax+rax+00h]
0x180077b89  mov     rcx, rax; hHeap
0x180077b8c  mov     r8d, esi; dwBytes
0x180077b8f  mov     esi, 8
0x180077b94  mov     edx, esi; dwFlags
0x180077b96  call    cs:__imp_HeapAlloc
0x180077b9d  nop     dword ptr [rax+rax+00h]
0x180077ba2  mov     r9, rax
0x180077ba5  test    rax, rax
0x180077ba8  jnz     short loc_180077BB5
0x180077baa  mov     r14d, 0C0000017h
0x180077bb0  jmp     loc_180079503
0x180077bb5  xor     eax, eax
0x180077bb7  mov     dword ptr [rsp+2C0h+var_284], eax
0x180077bbb  mov     [rbp+1C0h+lpMem+8], r9
0x180077bbf  xor     r10d, r10d
0x180077bc2  mov     dword ptr [rbp+1C0h+lpMem], r10d
0x180077bc6  mov     qword ptr [rbp+1C0h+var_20C], rax
0x180077bca  mov     [rbp-50h], rax
0x180077bce  test    r9, r9
0x180077bd1  jnz     short loc_180077C20
0x180077bd3  mov     [rsp+2C0h+var_288], eax
0x180077bd7  lea     r8, [rsp+2C0h+var_288]
0x180077bdc  lea     edx, [rax+4]
0x180077bdf  mov     ecx, edx
0x180077be1  call    RtlUIntAdd
0x180077be6  mov     r14d, eax
0x180077be9  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077bed  test    eax, eax
0x180077bef  js      loc_180077CA3
0x180077bf5  lea     r8, [rbp+1C0h+lpMem+4]
0x180077bf9  mov     edx, [rsp+2C0h+var_288]
0x180077bfd  mov     ecx, dword ptr [rbp+1C0h+lpMem+4]
0x180077c00  call    RtlUIntAdd
0x180077c05  mov     r14d, eax
0x180077c08  mov     dword ptr [rsp+2C0h+dwBytes], eax
0x180077c0c  test    eax, eax
0x180077c0e  js      loc_180077CA3
  ... truncated ...
```
