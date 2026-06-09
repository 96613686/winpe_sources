# RetrieveProvisioningPayloadCallback(ushort const *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,int,ushort const *,ushort * *,ulong,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *,ushort * *,ushort * *,ulong *,int *,ulong *)

- ea: `0x18002f6bc`
- end: `0x1800307fe`
- name: `?RetrieveProvisioningPayloadCallback@@YAJPEBGPEAUHKEY__@@0000W4MDMAuthPolicy@@HH0PEAPEAGKKKK0000PEAPEAEPEAK335PEAH5@Z`
- size: `4418`
- prototype: `int __high(const unsigned __int16 *, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum MDMAuthPolicy, int, int, const unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002d32c`

## callees

- `0x1800026d0`
- `0x180002ae0`
- `0x18000bd08`
- `0x180012f70`
- `0x1800141b0`
- `0x1800194e0`
- `0x180019f44`
- `0x18001b028`
- `0x18001cb08`
- `0x18001d684`
- `0x18001dc4c`
- `0x180021458`
- `0x180021db4`
- `0x180022e74`
- `0x1800284a0`
- `0x180029ac4`
- `0x18002bcdc`
- `0x18002eb4c`
- `0x18002f04c`
- `0x18002f6bc`
- `0x180034b80`
- `0x180041410`
- `0x1800432c4`
- `0x180043738`
- `0x180044e94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fb0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fbb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fb0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fbb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f92c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f95a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f9b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f9e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fa12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fa40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fc69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fc92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fcb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fdbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fded`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003031a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003035d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800303a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f92c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f95a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f9b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f9e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fa12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fa40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fbf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fc69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fc92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fcb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fdbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fded`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fe77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800302dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003031a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003035d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800303a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fa2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002faf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fbe4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fcca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fdab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fdd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002febf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030255`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003028f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030306`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030349`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003038c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fa2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002faf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fbe4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fc7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fcca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fd2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fdab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fdd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fe91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002febf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030255`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003028f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800302c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030306`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030349`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003038c`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180030455`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180030499`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180030455`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180030499`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x180030411`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x180030411`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002f88e`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002f88e`
- `DMCmnUtils!DmRevertToSelf` at `0x180030467`
- `DMCmnUtils!DmRevertToSelf` at `0x180030467`
- `DMCmnUtils!DmImpersonate` at `0x18003043d`
- `DMCmnUtils!DmImpersonate` at `0x18003043d`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall RetrieveProvisioningPayloadCallback(
        __int64 a1,
        HKEY a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        unsigned __int16 **a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        unsigned int a15,
        __int64 a16,
        unsigned __int16 *a17,
        unsigned __int16 *a18,
        unsigned __int16 *a19,
        unsigned __int8 **a20,
        unsigned int *a21,
        unsigned __int16 **a22,
        unsigned __int16 **a23,
        unsigned int *a24,
        signed int *a25,
        __int64 a26)
{
  unsigned int *v27; // r14
  unsigned __int16 *v28; // rdi
  unsigned __int8 *v29; // r15
  int DWORD; // eax
  unsigned int v31; // ebx
  void *v32; // rdi
  HANDLE ProcessHeap; // rax
  void *v34; // rdi
  HANDLE v35; // rax
  void *v36; // rdi
  HANDLE v37; // rax
  void *v38; // rdi
  HANDLE v39; // rax
  void *v40; // rdi
  HANDLE v41; // rax
  void *v42; // rdi
  HANDLE v43; // rax
  void *v44; // rdi
  HANDLE v45; // rax
  __int64 v47; // rcx
  __int64 v48; // r8
  unsigned int v49; // esi
  unsigned __int64 v50; // rsi
  HANDLE v51; // rax
  unsigned __int16 *v52; // rax
  const unsigned __int16 *v53; // r8
  HANDLE v54; // rax
  unsigned __int16 *v55; // rax
  unsigned __int16 *v56; // r14
  unsigned __int16 *v57; // rbx
  HANDLE v58; // rax
  _BYTE *v59; // rbx
  __int64 v60; // rcx
  _WORD *v61; // rax
  __int64 v62; // rdx
  HANDLE v63; // rax
  HANDLE v64; // rax
  HANDLE v65; // rax
  HANDLE v66; // rax
  __int64 v67; // rax
  unsigned __int16 *v68; // rcx
  __int64 v69; // rcx
  unsigned __int16 *i; // rax
  HANDLE v71; // rax
  unsigned int v72; // edi
  void *v73; // rbx
  HANDLE v74; // rax
  void *v75; // rbx
  HANDLE v76; // rax
  void *v77; // rbx
  HANDLE v78; // rax
  void *v79; // rbx
  HANDLE v80; // rax
  void *v81; // rbx
  HANDLE v82; // rax
  void *v83; // rbx
  HANDLE v84; // rax
  void *v85; // rbx
  HANDLE v86; // rax
  unsigned int v87; // r8d
  __int64 v88; // rcx
  unsigned int v89; // r8d
  __int64 v90; // rcx
  __int64 v91; // r8
  unsigned int v92; // r8d
  unsigned int v93; // r9d
  HKEY v94; // r14
  int v95; // edx
  int v96; // ecx
  void *v97; // rbx
  HANDLE v98; // rax
  void *v99; // rbx
  HANDLE v100; // rax
  void *v101; // rbx
  HANDLE v102; // rax
  void *v103; // rbx
  HANDLE v104; // rax
  void *v105; // rbx
  HANDLE v106; // rax
  void *v107; // rbx
  HANDLE v108; // rax
  CEnrollmentLogger *Logger; // rax
  wil::details::in1diag3 *v110; // rcx
  int v111; // eax
  unsigned int v112; // r8d
  signed int *v113; // rbx
  int v114; // eax
  __int64 v115; // rcx
  int v116; // eax
  __int64 v117; // rcx
  __int64 v118; // r8
  CEnrollmentLogger *v119; // rax
  int lpWideCharStr; // [rsp+20h] [rbp-140h]
  int String; // [rsp+E0h] [rbp-80h] BYREF
  int v122; // [rsp+E4h] [rbp-7Ch] BYREF
  __int16 v123; // [rsp+E8h] [rbp-78h]
  unsigned int *v124; // [rsp+F0h] [rbp-70h] BYREF
  unsigned __int16 *v125; // [rsp+F8h] [rbp-68h] BYREF
  int v126; // [rsp+100h] [rbp-60h] BYREF
  LPCVOID lpBuffer; // [rsp+108h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+110h] [rbp-50h] BYREF
  LPVOID v129; // [rsp+118h] [rbp-48h] BYREF
  LPVOID v130; // [rsp+120h] [rbp-40h] BYREF
  LPVOID v131; // [rsp+128h] [rbp-38h] BYREF
  LPVOID v132; // [rsp+130h] [rbp-30h] BYREF
  LPVOID v133; // [rsp+138h] [rbp-28h] BYREF
  LPVOID v134; // [rsp+140h] [rbp-20h] BYREF
  unsigned int v135; // [rsp+148h] [rbp-18h] BYREF
  unsigned int v136; // [rsp+14Ch] [rbp-14h] BYREF
  unsigned int v137; // [rsp+150h] [rbp-10h] BYREF
  unsigned int v138; // [rsp+154h] [rbp-Ch] BYREF
  unsigned int v139; // [rsp+158h] [rbp-8h] BYREF
  unsigned int v140; // [rsp+15Ch] [rbp-4h] BYREF
  unsigned int v141; // [rsp+160h] [rbp+0h] BYREF
  unsigned int v142; // [rsp+164h] [rbp+4h] BYREF
  unsigned __int16 *v143; // [rsp+168h] [rbp+8h] BYREF
  unsigned __int16 **v144; // [rsp+170h] [rbp+10h] BYREF
  HKEY v145; // [rsp+178h] [rbp+18h]
  LPCVOID v146[2]; // [rsp+180h] [rbp+20h] BYREF
  unsigned __int16 *v147; // [rsp+190h] [rbp+30h] BYREF
  unsigned __int8 *v148; // [rsp+198h] [rbp+38h] BYREF
  LPVOID *v149; // [rsp+1A0h] [rbp+40h]
  unsigned __int8 *v150; // [rsp+1A8h] [rbp+48h] BYREF
  char v151; // [rsp+1B0h] [rbp+50h]
  LPVOID *v152; // [rsp+1B8h] [rbp+58h]
  unsigned __int8 *v153; // [rsp+1C0h] [rbp+60h] BYREF
  char v154; // [rsp+1C8h] [rbp+68h]
  LPVOID *v155; // [rsp+1D0h] [rbp+70h]
  unsigned __int8 *v156; // [rsp+1D8h] [rbp+78h] BYREF
  char v157; // [rsp+1E0h] [rbp+80h]
  LPVOID *v158; // [rsp+1E8h] [rbp+88h]
  unsigned __int8 *v159; // [rsp+1F0h] [rbp+90h] BYREF
  char v160; // [rsp+1F8h] [rbp+98h]
  LPVOID *p_lpMem; // [rsp+200h] [rbp+A0h]
  unsigned __int8 *v162; // [rsp+208h] [rbp+A8h] BYREF
  char v163; // [rsp+210h] [rbp+B0h]
  char v164[8]; // [rsp+220h] [rbp+C0h] BYREF
  void *v165; // [rsp+228h] [rbp+C8h]
  _WORD *v166; // [rsp+230h] [rbp+D0h]
  _WORD v167[8]; // [rsp+238h] [rbp+D8h] BYREF
  void *Block; // [rsp+248h] [rbp+E8h]
  _WORD *v169; // [rsp+250h] [rbp+F0h]
  _WORD v170[12]; // [rsp+258h] [rbp+F8h] BYREF
  unsigned __int16 *v171; // [rsp+270h] [rbp+110h]
  unsigned __int16 *v172; // [rsp+278h] [rbp+118h]
  unsigned __int16 *v173; // [rsp+280h] [rbp+120h]
  __int64 v174; // [rsp+288h] [rbp+128h]
  __int64 v175; // [rsp+290h] [rbp+130h]
  unsigned __int16 *v176; // [rsp+298h] [rbp+138h]
  __int64 v177; // [rsp+2A0h] [rbp+140h]
  unsigned __int16 *v178; // [rsp+2A8h] [rbp+148h]
  __int64 v179; // [rsp+2B0h] [rbp+150h]
  signed int *v180; // [rsp+2B8h] [rbp+158h]
  __int64 v181; // [rsp+2C0h] [rbp+160h]
  unsigned __int8 **v182; // [rsp+2C8h] [rbp+168h]
  unsigned int *v183; // [rsp+2D0h] [rbp+170h]
  _QWORD v184[2]; // [rsp+2D8h] [rbp+178h] BYREF
  __int64 v185; // [rsp+2E8h] [rbp+188h]
  LPVOID *v186; // [rsp+2F0h] [rbp+190h] BYREF
  unsigned __int8 *v187; // [rsp+2F8h] [rbp+198h] BYREF
  char v188; // [rsp+300h] [rbp+1A0h]
  WCHAR LocaleName[256]; // [rsp+310h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+408h]

  v177 = a4;
  v178 = a3;
  v145 = a2;
  v181 = a1;
  v176 = a5;
  v175 = a6;
  v174 = a10;
  v144 = a11;
  v185 = a16;
  v172 = a17;
  v171 = a18;
  v173 = a19;
  v182 = a20;
  v183 = a21;
  v27 = a24;
  v124 = a24;
  v180 = a25;
  v179 = a26;
  String = 0;
  v147 = 0;
  lpBuffer = 0;
  v28 = 0;
  v146[0] = 0;
  v29 = 0;
  v148 = 0;
  v141 = 0;
  v143 = 0;
  v125 = 0;
  v140 = 0;
  v126 = 0;
  v139 = 0;
  v142 = 0;
  v138 = 0;
  v134 = 0;
  v133 = 0;
  v132 = 0;
  v131 = 0;
  v137 = 0;
  v136 = 0;
  v130 = 0;
  v129 = 0;
  lpMem = 0;
  v135 = 0;
  v165 = v167;
  v166 = v167;
  v167[0] = 0;
  Block = v170;
  v169 = v170;
  v170[0] = 0;
  v184[0] = "RetrieveProvisioningPayloadCallback";
  v184[1] = &String;
  DWORD = OmaDmRegistryGetDWORD(a2, 0, L"RenewROBOSupport", (unsigned int *)&v126);
  v31 = DWORD;
  String = DWORD;
  if ( DWORD == -2147024894 || DWORD == -2147023267 )
  {
    v126 = 0;
    String = 0;
  }
  else if ( DWORD < 0 )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v184);
    if ( Block != v170 )
      operator delete(Block);
    if ( v165 != v167 )
      operator delete(v165);
    v32 = lpMem;
    lpMem = 0;
    if ( v32 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v32);
    }
    v34 = v129;
    v129 = 0;
    if ( v34 )
    {
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v34);
    }
    v36 = v130;
    v130 = 0;
    if ( v36 )
    {
      v37 = GetProcessHeap();
      HeapFree(v37, 0, v36);
    }
    v38 = v131;
    v131 = 0;
    if ( v38 )
    {
      v39 = GetProcessHeap();
      HeapFree(v39, 0, v38);
    }
    v40 = v132;
    v132 = 0;
    if ( v40 )
    {
      v41 = GetProcessHeap();
      HeapFree(v41, 0, v40);
    }
    v42 = v133;
    v133 = 0;
    if ( v42 )
    {
      v43 = GetProcessHeap();
      HeapFree(v43, 0, v42);
    }
    v44 = v134;
    v134 = 0;
    if ( v44 )
    {
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v44);
    }
    return v31;
  }
  String = ParseServiceURL(a3, &v140, &v143, &v125, 0);
  if ( String < 0 )
    goto LABEL_39;
  v49 = a15;
  if ( (a15 & 0x80u) != 0 )
  {
    v94 = v145;
  }
  else
  {
    if ( !*a22 )
    {
      v50 = (-(__int64)((a15 & 0x20) != 0) & 0xFFFFFFFFFFFFFFF7uLL) + 23;
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_API_PROVIDER_Context,
          UsingDefaultHashAlgorithmEvent,
          v48,
          1,
          &v186);
      String = 0;
      v51 = GetProcessHeap();
      v52 = (unsigned __int16 *)HeapAlloc(v51, 8u, 2 * v50);
      *a22 = v52;
      if ( !v52 )
        goto LABEL_38;
      v53 = L"1.3.14.3.2.29";
      if ( (a15 & 0x20) == 0 )
        v53 = L"2.16.840.1.101.3.4.2.1";
      String = StringCchCopyW(v52, v50, v53);
      if ( String < 0 )
        goto LABEL_39;
      v49 = a15;
      v27 = v124;
    }
    if ( !*a23 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_API_PROVIDER_Context,
          UsingDefaultPrivateKeyAlgorithmEvent,
          v48,
          1,
          &v186);
      String = 0;
      v54 = GetProcessHeap();
      v55 = (unsigned __int16 *)HeapAlloc(v54, 8u, 0x2Au);
      *a23 = v55;
      if ( !v55 )
      {
LABEL_38:
        String = -2147024882;
LABEL_39:
        v56 = v125;
        goto LABEL_40;
      }
      String = StringCchCopyW(v55, 0x15u, L"1.2.840.113549.1.1.1");
      if ( String < 0 )
        goto LABEL_39;
    }
    v87 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
    if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
    {
      v124 = *(unsigned int **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                                 v47,
                                 &v124);
      v87 = (unsigned int)v124;
    }
    v122 = 0;
    v123 = 3;
    wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v87 >> 10) & 1, (v87 >> 11) & 1, &v122, 1);
    v89 = *(_DWORD *)Feature_UseTPMForEnrollmentKey__descriptor;
    if ( (*(_DWORD *)Feature_UseTPMForEnrollmentKey__descriptor & 4) == 0 )
    {
      v124 = *(unsigned int **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseTPMForEnrollmentKey>::GetCachedFeatureEnabledState(
                                 v88,
                                 &v124);
      v89 = (unsigned int)v124;
    }
    v122 = 0;
    v123 = 3;
    wil::details::ReportUsageToService(&qword_180070E18, 31513978, (v89 >> 10) & 1, (v89 >> 11) & 1, &v122, 1);
    if ( !CheckServerIsVersionOrAbove(v49, 5) && !*v27 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
        McGenEventWrite_EventWriteTransfer(
          WP_ENROLLMENT_API_PROVIDER_Context,
          UsingDefaultKeyLengthEvent,
          v91,
          1,
          &v186);
      *v27 = 2048;
    }
    v92 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
    if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
    {
      v124 = *(unsigned int **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                                 v90,
                                 &v124);
      v92 = (unsigned int)v124;
    }
    v122 = 0;
    v123 = 3;
    wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v92 >> 10) & 1, (v92 >> 11) & 1, &v122, 1);
    p_lpMem = &lpMem;
    v162 = 0;
    v163 = 1;
    v158 = &v129;
    v159 = 0;
    v160 = 1;
    v155 = &v130;
    v156 = 0;
    v157 = 1;
    v152 = &v131;
    v153 = 0;
    v154 = 1;
    v149 = &v132;
    v150 = 0;
    v151 = 1;
    v186 = &v133;
    v187 = 0;
    v188 = 1;
    v93 = *v27;
    v94 = v145;
    String = GenerateCertRequestOld(
               v145,
               (const unsigned __int16 **)v144,
               a12,
               v93,
               *a22,
               *a23,
               a8,
               v49,
               a13,
               a14,
               v172,
               v171,
               v173,
               &v187,
               &v139,
               &v150,
               &v142,
               &v153,
               &v138,
               &v147,
               &v156,
               &v137,
               &v159,
               &v136,
               &v162,
               &v135,
               (struct _ATTESTATION_STATUS *)v164);
    if ( v188 )
    {
      v96 = (int)v186;
      v97 = *v186;
      *v186 = v187;
      if ( v97 )
      {
        v98 = GetProcessHeap();
        HeapFree(v98, 0, v97);
      }
    }
    if ( v151 )
    {
      v96 = (int)v149;
      v99 = *v149;
      *v149 = v150;
      if ( v99 )
      {
        v100 = GetProcessHeap();
        HeapFree(v100, 0, v99);
      }
    }
    if ( v154 )
    {
      v96 = (int)v152;
      v101 = *v152;
      *v152 = v153;
      if ( v101 )
      {
        v102 = GetProcessHeap();
        HeapFree(v102, 0, v101);
      }
    }
    if ( v157 )
    {
      v96 = (int)v155;
      v103 = *v155;
      *v155 = v156;
      if ( v103 )
      {
        v104 = GetProcessHeap();
        HeapFree(v104, 0, v103);
      }
    }
    if ( v160 )
    {
      v96 = (int)v158;
      v105 = *v158;
      *v158 = v159;
      if ( v105 )
      {
        v106 = GetProcessHeap();
        HeapFree(v106, 0, v105);
      }
    }
    if ( v163 )
    {
      v96 = (int)p_lpMem;
      v107 = *p_lpMem;
      *p_lpMem = v162;
      if ( v107 )
      {
        v108 = GetProcessHeap();
        HeapFree(v108, 0, v107);
      }
    }
    if ( String < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zzd_EventWriteTransfer(v96, v95, (unsigned int)*a22, (unsigned int)*a23, String);
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollGenerateCertRequestFail(Logger, String, *a22, *a23, v49);
      String = -2145910745;
      goto LABEL_39;
    }
  }
  String = OmDmRegistryAllocAndGetString(v94, L"SID", 1, &v134);
  v122 = 0;
  LocaleName[0] = 0;
  if ( String < 0 )
    goto LABEL_126;
  String = DmImpersonate((const unsigned __int16 *)v134);
  GetUserDefaultLocaleName(LocaleName, 255);
  if ( String >= 0 )
  {
    v111 = DmRevertToSelf();
    v110 = retaddr;
    if ( v111 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\enrollclient.cpp",
        (const char *)(unsigned int)v111,
        lpWideCharStr);
    v122 = 1;
  }
  if ( !LocaleName[0] )
LABEL_126:
    GetUserDefaultLocaleName(LocaleName, 255);
  v112 = *(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor;
  if ( (*(_DWORD *)Feature_EnrollmentAttestationDebugFields__descriptor & 4) == 0 )
  {
    v144 = *(unsigned __int16 ***)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetCachedFeatureEnabledState(
                                    v110,
                                    &v144);
    v112 = (unsigned int)v144;
  }
  LODWORD(v124) = 0;
  WORD2(v124) = 3;
  wil::details::ReportUsageToService(&qword_180070DB0, 46391183, (v112 >> 10) & 1, (v112 >> 11) & 1, &v124, 1);
  String = CreateEnrollMessage(
             v178,
             v147,
             (const unsigned __int8 *)v133,
             v139,
             (const unsigned __int8 *)v132,
             v142,
             (const unsigned __int8 *)v131,
             v138,
             (const unsigned __int8 *)v130,
             v137,
             v129,
             v136,
             (__int64)lpMem,
             v135,
             (__int64)v164,
             v126,
             v177,
             v176,
             v175,
             LocaleName,
             a7,
             a8,
             v122,
             a9,
             v174,
             a15,
             (unsigned __int16 **)&lpBuffer);
  v56 = v125;
  if ( String < 0 )
  {
    v28 = (unsigned __int16 *)v146[0];
  }
  else
  {
    v113 = v180;
    String = SendRequestAndGetResponse(v181, 3, v143, v140, v125, lpBuffer, a15, v185, v146, v180, v179);
    v114 = WriteToTempFile(lpBuffer, L"SoapRequest.txt");
    if ( v114 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v115, SavingTempFileFailedEvent, L"SoapRequest.txt", (unsigned int)v114);
    v28 = (unsigned __int16 *)v146[0];
    v116 = WriteToTempFile((_WORD *)v146[0], L"SoapResponse.txt");
    if ( v116 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
      McTemplateU0zq_EventWriteTransfer(v117, SavingTempFileFailedEvent, L"SoapResponse.txt", (unsigned int)v116);
    if ( (int)LogServerTransaction(lpBuffer, 0, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (int)LogServerTransaction(v28, 1, 0) < 0 && v28 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( String >= 0 )
    {
      if ( *v113 == 200 )
      {
        String = GetCertFromResponse(v28, &v148, &v141);
        if ( String >= 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsEnrollCertificateResponseProcessedSuccess,
            v118,
            1,
            &v186);
        v29 = v148;
      }
      else
      {
        v29 = 0;
      }
      if ( *v113 == 200 && String >= 0
        || (String = GetWSSecurityFaultMessage(v28, v145, *v113),
            v119 = CEnrollmentLogger::GetLogger(),
            CEnrollmentLogger::LogEnrollCertificateResponseFail(v119, String),
            String >= 0) )
      {
        *v182 = v29;
        v29 = 0;
        *v183 = v141;
      }
      goto LABEL_40;
    }
  }
  v29 = 0;
LABEL_40:
  v57 = v147;
  if ( v147 )
  {
    v58 = GetProcessHeap();
    HeapFree(v58, 0, v57);
  }
  v59 = lpBuffer;
  if ( lpBuffer )
  {
    v60 = 0x7FFFFFFF;
    v61 = lpBuffer;
    do
    {
      if ( !*v61 )
        break;
      ++v61;
      --v60;
    }
    while ( v60 );
    if ( v60 )
    {
      v62 = (2 * (0x7FFFFFFF - v60)) & -(__int64)(v60 != 0);
      if ( v62 )
      {
        do
        {
          *v59++ = 0;
          --v62;
        }
        while ( v62 );
        v59 = lpBuffer;
      }
    }
    if ( v59 )
    {
      v63 = GetProcessHeap();
      HeapFree(v63, 0, v59);
    }
    lpBuffer = 0;
  }
  if ( v29 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 0, v29);
  }
  if ( v143 )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v143);
  }
  if ( v56 )
  {
    v66 = GetProcessHeap();
    HeapFree(v66, 0, v56);
  }
  if ( v28 )
  {
    v67 = 0x7FFFFFFF;
    v68 = v28;
    do
    {
      if ( !*v68 )
        break;
      ++v68;
      --v67;
    }
    while ( v67 );
    if ( v67 )
    {
      v69 = (2 * (0x7FFFFFFF - v67)) & -(__int64)(v67 != 0);
      for ( i = v28; v69; --v69 )
      {
        *(_BYTE *)i = 0;
        i = (unsigned __int16 *)((char *)i + 1);
      }
    }
    v71 = GetProcessHeap();
    HeapFree(v71, 0, v28);
  }
  v72 = String;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v184);
  if ( Block != v170 )
    operator delete(Block);
  if ( v165 != v167 )
    operator delete(v165);
  v73 = lpMem;
  lpMem = 0;
  if ( v73 )
  {
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v73);
  }
  v75 = v129;
  v129 = 0;
  if ( v75 )
  {
    v76 = GetProcessHeap();
    HeapFree(v76, 0, v75);
  }
  v77 = v130;
  v130 = 0;
  if ( v77 )
  {
    v78 = GetProcessHeap();
    HeapFree(v78, 0, v77);
  }
  v79 = v131;
  v131 = 0;
  if ( v79 )
  {
    v80 = GetProcessHeap();
    HeapFree(v80, 0, v79);
  }
  v81 = v132;
  v132 = 0;
  if ( v81 )
  {
    v82 = GetProcessHeap();
    HeapFree(v82, 0, v81);
  }
  v83 = v133;
  v133 = 0;
  if ( v83 )
  {
    v84 = GetProcessHeap();
    HeapFree(v84, 0, v83);
  }
  v85 = v134;
  v134 = 0;
  if ( v85 )
  {
    v86 = GetProcessHeap();
    HeapFree(v86, 0, v85);
  }
  return v72;
}

```

## disassembly

```asm
0x18002f6bc  push    rbp
0x18002f6be  push    rbx
0x18002f6bf  push    rsi
0x18002f6c0  push    rdi
0x18002f6c1  push    r12
0x18002f6c3  push    r13
0x18002f6c5  push    r14
0x18002f6c7  push    r15
0x18002f6c9  lea     rbp, [rsp-3C8h]
0x18002f6d1  sub     rsp, 528h
0x18002f6d8  mov     rax, cs:__security_cookie
0x18002f6df  xor     rax, rsp
0x18002f6e2  mov     [rbp+400h+var_50], rax
0x18002f6e9  mov     [rbp+400h+var_2C0], r9
0x18002f6f0  mov     rsi, r8
0x18002f6f3  mov     [rbp+400h+var_2B8], r8
0x18002f6fa  mov     r10, rdx
0x18002f6fd  mov     [rbp+400h+var_3E8], rdx
0x18002f701  mov     [rbp+400h+var_2A0], rcx
0x18002f708  mov     rax, [rbp+400h+arg_20]
0x18002f70f  mov     [rbp+400h+var_2C8], rax
0x18002f716  mov     rax, [rbp+400h+arg_28]
0x18002f71d  mov     [rbp+400h+var_2D0], rax
0x18002f724  mov     rax, [rbp+400h+arg_48]
0x18002f72b  mov     [rbp+400h+var_2D8], rax
0x18002f732  mov     rax, [rbp+400h+arg_50]
0x18002f739  mov     [rbp+400h+var_3F0], rax
0x18002f73d  mov     rax, [rbp+400h+arg_78]
0x18002f744  mov     [rbp+400h+var_278], rax
0x18002f74b  mov     rax, [rbp+400h+arg_80]
0x18002f752  mov     [rbp+400h+var_2E8], rax
0x18002f759  mov     rax, [rbp+400h+arg_88]
0x18002f760  mov     [rbp+400h+var_2F0], rax
0x18002f767  mov     rax, [rbp+400h+arg_90]
0x18002f76e  mov     [rbp+400h+var_2E0], rax
0x18002f775  mov     rax, [rbp+400h+arg_98]
0x18002f77c  mov     [rbp+400h+var_298], rax
0x18002f783  mov     rax, [rbp+400h+arg_A0]
0x18002f78a  mov     [rbp+400h+var_290], rax
0x18002f791  mov     r13, [rbp+400h+arg_A8]
0x18002f798  mov     r12, [rbp+400h+arg_B0]
0x18002f79f  mov     r14, [rbp+400h+arg_B8]
0x18002f7a6  mov     [rbp+400h+var_470], r14
0x18002f7aa  mov     rax, [rbp+400h+arg_C0]
0x18002f7b1  mov     [rbp+400h+var_2A8], rax
0x18002f7b8  mov     rax, [rbp+400h+arg_C8]
0x18002f7bf  mov     [rbp+400h+var_2B0], rax
0x18002f7c6  xor     ecx, ecx
0x18002f7c8  mov     [rbp+400h+var_480], ecx
0x18002f7cb  mov     [rbp+400h+var_3D0], rcx
0x18002f7cf  mov     [rbp+400h+lpBuffer], rcx
0x18002f7d3  mov     edi, ecx
0x18002f7d5  mov     [rbp+400h+var_3E0], rcx
0x18002f7d9  mov     r15d, ecx
0x18002f7dc  mov     [rbp+400h+var_3C8], rcx
0x18002f7e0  mov     [rbp+400h+var_400], ecx
0x18002f7e3  mov     [rbp+400h+var_3F8], rcx
0x18002f7e7  mov     [rbp+400h+var_468], rcx
0x18002f7eb  mov     [rbp+400h+var_404], ecx
0x18002f7ee  mov     [rbp+400h+var_460], ecx
0x18002f7f1  mov     [rbp+400h+var_408], ecx
0x18002f7f4  mov     [rbp+400h+var_3FC], ecx
0x18002f7f7  mov     [rbp+400h+var_40C], ecx
0x18002f7fa  mov     [rbp+400h+var_420], rcx
0x18002f7fe  mov     [rbp+400h+var_428], rcx
0x18002f802  mov     [rbp+400h+var_430], rcx
0x18002f806  mov     [rbp+400h+var_438], rcx
0x18002f80a  mov     [rbp+400h+var_410], ecx
0x18002f80d  mov     [rbp+400h+var_414], ecx
0x18002f810  mov     [rbp+400h+var_440], rcx
0x18002f814  mov     [rbp+400h+var_448], rcx
0x18002f818  mov     [rbp+400h+lpMem], rcx
0x18002f81c  mov     [rbp+400h+var_418], ecx
0x18002f81f  lea     rax, [rbp+400h+var_328]
0x18002f826  mov     [rbp+400h+var_338], rax
0x18002f82d  lea     rax, [rbp+400h+var_328]
0x18002f834  mov     [rbp+400h+var_330], rax
0x18002f83b  mov     [rbp+400h+var_328], cx
0x18002f842  lea     rax, [rbp+400h+var_308]
0x18002f849  mov     [rbp+400h+Block], rax
0x18002f850  lea     rax, [rbp+400h+var_308]
0x18002f857  mov     [rbp+400h+var_310], rax
0x18002f85e  mov     [rbp+400h+var_308], cx
0x18002f865  lea     rax, aRetrieveprovis; "RetrieveProvisioningPayloadCallback"
0x18002f86c  mov     [rbp+400h+var_288], rax
0x18002f873  lea     rax, [rbp+400h+var_480]
0x18002f877  mov     [rbp+400h+var_280], rax
0x18002f87e  lea     r9, [rbp+400h+var_460]
0x18002f882  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x18002f889  xor     edx, edx
0x18002f88b  mov     rcx, r10
0x18002f88e  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002f895  nop     dword ptr [rax+rax+00h]
0x18002f89a  mov     ebx, eax
0x18002f89c  mov     [rbp+400h+var_480], eax
0x18002f89f  cmp     eax, 80070002h
0x18002f8a4  jz      loc_18002FA53
0x18002f8aa  cmp     eax, 8007065Dh
0x18002f8af  jz      loc_18002FA53
0x18002f8b5  test    eax, eax
0x18002f8b7  jns     loc_18002FA61
0x18002f8bd  lea     rcx, [rbp+400h+var_288]; this
0x18002f8c4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002f8c9  nop
0x18002f8ca  mov     rcx, [rbp+400h+Block]; Block
0x18002f8d1  lea     rax, [rbp+400h+var_308]
0x18002f8d8  cmp     rcx, rax
0x18002f8db  jz      short loc_18002F8E9
0x18002f8dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002f8e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f8e9  mov     rcx, [rbp+400h+var_338]; Block
0x18002f8f0  lea     rax, [rbp+400h+var_328]
0x18002f8f7  cmp     rcx, rax
0x18002f8fa  jz      short loc_18002F909
0x18002f8fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002f903  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f908  nop
0x18002f909  mov     rdi, [rbp+400h+lpMem]
0x18002f90d  xor     esi, esi
0x18002f90f  mov     [rbp+400h+lpMem], rsi
0x18002f913  test    rdi, rdi
0x18002f916  jz      short loc_18002F939
0x18002f918  call    cs:__imp_GetProcessHeap
0x18002f91f  nop     dword ptr [rax+rax+00h]
0x18002f924  mov     rcx, rax; hHeap
0x18002f927  mov     r8, rdi; lpMem
0x18002f92a  xor     edx, edx; dwFlags
0x18002f92c  call    cs:__imp_HeapFree
0x18002f933  nop     dword ptr [rax+rax+00h]
0x18002f938  nop
0x18002f939  mov     rdi, [rbp+400h+var_448]
0x18002f93d  mov     [rbp+400h+var_448], rsi
0x18002f941  test    rdi, rdi
0x18002f944  jz      short loc_18002F967
0x18002f946  call    cs:__imp_GetProcessHeap
0x18002f94d  nop     dword ptr [rax+rax+00h]
0x18002f952  mov     rcx, rax; hHeap
0x18002f955  mov     r8, rdi; lpMem
0x18002f958  xor     edx, edx; dwFlags
0x18002f95a  call    cs:__imp_HeapFree
0x18002f961  nop     dword ptr [rax+rax+00h]
0x18002f966  nop
0x18002f967  mov     rdi, [rbp+400h+var_440]
0x18002f96b  mov     [rbp+400h+var_440], rsi
0x18002f96f  test    rdi, rdi
0x18002f972  jz      short loc_18002F995
0x18002f974  call    cs:__imp_GetProcessHeap
0x18002f97b  nop     dword ptr [rax+rax+00h]
0x18002f980  mov     rcx, rax; hHeap
0x18002f983  mov     r8, rdi; lpMem
0x18002f986  xor     edx, edx; dwFlags
0x18002f988  call    cs:__imp_HeapFree
0x18002f98f  nop     dword ptr [rax+rax+00h]
0x18002f994  nop
0x18002f995  mov     rdi, [rbp+400h+var_438]
0x18002f999  mov     [rbp+400h+var_438], rsi
0x18002f99d  test    rdi, rdi
0x18002f9a0  jz      short loc_18002F9C3
0x18002f9a2  call    cs:__imp_GetProcessHeap
0x18002f9a9  nop     dword ptr [rax+rax+00h]
0x18002f9ae  mov     rcx, rax; hHeap
0x18002f9b1  mov     r8, rdi; lpMem
0x18002f9b4  xor     edx, edx; dwFlags
0x18002f9b6  call    cs:__imp_HeapFree
0x18002f9bd  nop     dword ptr [rax+rax+00h]
0x18002f9c2  nop
0x18002f9c3  mov     rdi, [rbp+400h+var_430]
0x18002f9c7  mov     [rbp+400h+var_430], rsi
0x18002f9cb  test    rdi, rdi
0x18002f9ce  jz      short loc_18002F9F1
0x18002f9d0  call    cs:__imp_GetProcessHeap
0x18002f9d7  nop     dword ptr [rax+rax+00h]
0x18002f9dc  mov     rcx, rax; hHeap
0x18002f9df  mov     r8, rdi; lpMem
0x18002f9e2  xor     edx, edx; dwFlags
0x18002f9e4  call    cs:__imp_HeapFree
0x18002f9eb  nop     dword ptr [rax+rax+00h]
0x18002f9f0  nop
0x18002f9f1  mov     rdi, [rbp+400h+var_428]
0x18002f9f5  mov     [rbp+400h+var_428], rsi
0x18002f9f9  test    rdi, rdi
0x18002f9fc  jz      short loc_18002FA1F
0x18002f9fe  call    cs:__imp_GetProcessHeap
0x18002fa05  nop     dword ptr [rax+rax+00h]
0x18002fa0a  mov     rcx, rax; hHeap
0x18002fa0d  mov     r8, rdi; lpMem
0x18002fa10  xor     edx, edx; dwFlags
0x18002fa12  call    cs:__imp_HeapFree
0x18002fa19  nop     dword ptr [rax+rax+00h]
0x18002fa1e  nop
0x18002fa1f  mov     rdi, [rbp+400h+var_420]
0x18002fa23  mov     [rbp+400h+var_420], rsi
0x18002fa27  test    rdi, rdi
0x18002fa2a  jz      short loc_18002FA4C
0x18002fa2c  call    cs:__imp_GetProcessHeap
0x18002fa33  nop     dword ptr [rax+rax+00h]
0x18002fa38  mov     rcx, rax; hHeap
0x18002fa3b  mov     r8, rdi; lpMem
0x18002fa3e  xor     edx, edx; dwFlags
0x18002fa40  call    cs:__imp_HeapFree
0x18002fa47  nop     dword ptr [rax+rax+00h]
0x18002fa4c  mov     eax, ebx
0x18002fa4e  jmp     loc_18002FEE1
0x18002fa53  mov     [rbp+400h+var_460], 0
0x18002fa5a  mov     [rbp+400h+var_480], 0
0x18002fa61  mov     dword ptr [rsp+560h+lpWideCharStr], 0; int
0x18002fa69  lea     r9, [rbp+400h+var_468]; unsigned __int16 **
0x18002fa6d  lea     r8, [rbp+400h+var_3F8]; unsigned __int16 **
0x18002fa71  lea     rdx, [rbp+400h+var_404]; unsigned int *
0x18002fa75  mov     rcx, rsi; unsigned __int16 *
0x18002fa78  call    ?ParseServiceURL@@YAJPEBGPEAKPEAPEAG2H@Z; ParseServiceURL(ushort const *,ulong *,ushort * *,ushort * *,int)
0x18002fa7d  mov     [rbp+400h+var_480], eax
0x18002fa80  mov     ebx, 1
0x18002fa85  test    eax, eax
0x18002fa87  js      loc_18002FBD4
0x18002fa8d  mov     esi, [rbp+400h+arg_70]
0x18002fa93  test    sil, 80h
0x18002fa97  jnz     loc_1800303F5
0x18002fa9d  cmp     qword ptr [r13+0], 0
0x18002faa2  jnz     loc_18002FB5F
0x18002faa8  mov     r14d, esi
0x18002faab  and     r14d, 20h
0x18002faaf  mov     eax, r14d
0x18002fab2  neg     eax
0x18002fab4  sbb     rsi, rsi
0x18002fab7  and     rsi, 0FFFFFFFFFFFFFFF7h
0x18002fabb  add     rsi, 17h
0x18002fabf  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18002fac6  jz      short loc_18002FAEA
0x18002fac8  lea     rax, [rbp+400h+var_270]
0x18002facf  mov     [rsp+560h+lpWideCharStr], rax
0x18002fad4  mov     r9d, ebx
0x18002fad7  lea     rdx, UsingDefaultHashAlgorithmEvent
0x18002fade  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002fae5  call    McGenEventWrite_EventWriteTransfer
0x18002faea  mov     [rbp+400h+var_480], 0
0x18002faf1  lea     rbx, [rsi+rsi]
0x18002faf5  call    cs:__imp_GetProcessHeap
0x18002fafc  nop     dword ptr [rax+rax+00h]
0x18002fb01  mov     rcx, rax; hHeap
0x18002fb04  mov     r8, rbx; dwBytes
0x18002fb07  mov     edx, 8; dwFlags
0x18002fb0c  call    cs:__imp_HeapAlloc
0x18002fb13  nop     dword ptr [rax+rax+00h]
0x18002fb18  mov     [r13+0], rax
0x18002fb1c  test    rax, rax
0x18002fb1f  jz      loc_18002FBCD
0x18002fb25  lea     rcx, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x18002fb2c  lea     r8, a13143229; "1.3.14.3.2.29"
0x18002fb33  test    r14d, r14d
0x18002fb36  cmovz   r8, rcx; unsigned __int16 *
0x18002fb3a  mov     rdx, rsi; unsigned __int64
0x18002fb3d  mov     rcx, rax; unsigned __int16 *
0x18002fb40  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fb45  mov     [rbp+400h+var_480], eax
0x18002fb48  test    eax, eax
0x18002fb4a  js      loc_18002FBD4
0x18002fb50  mov     esi, [rbp+400h+arg_70]
0x18002fb56  mov     r14, [rbp+400h+var_470]
0x18002fb5a  mov     ebx, 1
0x18002fb5f  cmp     qword ptr [r12], 0
0x18002fb64  jnz     loc_18002FF24
0x18002fb6a  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18002fb71  jz      short loc_18002FB95
0x18002fb73  lea     rax, [rbp+400h+var_270]
0x18002fb7a  mov     [rsp+560h+lpWideCharStr], rax
0x18002fb7f  mov     r9d, ebx
0x18002fb82  lea     rdx, UsingDefaultPrivateKeyAlgorithmEvent
0x18002fb89  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002fb90  call    McGenEventWrite_EventWriteTransfer
0x18002fb95  mov     [rbp+400h+var_480], 0
0x18002fb9c  call    cs:__imp_GetProcessHeap
0x18002fba3  nop     dword ptr [rax+rax+00h]
0x18002fba8  mov     rcx, rax; hHeap
0x18002fbab  mov     edx, 8; dwFlags
0x18002fbb0  lea     r8d, [rdx+22h]; dwBytes
0x18002fbb4  call    cs:__imp_HeapAlloc
0x18002fbbb  nop     dword ptr [rax+rax+00h]
0x18002fbc0  mov     [r12], rax
0x18002fbc4  test    rax, rax
0x18002fbc7  jnz     loc_18002FF05
0x18002fbcd  mov     [rbp+400h+var_480], 8007000Eh
0x18002fbd4  mov     r14, [rbp+400h+var_468]
0x18002fbd8  xor     r12d, r12d
0x18002fbdb  mov     rbx, [rbp+400h+var_3D0]
0x18002fbdf  test    rbx, rbx
0x18002fbe2  jz      short loc_18002FC04
0x18002fbe4  call    cs:__imp_GetProcessHeap
0x18002fbeb  nop     dword ptr [rax+rax+00h]
0x18002fbf0  mov     rcx, rax; hHeap
0x18002fbf3  mov     r8, rbx; lpMem
0x18002fbf6  xor     edx, edx; dwFlags
0x18002fbf8  call    cs:__imp_HeapFree
0x18002fbff  nop     dword ptr [rax+rax+00h]
0x18002fc04  mov     esi, 7FFFFFFFh
0x18002fc09  mov     rbx, [rbp+400h+lpBuffer]
0x18002fc0d  test    rbx, rbx
0x18002fc10  jz      short loc_18002FC79
0x18002fc12  mov     ecx, esi
0x18002fc14  mov     rax, rbx
  ... truncated ...
```
