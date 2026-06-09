# GdiPrinterThunk

- ea: `0x18003bd20`
- end: `0x18003e751`
- name: `GdiPrinterThunk`
- size: `10801`
- prototype: `__int64 __fastcall(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting`

## callees

- `0x18003bbac`
- `0x18003bc78`
- `0x18003bce0`
- `0x18003bd20`
- `0x18003e7d4`
- `0x18003e8c0`
- `0x18003e8e0`
- `0x18003e930`
- `0x18003ea88`
- `0x18003fabc`
- `0x18003fb74`
- `0x1800403b4`
- `0x180041058`
- `0x1800410a4`
- `0x18005f32c`
- `0x180060820`
- `0x18007004c`
- `0x180080604`
- `0x18009b7fc`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c97f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c97f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e636`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c26b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c5a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c26b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c5a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c24b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c562`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c24b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c562`
- `GDI32!fpClosePrinter` at `0x18003c2b5`
- `GDI32!fpClosePrinter` at `0x18003ce31`
- `ntdll!RtlFreeHeap` at `0x18003ccc7`
- `ntdll!RtlFreeHeap` at `0x18003cdf9`
- `ntdll!RtlFreeHeap` at `0x18003ccc7`
- `ntdll!RtlFreeHeap` at `0x18003cdf9`
- `ntdll!RtlAllocateHeap` at `0x18003cc1c`
- `ntdll!RtlAllocateHeap` at `0x18003dcd8`
- `ntdll!RtlAllocateHeap` at `0x18003cc1c`
- `ntdll!RtlAllocateHeap` at `0x18003dcd8`
- `ntdll!RtlDecodePointer` at `0x18003c155`
- `ntdll!RtlDecodePointer` at `0x18003c2bf`
- `ntdll!RtlDecodePointer` at `0x18003c8b5`
- `ntdll!RtlDecodePointer` at `0x18003ce3b`
- `ntdll!RtlDecodePointer` at `0x18003dfc8`
- `ntdll!RtlDecodePointer` at `0x18003e177`
- `ntdll!RtlDecodePointer` at `0x18003e5d7`
- `ntdll!RtlDecodePointer` at `0x18003e71d`
- `ntdll!RtlDecodePointer` at `0x18003c155`
- `ntdll!RtlDecodePointer` at `0x18003c2bf`
- `ntdll!RtlDecodePointer` at `0x18003c8b5`
- `ntdll!RtlDecodePointer` at `0x18003ce3b`
- `ntdll!RtlDecodePointer` at `0x18003dfc8`
- `ntdll!RtlDecodePointer` at `0x18003e177`
- `ntdll!RtlDecodePointer` at `0x18003e5d7`
- `ntdll!RtlDecodePointer` at `0x18003e71d`
- `win32u!NtGdiSetPUMPDOBJ` at `0x18003bd8c`
- `win32u!NtGdiSetPUMPDOBJ` at `0x18003be43`
- `win32u!NtGdiSetPUMPDOBJ` at `0x18003bd8c`
- `win32u!NtGdiSetPUMPDOBJ` at `0x18003be43`
- `win32u!NtGdiUMPDEngFreeUserMem` at `0x18003e4b4`
- `win32u!NtGdiUMPDEngFreeUserMem` at `0x18003e4b4`
- `win32u!NtGdiBRUSHOBJ_DeleteRbrush` at `0x18003c036`
- `win32u!NtGdiBRUSHOBJ_DeleteRbrush` at `0x18003d408`
- `win32u!NtGdiBRUSHOBJ_DeleteRbrush` at `0x18003c036`
- `win32u!NtGdiBRUSHOBJ_DeleteRbrush` at `0x18003d408`

## pseudocode

```c
__int64 __fastcall GdiPrinterThunk(unsigned int *a1, unsigned int a2, _DWORD *a3, unsigned int a4)
{
  unsigned int v5; // r12d
  int v6; // ecx
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  void *v16; // rbx
  char *v18; // r13
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  _QWORD *v25; // rdx
  int v26; // eax
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  _QWORD *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  _BYTE *Heap; // r12
  __int64 v35; // rcx
  _QWORD *v36; // rdx
  _QWORD *v37; // r13
  bool v38; // zf
  _QWORD *v39; // rbx
  _QWORD *v40; // rbx
  volatile signed __int32 *v41; // rbx
  void (__fastcall *v42)(void *); // rax
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  _QWORD *v45; // rsi
  __int64 v46; // rcx
  _QWORD *v47; // rdx
  unsigned int v48; // ebx
  unsigned int v49; // ebx
  unsigned int v50; // ebx
  unsigned int v51; // ebx
  _QWORD *v52; // r12
  _QWORD *v53; // r12
  __int64 v54; // rcx
  _QWORD *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rcx
  _QWORD *v58; // rdx
  int v59; // eax
  unsigned int v60; // ebx
  unsigned int v61; // ebx
  _QWORD *v62; // r12
  __int64 v63; // rcx
  _QWORD *v64; // rdx
  unsigned int v65; // ebx
  unsigned int v66; // ebx
  unsigned int v67; // ebx
  _QWORD *v68; // r12
  __int64 v69; // r13
  __int64 v70; // rcx
  BOOL v71; // eax
  int v72; // edx
  PVOID v73; // rax
  unsigned int v74; // ecx
  __int64 (__fastcall *v75)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD); // r10
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  _QWORD *v82; // rcx
  unsigned __int16 ***v83; // r12
  int v84; // eax
  _QWORD *v85; // r13
  void *v86; // rcx
  unsigned int v87; // r8d
  __int64 v88; // r9
  struct _OffsetPointer *v89; // r13
  unsigned int v90; // r9d
  unsigned int v91; // r8d
  struct _OffsetPointer *v92; // rax
  _QWORD *v93; // r13
  unsigned int v94; // r9d
  unsigned __int16 *v95; // rdx
  unsigned int v96; // r10d
  char *v97; // rcx
  __int64 v98; // r9
  unsigned int *v99; // r12
  struct _HPRINTERLIST *PrinterHandle; // rax
  __int64 v101; // r13
  __int64 v102; // rax
  _DWORD *v103; // rax
  void *v104; // rcx
  unsigned int v105; // r8d
  struct _HPRINTERLIST *v106; // rbx
  void (__fastcall *v107)(_QWORD); // rax
  unsigned __int64 v108; // rcx
  UmpdPtr *v109; // rcx
  __int64 v110; // rax
  _QWORD *v111; // rcx
  unsigned __int64 v112; // r8
  unsigned int v113; // ecx
  unsigned int v114; // r8d
  __int64 v115; // rax
  unsigned int v116; // ecx
  __int64 v117; // rax
  unsigned int v118; // r8d
  _QWORD *v119; // rbx
  void (__fastcall *v120)(__int64, __int64); // rax
  __int64 v121; // rdx
  __int64 v122; // rcx
  _QWORD *v123; // rbx
  _QWORD *v124; // rbx
  __int64 v125; // rax
  __int64 v126; // r13
  unsigned int v127; // r8d
  unsigned int v128; // edx
  __int64 v129; // rcx
  __int64 v130; // rcx
  _QWORD *v131; // rdx
  int v132; // eax
  __int64 v133; // rcx
  _QWORD *v134; // rdx
  __int64 v135; // rcx
  unsigned int v136; // ebx
  unsigned int v137; // ebx
  __int64 v138; // rcx
  _QWORD *v139; // rdx
  _QWORD *v140; // rbx
  _QWORD *v141; // rbx
  const void *v142; // rdx
  __int64 v143; // rcx
  _QWORD *v144; // rdx
  __int64 v145; // rcx
  _QWORD *v146; // rdx
  unsigned int v147; // ebx
  void (__fastcall *v148)(_QWORD); // rax
  __int64 v149; // rcx
  _QWORD *v150; // rdx
  __int64 v151; // rcx
  _QWORD *v152; // rdx
  __int64 v153; // rcx
  _QWORD *v154; // rdx
  _QWORD *v155; // rdx
  __int64 v156; // rcx
  unsigned int v157; // ebx
  unsigned int v158; // ebx
  unsigned int v159; // ebx
  unsigned int v160; // ebx
  unsigned int v161; // ebx
  unsigned int v162; // ebx
  __int64 v163; // rcx
  _QWORD *v164; // rdx
  _QWORD *v165; // rbx
  _QWORD *v166; // rbx
  _QWORD *v167; // rbx
  __int64 v168; // rcx
  _QWORD *v169; // rdx
  __int64 (__fastcall *v170)(_QWORD, _QWORD); // rax
  __int64 v171; // rcx
  _QWORD *v172; // rdx
  __int64 (__fastcall *v173)(_QWORD, _QWORD); // r8
  _QWORD *v174; // rbx
  __int64 v175; // rcx
  _QWORD *v176; // rdx
  unsigned int v177; // ebx
  unsigned int v178; // ebx
  unsigned int v179; // ebx
  unsigned int v180; // ebx
  unsigned int v181; // ebx
  PVOID v182; // rax
  __int64 v183; // rcx
  _QWORD *v184; // rdx
  __int64 v185; // rcx
  _QWORD *v186; // rdx
  __int64 v187; // rcx
  _QWORD *v188; // rdx
  __int64 v189; // rcx
  _QWORD *v190; // rdx
  __int64 v191; // rcx
  _QWORD *v192; // rdx
  unsigned int v193; // ebx
  unsigned int v194; // ebx
  unsigned int v195; // ebx
  struct _HPRINTERLIST *v196; // rbx
  PVOID v197; // rcx
  __int64 (__fastcall *v198)(_QWORD); // rax
  int v199; // eax
  struct _HPRINTERLIST *v200; // r14
  PVOID v201; // rax
  unsigned int v202; // r9d
  struct _OffsetPointer **v203; // r13
  void *v204; // rcx
  void *v205; // rcx
  __int64 v206; // r13
  int v207; // eax
  void *v208; // rcx
  unsigned int v209; // r9d
  unsigned int v210; // r9d
  void *v211; // rcx
  __int64 v212; // r13
  unsigned int v213; // ebx
  unsigned int v214; // ebx
  unsigned int v215; // ebx
  unsigned int v216; // ebx
  unsigned int v217; // ebx
  __int64 v218; // rbx
  __int64 v219; // rdx
  unsigned int *v220; // rbx
  void *v221; // rcx
  struct _devicemodeW **v222; // r14
  PVOID v223; // rax
  int v224; // eax
  struct _HPRINTERLIST *v225; // r14
  __int64 (__fastcall *v226)(_QWORD, unsigned int *); // rax
  int v227; // eax
  __int64 v228; // [rsp+78h] [rbp-90h] BYREF
  void *v229; // [rsp+80h] [rbp-88h] BYREF
  _DWORD *v230; // [rsp+88h] [rbp-80h] BYREF
  PVOID v231; // [rsp+90h] [rbp-78h] BYREF
  __int128 v232; // [rsp+98h] [rbp-70h] BYREF
  __int128 v233; // [rsp+A8h] [rbp-60h] BYREF
  struct _HPRINTERLIST *v234; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v235; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v236; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v237; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v238; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v239; // [rsp+100h] [rbp-8h] BYREF
  __int128 v240; // [rsp+108h] [rbp+0h] BYREF
  __int128 v241; // [rsp+118h] [rbp+10h] BYREF
  __int128 v242; // [rsp+128h] [rbp+20h] BYREF
  int v243; // [rsp+188h] [rbp+80h]
  int v244; // [rsp+190h] [rbp+88h] BYREF

  v239 = 0;
  v5 = 0x7FFFFFFF;
  v243 = 0;
  v6 = 0;
  v244 = 0;
  v8 = a1[1];
  v9 = 1;
  if ( a2 < 0x7FFFFFFF )
    v5 = a2;
  if ( v8 <= 0x69 )
  {
    v243 = NtGdiSetPUMPDOBJ(*((_QWORD *)a1 + 2), 1, &v239, &v244);
    if ( !v243 )
      return 0xFFFFFFFFLL;
    v6 = v244;
  }
  if ( v8 <= 0x2F )
  {
    if ( v8 == 47 )
    {
      if ( a1[12] == 8 )
      {
        v155 = (_QWORD *)*((_QWORD *)a1 + 4);
      }
      else
      {
        v156 = *((_QWORD *)a1 + 3);
        v155 = *(_QWORD **)(v156 + 16);
        *(_QWORD *)(v156 + 16) = v155[1];
      }
      FindDriverForCookie(&v228, *v155);
      if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
        UmpdPtr::assert((UmpdPtr *)&v228);
        v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD))(v228 + 464))(
                 *((_QWORD *)a1 + 3),
                 *((_QWORD *)a1 + 5),
                 a1[12],
                 a1[13],
                 *((_QWORD *)a1 + 7),
                 a1[16],
                 *((_QWORD *)a1 + 9));
        goto LABEL_309;
      }
      goto LABEL_308;
    }
    if ( v8 <= 0x14 )
    {
      if ( v8 == 20 )
      {
        v46 = *((_QWORD *)a1 + 3);
        v47 = *(_QWORD **)(v46 + 16);
        *(_QWORD *)(v46 + 16) = v47[1];
        FindDriverForCookie(&v230, *v47);
        v16 = v230;
        if ( v230 )
        {
          if ( *v230 != -19088744 )
            goto LABEL_145;
          v26 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))v230
                 + 31))(
                  *((_QWORD *)a1 + 3),
                  *((_QWORD *)a1 + 4),
                  *((_QWORD *)a1 + 5),
                  *((_QWORD *)a1 + 6),
                  *((_QWORD *)a1 + 7),
                  *((_QWORD *)a1 + 8),
                  *((_QWORD *)a1 + 9),
                  *((_QWORD *)a1 + 10),
                  *((_QWORD *)a1 + 11),
                  *((_QWORD *)a1 + 12),
                  a1[26]);
          goto LABEL_37;
        }
        goto LABEL_35;
      }
      if ( v8 > 0xC )
      {
        v11 = v8 - 13;
        if ( !v11 )
        {
          v53 = (_QWORD *)*((_QWORD *)a1 + 3);
          FindDriverForCookie(&v230, *v53);
          v16 = v230;
          if ( v230 )
          {
            if ( *v230 != -19088744 )
              goto LABEL_145;
            v26 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))v230 + 24))(
                    v53[1],
                    a1[8],
                    a1[9],
                    *((_QWORD *)a1 + 5));
            goto LABEL_37;
          }
          goto LABEL_35;
        }
        v12 = v11 - 1;
        if ( !v12 )
        {
          v57 = *((_QWORD *)a1 + 3);
          v58 = *(_QWORD **)(v57 + 16);
          *(_QWORD *)(v57 + 16) = v58[1];
          FindDriverForCookie(&v230, *v58);
          v16 = v230;
          if ( !v230 )
            goto LABEL_15;
          if ( *v230 != -19088744 )
            goto LABEL_145;
          v59 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))v230
                 + 25))(
                  *((_QWORD *)a1 + 3),
                  *((_QWORD *)a1 + 4),
                  *((_QWORD *)a1 + 5),
                  *((_QWORD *)a1 + 6),
                  *((_QWORD *)a1 + 7),
                  *((_QWORD *)a1 + 8),
                  *((_QWORD *)a1 + 9),
                  a1[22]);
LABEL_146:
          *a3 = v59;
          if ( !v244 )
            goto LABEL_16;
          v32 = *((_QWORD *)a1 + 7);
LABEL_48:
          if ( !v32 )
            goto LABEL_16;
          v33 = 0;
LABEL_50:
          NtGdiBRUSHOBJ_DeleteRbrush(v32, v33);
          goto LABEL_16;
        }
        v13 = v12 - 1;
        if ( !v13 )
        {
          v14 = *((_QWORD *)a1 + 3);
          v15 = *(_QWORD **)(v14 + 16);
          *(_QWORD *)(v14 + 16) = v15[1];
          FindDriverForCookie(&v230, *v15);
          v16 = v230;
          if ( !v230 )
          {
LABEL_15:
            v9 = -1;
            *a3 = 0;
            goto LABEL_16;
          }
          if ( *v230 != -19088744 )
            goto LABEL_145;
          v59 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int))v230 + 26))(
                  *((_QWORD *)a1 + 3),
                  *((_QWORD *)a1 + 4),
                  *((_QWORD *)a1 + 5),
                  *((_QWORD *)a1 + 7),
                  *((_QWORD *)a1 + 8),
                  a1[22],
                  a1[23]);
          goto LABEL_146;
        }
        v27 = v13 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( !v29 )
            {
              v30 = *((_QWORD *)a1 + 3);
              if ( !*(_WORD *)(v30 + 76) && !*(_QWORD *)(v30 + 16) )
                v30 = *((_QWORD *)a1 + 4);
              if ( v30 )
              {
                v31 = *(_QWORD **)(v30 + 16);
                *(_QWORD *)(v30 + 16) = v31[1];
                if ( v31 )
                {
                  FindDriverForCookie(&v230, *v31);
                  v16 = v230;
                  if ( !v230 )
                    goto LABEL_15;
                  if ( *v230 != -19088744 )
                    goto LABEL_145;
                  *a3 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))v230
                         + 29))(
                          *((_QWORD *)a1 + 3),
                          *((_QWORD *)a1 + 4),
                          *((_QWORD *)a1 + 5),
                          *((_QWORD *)a1 + 6),
                          *((_QWORD *)a1 + 7),
                          *((_QWORD *)a1 + 8),
                          *((_QWORD *)a1 + 9),
                          *((_QWORD *)a1 + 10),
                          *((_QWORD *)a1 + 11),
                          *((_QWORD *)a1 + 12),
                          a1[26]);
                  if ( !v244 )
                    goto LABEL_16;
                  v32 = *((_QWORD *)a1 + 11);
                  goto LABEL_48;
                }
              }
LABEL_142:
              *a3 = 0;
              goto LABEL_17;
            }
            if ( v29 == 1 )
            {
              v54 = *((_QWORD *)a1 + 3);
              if ( !*(_WORD *)(v54 + 76) && !*(_QWORD *)(v54 + 16) )
                v54 = *((_QWORD *)a1 + 4);
              if ( !v54 )
                goto LABEL_142;
              v55 = *(_QWORD **)(v54 + 16);
              *(_QWORD *)(v54 + 16) = v55[1];
              if ( !v55 )
                goto LABEL_142;
              FindDriverForCookie(&v230, *v55);
              v16 = v230;
              if ( v230 )
              {
                if ( *v230 != -19088744 )
                  goto LABEL_145;
                v26 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v230 + 30))(
                        *((_QWORD *)a1 + 3),
                        *((_QWORD *)a1 + 4),
                        *((_QWORD *)a1 + 5),
                        *((_QWORD *)a1 + 6),
                        *((_QWORD *)a1 + 7),
                        *((_QWORD *)a1 + 8));
                goto LABEL_37;
              }
              goto LABEL_35;
            }
LABEL_485:
            v9 = -1;
            goto LABEL_17;
          }
          v133 = *((_QWORD *)a1 + 3);
          v134 = *(_QWORD **)(v133 + 16);
          *(_QWORD *)(v133 + 16) = v134[1];
          FindDriverForCookie(&v228, *v134);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            *a3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(v228 + 224))(
                    *((_QWORD *)a1 + 3),
                    *((_QWORD *)a1 + 5),
                    *((_QWORD *)a1 + 7),
                    *((_QWORD *)a1 + 8),
                    a1[22]);
            if ( v244 )
            {
              v135 = *((_QWORD *)a1 + 7);
              goto LABEL_315;
            }
LABEL_256:
            v109 = (UmpdPtr *)&v228;
LABEL_257:
            UmpdPtr::reset(v109, 0);
            goto LABEL_17;
          }
          goto LABEL_317;
        }
        v63 = *((_QWORD *)a1 + 3);
        v64 = *(_QWORD **)(v63 + 16);
        *(_QWORD *)(v63 + 16) = v64[1];
        FindDriverForCookie(&v230, *v64);
        v16 = v230;
        if ( !v230 )
          goto LABEL_15;
        if ( *v230 != -19088744 )
          goto LABEL_145;
        *a3 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int))v230
               + 27))(
                *((_QWORD *)a1 + 3),
                *((_QWORD *)a1 + 4),
                *((_QWORD *)a1 + 5),
                *((_QWORD *)a1 + 6),
                *((_QWORD *)a1 + 7),
                *((_QWORD *)a1 + 9),
                *((_QWORD *)a1 + 10),
                *((_QWORD *)a1 + 8),
                a1[22],
                a1[23]);
        if ( !v244 )
          goto LABEL_16;
        v32 = *((_QWORD *)a1 + 7);
LABEL_129:
        if ( !v32 && !*((_QWORD *)a1 + 10) )
          goto LABEL_16;
        v33 = *((_QWORD *)a1 + 10);
        goto LABEL_50;
      }
      if ( v8 != 12 )
      {
        if ( !v8 )
        {
          FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
          v16 = v229;
          if ( v229 )
          {
            if ( *(_DWORD *)v229 != -19088744 )
              goto LABEL_145;
            v99 = a1 + 28;
            v230 = (_DWORD *)*((_QWORD *)v229 + 11);
            if ( a1[30] )
            {
              PrinterHandle = FindPrinterHandle((struct UmpdPtr *)&v229, a1[31], *v99);
              if ( PrinterHandle )
                v99 = (unsigned int *)((char *)PrinterHandle + 16);
            }
            v101 = *(_QWORD *)v99;
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
            if ( Heap )
            {
              *(_OWORD *)Heap = 0;
              *((_QWORD *)Heap + 2) = 0;
              if ( *(_DWORD *)v16 != -19088744 )
                goto LABEL_145;
              *(_QWORD *)Heap = *((_QWORD *)v16 + 9);
              v102 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, unsigned int, _QWORD, _QWORD, _QWORD, __int64))v230)(
                       *((_QWORD *)a1 + 4),
                       *((_QWORD *)a1 + 5),
                       a1[12],
                       *((_QWORD *)a1 + 7),
                       a1[16],
                       *((_QWORD *)a1 + 9),
                       a1[20],
                       *((_QWORD *)a1 + 11),
                       *((_QWORD *)a1 + 12),
                       *((_QWORD *)a1 + 13),
                       v101);
              *((_QWORD *)Heap + 1) = v102;
              if ( v102 )
              {
                v126 = *((_QWORD *)a1 + 9);
                if ( v126 )
                {
                  if ( *(_DWORD *)(v126 + 236) == 18 )
                  {
                    v127 = *(_DWORD *)(v126 + 272);
                    if ( v127 <= 0x100 && *(_DWORD *)(v126 + 276) <= 0x100u )
                    {
                      a1[32] = v127;
                      v128 = *(_DWORD *)(v126 + 276);
                      a1[33] = v128;
                      v129 = *(_QWORD *)(v126 + 280);
                      a1[40] = v129 != 0;
                      a1[41] = *(_QWORD *)(v126 + 288) != 0;
                      a1[42] = *(_QWORD *)(v126 + 296) != 0;
                      if ( v129 )
                        memcpy_0(*((void **)a1 + 17), *(const void **)(v126 + 280), v128 * v127);
                      if ( a1[41] )
                        memcpy_0(*((void **)a1 + 18), *(const void **)(v126 + 288), a1[32] * a1[33]);
                      if ( a1[42] )
                        memcpy_0(*((void **)a1 + 19), *(const void **)(v126 + 296), a1[32] * a1[33]);
                    }
                  }
                }
              }
              else
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
                Heap = 0;
              }
            }
            if ( *(_DWORD *)v16 != -19088744 )
LABEL_145:
              __fastfail(7u);
            if ( *((_QWORD *)v16 + 53) )
              Heap[16] = 1;
          }
          else
          {
            Heap = 0;
            v9 = -1;
          }
          *(_QWORD *)a3 = Heap;
LABEL_16:
          if ( !v16 )
            goto LABEL_17;
          if ( *(_DWORD *)v16 == -19088744 )
          {
            _InterlockedDecrement((volatile signed __int32 *)v16 + 11);
            goto LABEL_17;
          }
          goto LABEL_145;
        }
        v43 = v8 - 1;
        if ( !v43 )
        {
          v119 = (_QWORD *)*((_QWORD *)a1 + 3);
          FindDriverForCookie(&v228, *v119);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v120 = *(void (__fastcall **)(__int64, __int64))(v228 + 96);
            goto LABEL_285;
          }
LABEL_255:
          v9 = -1;
          goto LABEL_256;
        }
        v44 = v43 - 1;
        if ( !v44 )
        {
          v45 = (_QWORD *)*((_QWORD *)a1 + 3);
          FindDriverForCookie(&v230, *v45);
          v16 = v230;
          if ( v230 )
          {
            if ( *v230 != -19088744 )
              goto LABEL_145;
            (*((void (__fastcall **)(_QWORD))v230 + 13))(v45[1]);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v45);
            goto LABEL_16;
          }
LABEL_84:
          v9 = -1;
          goto LABEL_16;
        }
        v65 = v44 - 1;
        if ( v65 )
        {
          v66 = v65 - 1;
          if ( !v66 )
          {
            v123 = (_QWORD *)*((_QWORD *)a1 + 3);
            FindDriverForCookie(&v228, *v123);
            if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
            {
              UmpdPtr::assert((UmpdPtr *)&v228);
              (*(void (__fastcall **)(_QWORD))(v228 + 120))(v123[1]);
              goto LABEL_256;
            }
            goto LABEL_255;
          }
          v67 = v66 - 3;
          if ( !v67 )
          {
            v68 = (_QWORD *)*((_QWORD *)a1 + 4);
            v69 = *((_QWORD *)a1 + 3);
            FindDriverForCookie(&v230, *v68);
            v16 = v230;
            if ( v230 )
            {
              if ( *v230 != -19088744 )
                goto LABEL_145;
              v26 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))v230 + 18))(*(_QWORD *)(v69 + 8), v68[1]);
              goto LABEL_37;
            }
            v9 = -1;
            goto LABEL_36;
          }
          if ( v67 != 4 )
            goto LABEL_485;
          v119 = (_QWORD *)*((_QWORD *)a1 + 3);
          FindDriverForCookie(&v228, *v119);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v120 = *(void (__fastcall **)(__int64, __int64))(v228 + 176);
LABEL_285:
            v121 = *((_QWORD *)a1 + 4);
            v122 = v119[1];
LABEL_286:
            v120(v122, v121);
            goto LABEL_256;
          }
          goto LABEL_255;
        }
        v124 = (_QWORD *)*((_QWORD *)a1 + 3);
        FindDriverForCookie(&v228, *v124);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          v125 = (*(__int64 (__fastcall **)(_QWORD))(v228 + 112))(v124[1]);
LABEL_292:
          *(_QWORD *)a3 = v125;
          goto LABEL_256;
        }
LABEL_291:
        v9 = -1;
        v125 = 0;
        goto LABEL_292;
      }
      v130 = *((_QWORD *)a1 + 3);
      v131 = *(_QWORD **)(v130 + 16);
      *(_QWORD *)(v130 + 16) = v131[1];
      FindDriverForCookie(&v228, *v131);
      if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
        UmpdPtr::assert((UmpdPtr *)&v228);
        v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(v228 + 184))(
                 *((_QWORD *)a1 + 6),
                 *((_QWORD *)a1 + 3),
                 *((_QWORD *)a1 + 4),
                 *((_QWORD *)a1 + 5),
                 *((_QWORD *)a1 + 7),
                 a1[16]);
LABEL_309:
        *a3 = v132;
        goto LABEL_256;
      }
      goto LABEL_308;
    }
    if ( v8 > 0x20 )
    {
      v48 = v8 - 33;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( v49 )
        {
          v50 = v49 - 1;
          if ( v50 )
          {
            v51 = v50 - 2;
            if ( !v51 )
            {
              v52 = (_QWORD *)*((_QWORD *)a1 + 3);
              FindDriverForCookie(&v230, *v52);
              v16 = v230;
              if ( v230 )
              {
                if ( *v230 != -19088744 )
                  goto LABEL_145;
                v26 = (*((__int64 (__fastcall **)(_QWORD, _QWORD))v230 + 48))(v52[1], *((_QWORD *)a1 + 4));
                goto LABEL_37;
              }
              goto LABEL_35;
            }
            v147 = v51 - 5;
            if ( v147 )
            {
              if ( v147 != 1 )
                goto LABEL_485;
              FindDriverForCookie(&v228, **((_QWORD **)a1 + 3));
              if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
              {
                UmpdPtr::assert((UmpdPtr *)&v228);
                v148 = *(void (__fastcall **)(_QWORD))(v228 + 432);
                if ( v148 )
                  v148(*((_QWORD *)a1 + 4));
                goto LABEL_256;
              }
              goto LABEL_255;
            }
            FindDriverForCookie(&v228, **((_QWORD **)a1 + 3));
            if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
            {
              UmpdPtr::assert((UmpdPtr *)&v228);
              v120 = *(void (__fastcall **)(__int64, __int64))(v228 + 424);
              if ( !v120 )
                goto LABEL_256;
              v121 = a1[10];
              v122 = *((_QWORD *)a1 + 4);
              goto LABEL_286;
            }
            goto LABEL_255;
          }
          v149 = *((_QWORD *)a1 + 3);
          v150 = *(_QWORD **)(v149 + 16);
          *(_QWORD *)(v149 + 16) = v150[1];
          if ( !v150 )
            goto LABEL_142;
          FindDriverForCookie(&v228, *v150);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v228 + 368))(
                     *((_QWORD *)a1 + 3),
                     *((_QWORD *)a1 + 4),
                     a1[10]);
            goto LABEL_309;
          }
        }
        else
        {
          v151 = *((_QWORD *)a1 + 3);
          v152 = *(_QWORD **)(v151 + 16);
          *(_QWORD *)(v151 + 16) = v152[1];
          FindDriverForCookie(&v228, *v152);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v228 + 360))(*((_QWORD *)a1 + 3), a1[8]);
            goto LABEL_309;
          }
        }
      }
      else
      {
        v153 = *((_QWORD *)a1 + 3);
        v154 = *(_QWORD **)(v153 + 16);
        *(_QWORD *)(v153 + 16) = v154[1];
        FindDriverForCookie(&v228, *v154);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          v132 = (*(__int64 (__fastcall **)(_QWORD))(v228 + 352))(*((_QWORD *)a1 + 3));
          goto LABEL_309;
        }
      }
      goto LABEL_308;
    }
    if ( v8 == 32 )
    {
      v145 = *((_QWORD *)a1 + 3);
      v146 = *(_QWORD **)(v145 + 16);
      *(_QWORD *)(v145 + 16) = v146[1];
      FindDriverForCookie(&v228, *v146);
      if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
        UmpdPtr::assert((UmpdPtr *)&v228);
        v132 = (*(__int64 (__fastcall **)(_QWORD))(v228 + 344))(*((_QWORD *)a1 + 3));
        goto LABEL_309;
      }
      goto LABEL_308;
    }
    v22 = v8 - 23;
    if ( !v22 )
    {
      v35 = *((_QWORD *)a1 + 3);
      v36 = *(_QWORD **)(v35 + 16);
      *(_QWORD *)(v35 + 16) = v36[1];
      FindDriverForCookie(&v230, *v36);
      v16 = v230;
      if ( !v230 )
        goto LABEL_15;
      if ( *v230 != -19088744 )
        goto LABEL_145;
      *a3 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))v230
             + 34))(
              *((_QWORD *)a1 + 3),
              *((_QWORD *)a1 + 4),
              *((_QWORD *)a1 + 5),
              *((_QWORD *)a1 + 6),
              *((_QWORD *)a1 + 7),
              *((_QWORD *)a1 + 8),
              *((_QWORD *)a1 + 9),
              *((_QWORD *)a1 + 10),
              *((_QWORD *)a1 + 11),
              a1[24]);
      if ( !v244 )
        goto LABEL_16;
      v32 = *((_QWORD *)a1 + 9);
      goto LABEL_129;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v24 = *((_QWORD *)a1 + 3);
      v25 = *(_QWORD **)(v24 + 16);
      *(_QWORD *)(v24 + 16) = v25[1];
      FindDriverForCookie(&v230, *v25);
      v16 = v230;
      if ( v230 )
      {
        if ( *v230 != -19088744 )
          goto LABEL_145;
        v26 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD))v230 + 35))(
                *((_QWORD *)a1 + 3),
                a1[8],
                a1[9],
                *((_QWORD *)a1 + 5),
                a1[12],
                *((_QWORD *)a1 + 7));
        goto LABEL_37;
      }
LABEL_35:
      v9 = -1;
LABEL_36:
      v26 = 0;
LABEL_37:
      *a3 = v26;
      goto LABEL_16;
    }
    v60 = v23 - 1;
    if ( !v60 )
    {
      v143 = *((_QWORD *)a1 + 3);
      v144 = *(_QWORD **)(v143 + 16);
      *(_QWORD *)(v143 + 16) = v144[1];
      FindDriverForCookie(&v228, *v144);
      if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
        UmpdPtr::assert((UmpdPtr *)&v228);
        v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD))(v228 + 288))(
                 *((_QWORD *)a1 + 3),
                 a1[8],
                 *((_QWORD *)a1 + 5),
                 *((_QWORD *)a1 + 6),
                 a1[14],
                 *((_QWORD *)a1 + 8));
        goto LABEL_309;
      }
      goto LABEL_308;
    }
    v61 = v60 - 1;
    if ( !v61 )
    {
      v62 = (_QWORD *)*((_QWORD *)a1 + 3);
      FindDriverForCookie(&v230, *v62);
      v16 = v230;
      if ( v230 )
      {
        if ( *v230 != -19088744 )
          goto LABEL_145;
        v103 = (_DWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))v230 + 37))(
                           v62[1],
                           *((_QWORD *)a1 + 4),
                           a1[10],
                           *((_QWORD *)a1 + 6));
        *(_QWORD *)a3 = v103;
        if ( !a1[10] )
          goto LABEL_16;
        if ( !v103 )
          goto LABEL_16;
        v104 = (void *)*((_QWORD *)a1 + 8);
        if ( !v104 )
          goto LABEL_16;
        if ( a1[14] >= *v103 )
        {
          memcpy_0(v104, v103, (unsigned int)*v103);
          goto LABEL_16;
        }
        a1[14] = 0;
      }
      else
      {
        *(_QWORD *)a3 = 0;
      }
      goto LABEL_84;
    }
    v136 = v61 - 1;
    if ( !v136 )
    {
      v141 = (_QWORD *)*((_QWORD *)a1 + 3);
      FindDriverForCookie(&v228, *v141);
      if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
        UmpdPtr::assert((UmpdPtr *)&v228);
        v115 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v228 + 304))(
                 v141[1],
                 *((_QWORD *)a1 + 4),
                 a1[10],
                 a1[11],
                 *((_QWORD *)a1 + 6));
        *(_QWORD *)a3 = v115;
        v142 = (const void *)v115;
        if ( a1[11] == 3 )
        {
          if ( !v115 )
            goto LABEL_256;
          if ( !*((_QWORD *)a1 + 8) )
            goto LABEL_256;
          v108 = 16LL * *(unsigned int *)(v115 + 12);
          if ( v108 <= 0xFFFFFFFF )
          {
            v112 = 4LL * *(unsigned int *)(v115 + 8);
            if ( v112 <= 0xFFFFFFFF )
            {
              v113 = v108 + 16;
              if ( v113 >= 0x10 )
              {
                v114 = v113 + v112;
                if ( v114 >= v113
                  && a1[14] >= v114
                  && (unsigned int)GdiCopyFD_GLYPHSET(
                                     *((struct _FD_GLYPHSET **)a1 + 8),
                                     (struct _FD_GLYPHSET *)v115,
                                     v114) )
                {
                  goto LABEL_256;
                }
              }
            }
          }
        }
        else
        {
          if ( a1[11] != 2 || !v115 || !*((_QWORD *)a1 + 8) )
            goto LABEL_256;
          v116 = 0;
          while ( *(_WORD *)v115 || *(_WORD *)(v115 + 2) || *(_WORD *)(v115 + 4) )
          {
            if ( v116 + 1 < v116 )
              goto LABEL_254;
            v115 += 6;
            ++v116;
          }
          v117 = v116 + 1;
          if ( (unsigned int)v117 >= v116 )
          {
            v118 = 6 * v117;
            if ( (unsigned __int64)(6 * v117) <= 0xFFFFFFFF && a1[14] >= v118 )
            {
              memcpy_0(*((void **)a1 + 8), v142, v118);
              goto LABEL_256;
            }
          }
        }
LABEL_254:
        a1[14] = 0;
      }
      else
      {
        *(_QWORD *)a3 = 0;
      }
      goto LABEL_255;
    }
    v137 = v136 - 1;
    if ( !v137 )
    {
      v140 = (_QWORD *)*((_QWORD *)a1 + 3);
      FindDriverForCookie(&v228, *v140);
      if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
        UmpdPtr::assert((UmpdPtr *)&v228);
        v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(v228 + 312))(
                 v140[1],
                 *((_QWORD *)a1 + 4),
                 a1[10],
                 a1[11],
                 *((_QWORD *)a1 + 6),
                 *((_QWORD *)a1 + 7),
                 a1[16]);
        goto LABEL_309;
      }
      goto LABEL_308;
    }
    if ( v137 != 3 )
      goto LABEL_485;
    v138 = *((_QWORD *)a1 + 3);
    v139 = *(_QWORD **)(v138 + 16);
    *(_QWORD *)(v138 + 16) = v139[1];
    FindDriverForCookie(&v228, *v139);
    if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
    {
      UmpdPtr::assert((UmpdPtr *)&v228);
      *a3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int, _QWORD, unsigned int))(v228 + 336))(
              *((_QWORD *)a1 + 3),
              *((_QWORD *)a1 + 4),
              *((_QWORD *)a1 + 5),
              a1[12],
              a1[13],
              a1[14],
              a1[15],
              *((_QWORD *)a1 + 8),
              a1[18]);
      if ( !v244 )
        goto LABEL_256;
      v135 = *((_QWORD *)a1 + 5);
LABEL_315:
      if ( v135 )
        NtGdiBRUSHOBJ_DeleteRbrush(v135, 0);
      goto LABEL_256;
    }
    goto LABEL_317;
  }
  v18 = (char *)a1 + v5;
  v228 = (__int64)v18;
  if ( v8 > 0x6A )
  {
    if ( v8 <= 0x72 )
    {
      if ( v8 == 114 )
      {
        if ( a4 < 4 || v5 < 0x28 )
          return 0xFFFFFFFFLL;
        FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
        if ( (unsigned __int8)UmpdPtr::operator bool(&v229) )
        {
          v196 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
          if ( v196 )
          {
            v197 = fpAbortPrinter;
            goto LABEL_425;
          }
          goto LABEL_426;
        }
        goto LABEL_428;
      }
      v19 = v8 - 107;
      if ( !v19 )
      {
        if ( a4 >= 8 && v5 >= 0x30 )
        {
          *(_QWORD *)a3 = 0;
          EnterCriticalSection(&semUMPD);
          FindDriverForCookie(&v228, *((_QWORD *)a1 + 3));
          v56 = v228;
          if ( v228 )
          {
            if ( *(_DWORD *)v228 != -19088744 )
              goto LABEL_145;
            v105 = a1[9];
            if ( v105 )
            {
              v106 = FindPrinterHandle((struct UmpdPtr *)&v228, a1[8], v105);
              if ( v106 )
              {
                v107 = (void (__fastcall *)(_QWORD))RtlDecodePointer(fpClosePrinter);
                v107(*((_QWORD *)v106 + 2));
                *(_QWORD *)a3 = *((_QWORD *)v106 + 2);
                DeletePrinterHandle((struct UmpdPtr *)&v228, v106);
              }
            }
            UnloadUserModePrinterDriver((struct UmpdPtr *)&v228, a1[10], 0);
            v56 = v228;
          }
          else
          {
            v9 = -1;
          }
          if ( v56 )
          {
            if ( *(_DWORD *)v56 != -19088744 )
              goto LABEL_145;
            _InterlockedDecrement((volatile signed __int32 *)(v56 + 44));
          }
          LeaveCriticalSection(&semUMPD);
          goto LABEL_17;
        }
        return 0xFFFFFFFFLL;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        FindDriverForCookie(&v234, *((_QWORD *)a1 + 3));
        v16 = v234;
        if ( v234 )
        {
          if ( *(_DWORD *)v234 == -19088744 )
          {
            v72 = 0;
            while ( *(_DWORD *)v16 == -19088744 )
            {
              v70 = v72;
              v71 = *((_QWORD *)v16 + v72++ + 11) != 0;
              a3[v70] = v71;
              if ( v72 >= 104 )
                goto LABEL_16;
            }
          }
          goto LABEL_145;
        }
        memset_0(a3, 0, 0x1A0u);
        goto LABEL_16;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        if ( a4 >= 4 && v5 >= 0x60 )
        {
          FindDriverForCookie(&v230, *((_QWORD *)a1 + 3));
          v16 = v230;
          if ( !v230 )
          {
            v9 = -1;
            goto LABEL_16;
          }
          if ( *v230 != -19088744 )
            goto LABEL_145;
          v234 = FindPrinterHandle((struct UmpdPtr *)&v230, a1[8], a1[9]);
          if ( !v234 )
          {
            *a3 = -1;
            goto LABEL_16;
          }
          v230 = 0;
          v229 = 0;
          v240 = 0;
          v241 = 0;
          v242 = 0;
          v236 = 0;
          v232 = 0;
          v237 = 0;
          v233 = 0;
          v238 = 0;
          v235 = 0;
          v73 = RtlDecodePointer(fpDocumentEvent);
          v74 = a1[14];
          v75 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD))v73;
          v231 = v73;
          v76 = v74 - 1;
          if ( v76 )
          {
            v77 = v76 - 1;
            if ( !v77 )
              goto LABEL_463;
            v78 = v77 - 1;
            if ( v78 )
            {
              v79 = v78 - 1;
              if ( v79 )
              {
                v80 = v79 - 1;
                if ( v80 )
                {
                  v81 = v80 - 6;
                  if ( !v81 )
                  {
                    v85 = a1 + 16;
                    if ( a1 != (unsigned int *)-64LL )
                    {
                      *(_QWORD *)&v238 = *v85;
                      if ( (unsigned int)PointerFromOffsetHelper(
                                           a1,
                                           v5,
                                           0x60u,
                                           0x10u,
                                           (struct _OffsetPointer *)(a1 + 16)) )
                      {
                        v88 = *v85;
                        if ( *v85 )
                        {
                          *((_QWORD *)&v238 + 1) = a1 + 16;
                          v89 = (struct _OffsetPointer *)(v88 + 8);
                          if ( v88 != -8 )
                          {
                            v90 = *(_DWORD *)(v88 + 4);
                            v230 = *(_DWORD **)v89;
                            if ( (unsigned int)PointerFromOffsetHelper(v86, v5, v87, v90, v89) )
                            {
                              v92 = 0;
                              if ( *(_QWORD *)v89 )
                                v92 = v89;
                              v93 = a1 + 20;
                              v229 = v92;
                              if ( a1 != (unsigned int *)-80LL )
                              {
                                *((_QWORD *)&v235 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
                                if ( !*((_QWORD *)&v235 + 1) )
                                {
                                  v94 = a1[18];
                                  *(_QWORD *)&v235 = *v93;
                                  if ( (unsigned int)PointerFromOffsetHelper(
                                                       a1,
                                                       v5,
                                                       v91,
                                                       v94,
                                                       (struct _OffsetPointer *)(a1 + 20)) )
                                  {
                                    v75 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD))v231;
                                    if ( *v93 )
                                      *((_QWORD *)&v235 + 1) = a1 + 20;
                                    v18 = (char *)v228;
                                    goto LABEL_158;
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
LABEL_201:
                    v9 = -1;
                    goto LABEL_165;
                  }
                  if ( v81 != 2 )
                    goto LABEL_158;
                  v202 = 4;
                  goto LABEL_200;
                }
                v203 = (struct _OffsetPointer **)(a1 + 16);
                if ( !(unsigned int)UMPDPointerFromOffset(
                                      a1,
                                      v5,
                                      0x60u,
                                      8u,
                                      (struct _OffsetPointer *)(a1 + 16),
                                      (struct UMPDOffset *)&v238) )
                  goto LABEL_201;
                if ( !(unsigned int)UMPDPointerFromOffset(v204, v5, 0x60u, 0x28u, *v203, (struct UMPDOffset *)&v233) )
                  goto LABEL_201;
                v206 = *(_QWORD *)*v203;
                if ( !v206
                  || !UMPDStringPointerFromOffset(
                        v205,
                        v5,
                        0x60u,
                        (struct _OffsetPointer *)(v206 + 8),
                        (struct UMPDOffset *)&v241)
                  || !UMPDStringPointerFromOffset(
                        a1,
                        v5,
                        0x60u,
                        (struct _OffsetPointer *)(v206 + 16),
                        (struct UMPDOffset *)&v242) )
                {
                  goto LABEL_201;
                }
                v207 = UMPDStringPointerFromOffset(
                         a1,
                         v5,
                         0x60u,
                         (struct _OffsetPointer *)(v206 + 24),
                         (struct UMPDOffset *)&v240);
LABEL_460:
                if ( !v207 )
                  goto LABEL_201;
                v18 = (char *)v228;
                goto LABEL_462;
              }
LABEL_463:
              v202 = 8;
LABEL_200:
              if ( !(unsigned int)UMPDPointerFromOffset(
                                    a1,
                                    v5,
                                    0x60u,
                                    v202,
                                    (struct _OffsetPointer *)(a1 + 16),
                                    (struct UMPDOffset *)&v238) )
                goto LABEL_201;
LABEL_462:
              v75 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD))v231;
LABEL_158:
              if ( *((_QWORD *)a1 + 8) && *((_QWORD *)a1 + 8) + a1[15] > (__int64)v18 )
                goto LABEL_165;
              v82 = (_QWORD *)*((_QWORD *)a1 + 10);
              if ( !v82 )
              {
                v83 = (unsigned __int16 ***)(a1 + 20);
LABEL_161:
                if ( ((a1[14] - 1) & 0xFFFFFFFD) == 0 )
                  *v82 = 0;
                v84 = v75(
                        *((_QWORD *)v234 + 2),
                        *((_QWORD *)a1 + 6),
                        a1[14],
                        a1[15],
                        *((_QWORD *)a1 + 8),
                        a1[18],
                        *((_QWORD *)a1 + 10));
                *a3 = v84;
                if ( ((a1[14] - 1) & 0xFFFFFFFD) == 0 && v84 != -1 )
                {
                  v95 = **v83;
                  if ( v95 )
                  {
                    v96 = v95[34];
                    v97 = (char *)*((_QWORD *)a1 + 11);
                    v98 = v96 + v95[35];
                    if ( (__int64)&v97[v98] <= (__int64)v18 && (unsigned int)v98 >= v96 && (unsigned int)v98 <= 0x1FFFE )
                      memcpy_0(v97, v95, v96 + v95[35]);
                  }
                }
                a1[10] = GetLastError();
                goto LABEL_165;
              }
              if ( (__int64)v82 + a1[18] <= (__int64)v18 )
              {
                v83 = (unsigned __int16 ***)(a1 + 20);
                goto LABEL_161;
              }
LABEL_165:
              if ( *((_QWORD *)&v240 + 1) )
                **((_QWORD **)&v240 + 1) = v240;
              if ( *((_QWORD *)&v241 + 1) )
                **((_QWORD **)&v241 + 1) = v241;
              if ( *((_QWORD *)&v242 + 1) )
                **((_QWORD **)&v242 + 1) = v242;
              if ( *((_QWORD *)&v236 + 1) )
                **((_QWORD **)&v236 + 1) = v236;
              if ( *((_QWORD *)&v232 + 1) )
                **((_QWORD **)&v232 + 1) = v232;
              if ( *((_QWORD *)&v237 + 1) )
                **((_QWORD **)&v237 + 1) = v237;
              if ( *((_QWORD *)&v233 + 1) )
                **((_QWORD **)&v233 + 1) = v233;
              if ( *((_QWORD *)&v238 + 1) )
                **((_QWORD **)&v238 + 1) = v238;
              if ( v229 )
                *(_QWORD *)v229 = v230;
              if ( *((_QWORD *)&v235 + 1) )
                **((_QWORD **)&v235 + 1) = v235;
              goto LABEL_16;
            }
            if ( !(unsigned int)UMPDPointerFromOffset(
                                  a1,
                                  v5,
                                  0x60u,
                                  8u,
                                  (struct _OffsetPointer *)(a1 + 16),
                                  (struct UMPDOffset *)&v238)
              || !(unsigned int)UMPDPointerFromOffset(
                                  v208,
                                  v5,
                                  0x60u,
                                  0,
                                  *((struct _OffsetPointer **)a1 + 8),
                                  (struct UMPDOffset *)&v233) )
            {
              goto LABEL_201;
            }
            v209 = 8;
          }
          else
          {
            if ( !(unsigned int)UMPDPointerFromOffset(
                                  a1,
                                  v5,
                                  0x60u,
                                  0x20u,
                                  (struct _OffsetPointer *)(a1 + 16),
                                  (struct UMPDOffset *)&v238) )
              goto LABEL_201;
            v212 = *((_QWORD *)a1 + 8);
            if ( !v212
              || !UMPDStringPointerFromOffset(
                    v211,
                    v5,
                    0x60u,
                    (struct _OffsetPointer *)(v212 + 8),
                    (struct UMPDOffset *)&v237)
              || !(unsigned int)UMPDPointerFromOffset(
                                  a1,
                                  v5,
                                  0x60u,
                                  8u,
                                  (struct _OffsetPointer *)(v212 + 16),
                                  (struct UMPDOffset *)&v236) )
            {
              goto LABEL_201;
            }
          }
          if ( !(unsigned int)UMPDPointerFromOffset(
                                a1,
                                v5,
                                0x60u,
                                v209,
                                (struct _OffsetPointer *)(a1 + 20),
                                (struct UMPDOffset *)&v235) )
            goto LABEL_201;
          v207 = UMPDPointerFromOffset(
                   a1,
                   v5,
                   0x60u,
                   v210,
                   (struct _OffsetPointer *)(a1 + 22),
                   (struct UMPDOffset *)&v232);
          goto LABEL_460;
        }
        return 0xFFFFFFFFLL;
      }
      v193 = v21 - 1;
      if ( v193 )
      {
        v194 = v193 - 1;
        if ( v194 )
        {
          v195 = v194 - 1;
          if ( v195 )
          {
            if ( v195 != 1 )
              goto LABEL_485;
            if ( a4 < 4 || v5 < 0x28 )
              return 0xFFFFFFFFLL;
            FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
            if ( (unsigned __int8)UmpdPtr::operator bool(&v229) )
            {
              v196 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
              if ( v196 )
              {
                v197 = fpEndDocPrinter;
LABEL_425:
                v198 = (__int64 (__fastcall *)(_QWORD))RtlDecodePointer(v197);
                v199 = v198(*((_QWORD *)v196 + 2));
LABEL_427:
                *a3 = v199;
                goto LABEL_259;
              }
              goto LABEL_426;
            }
          }
          else
          {
            if ( a4 < 4 || v5 < 0x28 )
              return 0xFFFFFFFFLL;
            FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
            if ( (unsigned __int8)UmpdPtr::operator bool(&v229) )
            {
              v196 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
              if ( v196 )
              {
                v197 = fpEndPagePrinter;
                goto LABEL_425;
              }
LABEL_426:
              v199 = 0;
              goto LABEL_427;
            }
          }
        }
        else
        {
          if ( a4 < 4 || v5 < 0x28 )
            return 0xFFFFFFFFLL;
          FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
          if ( (unsigned __int8)UmpdPtr::operator bool(&v229) )
          {
            v196 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
            if ( v196 )
            {
              v197 = fpStartPagePrinter;
              goto LABEL_425;
            }
            goto LABEL_426;
          }
        }
LABEL_428:
        v9 = -1;
        goto LABEL_259;
      }
      if ( a4 < 4 || v5 < 0x58 )
        return 0xFFFFFFFFLL;
      FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
      if ( !(unsigned __int8)UmpdPtr::operator bool(&v229) )
        goto LABEL_428;
      v200 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
      v233 = 0;
      v232 = 0;
      v235 = 0;
      if ( v200
        && UMPDStringPointerFromOffset(a1, v5, 0x58u, (struct _OffsetPointer *)(a1 + 12), (struct UMPDOffset *)&v233)
        && UMPDStringPointerFromOffset(a1, v5, 0x58u, (struct _OffsetPointer *)(a1 + 14), (struct UMPDOffset *)&v232)
        && UMPDStringPointerFromOffset(a1, v5, 0x58u, (struct _OffsetPointer *)(a1 + 16), (struct UMPDOffset *)&v235) )
      {
        v201 = RtlDecodePointer(fpStartDocPrinterW);
        *a3 = ((__int64 (__fastcall *)(_QWORD, _QWORD, unsigned int *))v201)(*((_QWORD *)v200 + 2), a1[10], a1 + 12);
        a1[20] = GetLastError();
      }
      else
      {
        *a3 = 0;
      }
      if ( *((_QWORD *)&v233 + 1) )
        **((_QWORD **)&v233 + 1) = v233;
      if ( *((_QWORD *)&v232 + 1) )
        **((_QWORD **)&v232 + 1) = v232;
      v111 = (_QWORD *)*((_QWORD *)&v235 + 1);
      if ( !*((_QWORD *)&v235 + 1) )
        goto LABEL_259;
      v110 = v235;
LABEL_258:
      *v111 = v110;
LABEL_259:
      v109 = (UmpdPtr *)&v229;
      goto LABEL_257;
    }
    v213 = v8 - 115;
    if ( v213 )
    {
      v214 = v213 - 1;
      if ( v214 )
      {
        v215 = v214 - 1;
        if ( v215 )
        {
          v216 = v215 - 1;
          if ( !v216 )
          {
            v218 = *((_QWORD *)a1 + 4);
            if ( v218 )
              memcpy_0(*((void **)a1 + 4), *((const void **)a1 + 3), a1[10]);
            *(_QWORD *)a3 = v218;
            goto LABEL_17;
          }
          v217 = v216 - 1;
          if ( !v217 )
          {
            *a3 = UMPDFreeMemory(*((PVOID *)a1 + 3), *((PVOID *)a1 + 4), *((PVOID *)a1 + 5));
            goto LABEL_17;
          }
          if ( v217 == 1 )
          {
            if ( v6 )
              *a3 = NtGdiUMPDEngFreeUserMem(a1 + 6);
            goto LABEL_17;
          }
          goto LABEL_485;
        }
        v182 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a1[6]);
        goto LABEL_400;
      }
      if ( a4 < 4 || v5 < 0x50 )
        return 0xFFFFFFFFLL;
      v219 = *((_QWORD *)a1 + 3);
      v220 = a1 + 16;
      LODWORD(v231) = a1[16];
      FindDriverForCookie(&v229, v219);
      if ( !(unsigned __int8)UmpdPtr::operator bool(&v229) )
        goto LABEL_428;
      v234 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
      v237 = 0;
      v236 = 0;
      if ( v234
        && (unsigned int)UMPDPointerFromOffset(
                           a1,
                           v5,
                           0x50u,
                           *v220,
                           (struct _OffsetPointer *)(a1 + 14),
                           (struct UMPDOffset *)&v237)
        && (v222 = (struct _devicemodeW **)(a1 + 10),
            (unsigned int)UMPDPointerFromOffset(
                            v221,
                            v5,
                            0x50u,
                            8u,
                            (struct _OffsetPointer *)(a1 + 10),
                            (struct UMPDOffset *)&v236))
        && (unsigned int)ValidateDevModeBuffer(*v222, v228) )
      {
        v223 = RtlDecodePointer(fpQueryColorProfile);
        v224 = ((__int64 (__fastcall *)(_QWORD, struct _devicemodeW *, _QWORD, _QWORD, unsigned int *, unsigned int *))v223)(
                 *((_QWORD *)v234 + 2),
                 *v222,
                 a1[12],
                 *((_QWORD *)a1 + 7),
                 a1 + 16,
                 a1 + 17);
        *a3 = v224;
        if ( !v224 && *v220 > (unsigned int)v231 && GetLastError() == 122 )
          a1[18] = GetLastError();
      }
      else
      {
        *a3 = 0;
      }
    }
    else
    {
      if ( a4 < 4 || v5 < 0x40 )
        return 0xFFFFFFFFLL;
      FindDriverForCookie(&v229, *((_QWORD *)a1 + 3));
      if ( !(unsigned __int8)UmpdPtr::operator bool(&v229) )
      {
        v9 = -1;
        goto LABEL_259;
      }
      v225 = FindPrinterHandle((struct UmpdPtr *)&v229, a1[8], a1[9]);
      v237 = 0;
      v236 = 0;
      if ( v225
        && UMPDStringPointerFromOffset(a1, v5, 0x40u, (struct _OffsetPointer *)(a1 + 10), (struct UMPDOffset *)&v237)
        && (unsigned int)UMPDPointerFromOffset(
                           a1,
                           v5,
                           0x40u,
                           8u,
                           (struct _OffsetPointer *)(a1 + 12),
                           (struct UMPDOffset *)&v236)
        && (unsigned int)ValidateDevModeBuffer(*((struct _devicemodeW **)a1 + 6), (__int64)a1 + v5) )
      {
        v226 = (__int64 (__fastcall *)(_QWORD, unsigned int *))RtlDecodePointer(fpResetPrinterW);
        v227 = v226(*((_QWORD *)v225 + 2), a1 + 10);
      }
      else
      {
        v227 = 0;
      }
      *a3 = v227;
    }
    if ( *((_QWORD *)&v237 + 1) )
      **((_QWORD **)&v237 + 1) = v237;
    v111 = (_QWORD *)*((_QWORD *)&v236 + 1);
    if ( !*((_QWORD *)&v236 + 1) )
      goto LABEL_259;
    v110 = v236;
    goto LABEL_258;
  }
  if ( v8 != 106 )
  {
    if ( v8 > 0x45 )
    {
      v177 = v8 - 70;
      if ( !v177 )
      {
        v191 = *((_QWORD *)a1 + 3);
        v192 = *(_QWORD **)(v191 + 16);
        *(_QWORD *)(v191 + 16) = v192[1];
        FindDriverForCookie(&v228, *v192);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(v228 + 648))(
                   *((_QWORD *)a1 + 3),
                   *((_QWORD *)a1 + 4),
                   *((_QWORD *)a1 + 5),
                   *((_QWORD *)a1 + 6),
                   *((_QWORD *)a1 + 7),
                   *((_QWORD *)a1 + 8),
                   *((_QWORD *)a1 + 9),
                   *((_QWORD *)a1 + 10),
                   *((_QWORD *)a1 + 11),
                   *((_QWORD *)a1 + 12),
                   a1[26]);
          goto LABEL_309;
        }
        goto LABEL_308;
      }
      v178 = v177 - 1;
      if ( !v178 )
      {
        v189 = *((_QWORD *)a1 + 3);
        v190 = *(_QWORD **)(v189 + 16);
        *(_QWORD *)(v189 + 16) = v190[1];
        FindDriverForCookie(&v228, *v190);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v228 + 656))(
                   *((_QWORD *)a1 + 3),
                   *((_QWORD *)a1 + 4),
                   *((_QWORD *)a1 + 5),
                   *((_QWORD *)a1 + 6),
                   *((_QWORD *)a1 + 7),
                   *((_QWORD *)a1 + 8),
                   *((_QWORD *)a1 + 9));
          goto LABEL_309;
        }
        goto LABEL_308;
      }
      v179 = v178 - 3;
      if ( !v179 )
      {
        v187 = *((_QWORD *)a1 + 3);
        v188 = *(_QWORD **)(v187 + 16);
        *(_QWORD *)(v187 + 16) = v188[1];
        FindDriverForCookie(&v228, *v188);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int))(v228 + 680))(
                   *((_QWORD *)a1 + 3),
                   *((_QWORD *)a1 + 4),
                   *((_QWORD *)a1 + 5),
                   *((_QWORD *)a1 + 6),
                   *((_QWORD *)a1 + 7),
                   *((_QWORD *)a1 + 8),
                   a1[18],
                   a1[19]);
          goto LABEL_309;
        }
        goto LABEL_308;
      }
      v180 = v179 - 1;
      if ( v180 )
      {
        v181 = v180 - 1;
        if ( !v181 )
        {
          v183 = *((_QWORD *)a1 + 3);
          v184 = *(_QWORD **)(v183 + 16);
          *(_QWORD *)(v183 + 16) = v184[1];
          FindDriverForCookie(&v228, *v184);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, unsigned int, _QWORD))(v228 + 696))(
                     *((_QWORD *)a1 + 3),
                     *((_QWORD *)a1 + 4),
                     *((_QWORD *)a1 + 5),
                     a1[12],
                     a1[13],
                     *((_QWORD *)a1 + 7),
                     a1[16],
                     *((_QWORD *)a1 + 9));
            goto LABEL_309;
          }
          goto LABEL_308;
        }
        if ( v181 != 29 )
          goto LABEL_485;
        v182 = (PVOID)UMPDDrvEnableDriver(*((unsigned __int16 **)a1 + 3));
LABEL_400:
        *(_QWORD *)a3 = v182;
        goto LABEL_17;
      }
      v185 = *((_QWORD *)a1 + 3);
      v186 = *(_QWORD **)(v185 + 16);
      *(_QWORD *)(v185 + 16) = v186[1];
      FindDriverForCookie(&v228, *v186);
      if ( !(unsigned __int8)UmpdPtr::operator bool(&v228) )
        goto LABEL_308;
      UmpdPtr::assert((UmpdPtr *)&v228);
      v170 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(v228 + 688);
    }
    else
    {
      if ( v8 == 69 )
      {
        v175 = *((_QWORD *)a1 + 3);
        v176 = *(_QWORD **)(v175 + 16);
        *(_QWORD *)(v175 + 16) = v176[1];
        FindDriverForCookie(&v228, *v176);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          *a3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, unsigned int))(v228 + 640))(
                  *((_QWORD *)a1 + 3),
                  *((_QWORD *)a1 + 4),
                  *((_QWORD *)a1 + 5),
                  *((_QWORD *)a1 + 6),
                  *((_QWORD *)a1 + 7),
                  *((_QWORD *)a1 + 8),
                  *((_QWORD *)a1 + 9),
                  *((_QWORD *)a1 + 10),
                  *((_QWORD *)a1 + 11),
                  *((_QWORD *)a1 + 12),
                  a1[26],
                  *((_QWORD *)a1 + 14),
                  a1[30]);
          if ( !v244 )
            goto LABEL_256;
          v135 = *((_QWORD *)a1 + 14);
          goto LABEL_315;
        }
LABEL_317:
        *a3 = 0;
        goto LABEL_255;
      }
      v157 = v8 - 53;
      if ( !v157 )
      {
        v174 = (_QWORD *)*((_QWORD *)a1 + 3);
        FindDriverForCookie(&v228, *v174);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          UmpdPtr::assert((UmpdPtr *)&v228);
          v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(v228 + 512))(
                   v174[1],
                   *((_QWORD *)a1 + 4),
                   a1[10],
                   *((_QWORD *)a1 + 6),
                   *((_QWORD *)a1 + 7),
                   a1[16]);
          goto LABEL_309;
        }
        goto LABEL_308;
      }
      v158 = v157 - 4;
      if ( !v158 )
      {
        v171 = *((_QWORD *)a1 + 3);
        v172 = *(_QWORD **)(v171 + 16);
        *(_QWORD *)(v171 + 16) = v172[1];
        FindDriverForCookie(&v228, *v172);
        UmpdPtr::assert((UmpdPtr *)&v228);
        if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
        {
          v132 = v173(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 4));
          goto LABEL_309;
        }
        goto LABEL_308;
      }
      v159 = v158 - 1;
      if ( v159 )
      {
        v160 = v159 - 6;
        if ( !v160 )
        {
          v167 = (_QWORD *)*((_QWORD *)a1 + 3);
          FindDriverForCookie(&v228, *v167);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v125 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, unsigned int, unsigned int))(v228 + 600))(
                     v167[1],
                     *((_QWORD *)a1 + 4),
                     *((_QWORD *)a1 + 5),
                     a1[12],
                     *((_QWORD *)a1 + 7),
                     a1[16],
                     *((_QWORD *)a1 + 9),
                     a1[20],
                     a1[21]);
            goto LABEL_292;
          }
          goto LABEL_291;
        }
        v161 = v160 - 1;
        if ( v161 )
        {
          v162 = v161 - 1;
          if ( !v162 )
          {
            v165 = (_QWORD *)*((_QWORD *)a1 + 3);
            FindDriverForCookie(&v228, *v165);
            if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
            {
              UmpdPtr::assert((UmpdPtr *)&v228);
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(v228 + 616))(
                v165[1],
                *((_QWORD *)a1 + 4),
                *((_QWORD *)a1 + 5),
                *((_QWORD *)a1 + 6));
              goto LABEL_256;
            }
            goto LABEL_255;
          }
          if ( v162 != 2 )
            goto LABEL_485;
          v163 = *((_QWORD *)a1 + 3);
          v164 = *(_QWORD **)(v163 + 16);
          *(_QWORD *)(v163 + 16) = v164[1];
          FindDriverForCookie(&v228, *v164);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, unsigned int, _QWORD, _QWORD, unsigned int))(v228 + 632))(
                     *((_QWORD *)a1 + 3),
                     *((_QWORD *)a1 + 4),
                     *((_QWORD *)a1 + 5),
                     *((_QWORD *)a1 + 6),
                     a1[14],
                     *((_QWORD *)a1 + 8),
                     a1[18],
                     *((_QWORD *)a1 + 10),
                     *((_QWORD *)a1 + 11),
                     a1[24]);
            goto LABEL_309;
          }
        }
        else
        {
          v166 = (_QWORD *)*((_QWORD *)a1 + 3);
          FindDriverForCookie(&v228, *v166);
          if ( (unsigned __int8)UmpdPtr::operator bool(&v228) )
          {
            UmpdPtr::assert((UmpdPtr *)&v228);
            v132 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v228 + 608))(v166[1], *((_QWORD *)a1 + 4));
            goto LABEL_309;
          }
        }
        goto LABEL_308;
      }
      v168 = *((_QWORD *)a1 + 3);
      v169 = *(_QWORD **)(v168 + 16);
      *(_QWORD *)(v168 + 16) = v169[1];
      FindDriverForCookie(&v228, *v169);
      if ( !(unsigned __int8)UmpdPtr::operator bool(&v228) )
      {
LABEL_308:
        v9 = -1;
        v132 = 0;
        goto LABEL_309;
      }
      UmpdPtr::assert((UmpdPtr *)&v228);
      v170 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(v228 + 552);
    }
    v132 = v170(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 4));
    goto LABEL_309;
  }
  v37 = 0;
  v229 = 0;
  if ( a4 < 8 )
    return 0xFFFFFFFFLL;
  v38 = ghSpooler == 0;
  *(_QWORD *)a3 = 0;
  if ( !v38 || (unsigned int)bLoadSpooler() )
  {
    v231 = RtlDecodePointer(fpOpenPrinterW);
    if ( v5 >= 0x48 )
    {
      v39 = a1 + 10;
      v230 = 0;
      v233 = 0;
      v232 = 0;
      if ( a1 == (unsigned int *)-40LL )
        goto LABEL_70;
      v230 = (_DWORD *)*v39;
      if ( !(unsigned int)PointerFromOffsetHelper(a1, v5, 0x48u, 8u, (struct _OffsetPointer *)(a1 + 10)) )
        goto LABEL_70;
      if ( *v39 )
        v37 = a1 + 10;
      if ( (unsigned int)ValidateDevModeBuffer(*((struct _devicemodeW **)a1 + 5), v228)
        && (v40 = a1 + 6,
            UMPDStringPointerFromOffset(a1, v5, 0x48u, (struct _OffsetPointer *)(a1 + 6), (struct UMPDOffset *)&v233))
        && UMPDStringPointerFromOffset(a1, v5, 0x48u, (struct _OffsetPointer *)(a1 + 8), (struct UMPDOffset *)&v232) )
      {
        ((void (__fastcall *)(_QWORD, void **, unsigned int *))v231)(*v40, &v229, a1 + 8);
      }
      else
      {
LABEL_70:
        v9 = -1;
        v40 = a1 + 6;
      }
      if ( v229 )
      {
        LoadUserModePrinterDriver(&v231, *v40, 0);
        v41 = (volatile signed __int32 *)v231;
        if ( !v231 )
          goto LABEL_514;
        if ( *(_DWORD *)v231 != -19088744 )
          goto LABEL_145;
        EnterCriticalSection(&semUMPD);
        if ( *v41 != -19088744 )
          goto LABEL_145;
        _InterlockedIncrement(v41 + 11);
        LeaveCriticalSection(&semUMPD);
        if ( !v41 )
          goto LABEL_514;
        if ( *v41 != -19088744 )
          goto LABEL_145;
        if ( (unsigned int)bAddPrinterHandle((struct UmpdPtr *)&v231, a1[14], a1[15], v229) )
        {
          if ( *v41 != -19088744 )
            goto LABEL_145;
          *(_QWORD *)a3 = *((_QWORD *)v41 + 9);
        }
        else
        {
LABEL_514:
          if ( (unsigned __int8)UmpdPtr::operator bool(&v231) )
          {
            UnloadUserModePrinterDriver((struct UmpdPtr *)&v231, 1, 0);
            if ( a1[16] )
              UnloadUserModePrinterDriver((struct UmpdPtr *)&v231, 0, 0);
            v41 = (volatile signed __int32 *)v231;
          }
          v42 = (void (__fastcall *)(void *))RtlDecodePointer(fpClosePrinter);
          v42(v229);
        }
        if ( v41 )
        {
          if ( *v41 != -19088744 )
            goto LABEL_145;
          _InterlockedDecrement(v41 + 11);
        }
      }
      if ( v37 )
        *v37 = v230;
      if ( *((_QWORD *)&v233 + 1) )
        **((_QWORD **)&v233 + 1) = v233;
      if ( *((_QWORD *)&v232 + 1) )
        **((_QWORD **)&v232 + 1) = v232;
      goto LABEL_17;
    }
    return 0xFFFFFFFFLL;
  }
LABEL_17:
  if ( v243 )
    NtGdiSetPUMPDOBJ(v239, 0, a1 + 4, 0);
  return v9;
}

```

## disassembly

```asm
0x18003bd20  mov     rax, rsp
0x18003bd23  mov     [rax+18h], rbx
0x18003bd27  push    rbp
0x18003bd28  push    rsi
0x18003bd29  push    rdi
0x18003bd2a  push    r12
0x18003bd2c  push    r13
0x18003bd2e  push    r14
0x18003bd30  push    r15
0x18003bd32  lea     rbp, [rax-78h]
0x18003bd36  sub     rsp, 140h
0x18003bd3d  xor     r13d, r13d
0x18003bd40  movaps  xmmword ptr [rax-48h], xmm6
0x18003bd44  mov     rdi, rcx
0x18003bd47  mov     [rbp+70h+var_78], r13
0x18003bd4b  mov     r12d, 7FFFFFFFh
0x18003bd51  mov     [rbp+70h+arg_0], r13d
0x18003bd58  cmp     edx, r12d
0x18003bd5b  mov     ecx, r13d
0x18003bd5e  mov     r14d, r9d
0x18003bd61  mov     [rbp+70h+arg_8], ecx
0x18003bd67  mov     ebx, [rdi+4]
0x18003bd6a  lea     r15d, [r13+1]
0x18003bd6e  cmovb   r12d, edx
0x18003bd72  mov     rsi, r8
0x18003bd75  cmp     ebx, 69h ; 'i'
0x18003bd78  ja      short loc_18003BDAC
0x18003bd7a  mov     rcx, [rdi+10h]
0x18003bd7e  lea     r9, [rbp+70h+arg_8]
0x18003bd85  lea     r8, [rbp+70h+var_78]
0x18003bd89  mov     edx, r15d
0x18003bd8c  call    cs:__imp_NtGdiSetPUMPDOBJ
0x18003bd93  nop     dword ptr [rax+rax+00h]
0x18003bd98  mov     [rbp+70h+arg_0], eax
0x18003bd9e  test    eax, eax
0x18003bda0  jz      loc_18003C781
0x18003bda6  mov     ecx, [rbp+70h+arg_8]
0x18003bdac  cmp     ebx, 2Fh ; '/'
0x18003bdaf  ja      loc_18003BE73
0x18003bdb5  jz      loc_18003D8B0
0x18003bdbb  cmp     ebx, 14h
0x18003bdbe  ja      loc_18003BEF1
0x18003bdc4  jz      loc_18003C318
0x18003bdca  cmp     ebx, 0Ch
0x18003bdcd  jbe     loc_18003C047
0x18003bdd3  sub     ebx, 0Dh
0x18003bdd6  jz      loc_18003C462
0x18003bddc  sub     ebx, r15d
0x18003bddf  jz      loc_18003C5B5
0x18003bde5  sub     ebx, r15d
0x18003bde8  jnz     loc_18003BF4F
0x18003bdee  mov     rcx, [rdi+18h]
0x18003bdf2  mov     rdx, [rcx+10h]
0x18003bdf6  mov     rax, [rdx+8]
0x18003bdfa  mov     [rcx+10h], rax
0x18003bdfe  lea     rcx, [rbp+70h+var_F0]
0x18003be02  mov     rdx, [rdx]
0x18003be05  call    ?FindDriverForCookie@@YA?AVUmpdPtr@@_K@Z; FindDriverForCookie(unsigned __int64)
0x18003be0a  mov     rbx, [rbp+70h+var_F0]
0x18003be0e  mov     r14d, 0FEDCBA98h
0x18003be14  test    rbx, rbx
0x18003be17  jnz     loc_18003CBCB
0x18003be1d  or      r15d, 0FFFFFFFFh
0x18003be21  mov     [rsi], r13d
0x18003be24  test    rbx, rbx
0x18003be27  jnz     loc_18003C842
0x18003be2d  cmp     [rbp+70h+arg_0], r13d
0x18003be34  jz      short loc_18003BE4F
0x18003be36  mov     rcx, [rbp+70h+var_78]
0x18003be3a  lea     r8, [rdi+10h]
0x18003be3e  xor     r9d, r9d
0x18003be41  xor     edx, edx
0x18003be43  call    cs:__imp_NtGdiSetPUMPDOBJ
0x18003be4a  nop     dword ptr [rax+rax+00h]
0x18003be4f  mov     eax, r15d
0x18003be52  lea     r11, [rsp+170h+var_30]
0x18003be5a  mov     rbx, [r11+50h]
0x18003be5e  movaps  xmm6, xmmword ptr [r11-10h]
0x18003be63  mov     rsp, r11
0x18003be66  pop     r15
0x18003be68  pop     r14
0x18003be6a  pop     r13
0x18003be6c  pop     r12
0x18003be6e  pop     rdi
0x18003be6f  pop     rsi
0x18003be70  pop     rbp
0x18003be71  retn
0x18003be73  mov     r13d, r12d
0x18003be76  add     r13, rdi
0x18003be79  mov     [rsp+170h+var_100], r13
0x18003be7e  cmp     ebx, 6Ah ; 'j'
0x18003be81  jbe     loc_18003C126
0x18003be87  cmp     ebx, 72h ; 'r'
0x18003be8a  ja      loc_18003E47B
0x18003be90  jz      loc_18003E422
0x18003be96  sub     ebx, 6Bh ; 'k'
0x18003be99  jz      loc_18003C541
0x18003be9f  sub     ebx, r15d
0x18003bea2  jz      loc_18003C78B
0x18003bea8  sub     ebx, r15d
0x18003beab  jnz     loc_18003DF48
0x18003beb1  cmp     r14d, 4
0x18003beb5  jb      loc_18003C781
0x18003bebb  cmp     r12d, 60h ; '`'
0x18003bebf  jb      loc_18003C781
0x18003bec5  mov     rdx, [rdi+18h]
0x18003bec9  lea     rcx, [rbp+70h+var_F0]
0x18003becd  call    ?FindDriverForCookie@@YA?AVUmpdPtr@@_K@Z; FindDriverForCookie(unsigned __int64)
0x18003bed2  mov     rbx, [rbp+70h+var_F0]
0x18003bed6  mov     r14d, 0FEDCBA98h
0x18003bedc  test    rbx, rbx
0x18003bedf  jnz     loc_18003CCF6
0x18003bee5  or      r15d, 0FFFFFFFFh
0x18003bee9  xor     r13d, r13d
0x18003beec  jmp     loc_18003BE24
0x18003bef1  cmp     ebx, 20h ; ' '
0x18003bef4  ja      loc_18003C3F7
0x18003befa  jz      loc_18003D6BB
0x18003bf00  sub     ebx, 17h
0x18003bf03  jz      loc_18003C086
0x18003bf09  sub     ebx, r15d
0x18003bf0c  jnz     loc_18003C630
0x18003bf12  mov     rcx, [rdi+18h]
0x18003bf16  mov     rdx, [rcx+10h]
0x18003bf1a  mov     rax, [rdx+8]
0x18003bf1e  mov     [rcx+10h], rax
0x18003bf22  lea     rcx, [rbp+70h+var_F0]
0x18003bf26  mov     rdx, [rdx]
0x18003bf29  call    ?FindDriverForCookie@@YA?AVUmpdPtr@@_K@Z; FindDriverForCookie(unsigned __int64)
0x18003bf2e  mov     rbx, [rbp+70h+var_F0]
0x18003bf32  mov     r14d, 0FEDCBA98h
0x18003bf38  test    rbx, rbx
0x18003bf3b  jnz     loc_18003CD8A
0x18003bf41  or      r15d, 0FFFFFFFFh
0x18003bf45  mov     eax, r13d
0x18003bf48  mov     [rsi], eax
0x18003bf4a  jmp     loc_18003BE24
0x18003bf4f  sub     ebx, r15d
0x18003bf52  jz      loc_18003C66E
0x18003bf58  sub     ebx, r15d
0x18003bf5b  jz      loc_18003D387
0x18003bf61  sub     ebx, r15d
0x18003bf64  jnz     loc_18003C4B0
0x18003bf6a  mov     rcx, [rdi+18h]
0x18003bf6e  cmp     [rcx+4Ch], r13w
0x18003bf73  jz      loc_18003C76E
0x18003bf79  test    rcx, rcx
0x18003bf7c  jz      loc_18003C7C3
0x18003bf82  mov     rdx, [rcx+10h]
0x18003bf86  mov     rax, [rdx+8]
0x18003bf8a  mov     [rcx+10h], rax
0x18003bf8e  test    rdx, rdx
0x18003bf91  jz      loc_18003C7C3
0x18003bf97  mov     rdx, [rdx]
0x18003bf9a  lea     rcx, [rbp+70h+var_F0]
0x18003bf9e  call    ?FindDriverForCookie@@YA?AVUmpdPtr@@_K@Z; FindDriverForCookie(unsigned __int64)
0x18003bfa3  mov     rbx, [rbp+70h+var_F0]
0x18003bfa7  mov     r14d, 0FEDCBA98h
0x18003bfad  test    rbx, rbx
0x18003bfb0  jz      loc_18003BE1D
0x18003bfb6  cmp     [rbx], r14d
0x18003bfb9  jnz     loc_18003C7F0
0x18003bfbf  mov     eax, [rdi+68h]
0x18003bfc2  mov     rcx, [rdi+58h]
0x18003bfc6  mov     r9, [rdi+30h]
0x18003bfca  mov     r8, [rdi+28h]
0x18003bfce  mov     rdx, [rdi+20h]
0x18003bfd2  mov     dword ptr [rsp+170h+var_120], eax
0x18003bfd6  mov     rax, [rdi+60h]
0x18003bfda  mov     [rsp+170h+var_128], rax
0x18003bfdf  mov     rax, [rbx+0E8h]
0x18003bfe6  mov     [rsp+170h+var_130], rcx
0x18003bfeb  mov     rcx, [rdi+50h]
0x18003bfef  mov     [rsp+170h+var_138], rcx
0x18003bff4  mov     rcx, [rdi+48h]
0x18003bff8  mov     [rsp+170h+var_140], rcx
0x18003bffd  mov     rcx, [rdi+40h]
0x18003c001  mov     [rsp+170h+var_148], rcx
0x18003c006  mov     rcx, [rdi+38h]
0x18003c00a  mov     [rsp+170h+var_150], rcx
0x18003c00f  mov     rcx, [rdi+18h]
0x18003c013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c018  mov     [rsi], eax
0x18003c01a  cmp     [rbp+70h+arg_8], r13d
0x18003c021  jz      loc_18003BE24
0x18003c027  mov     rcx, [rdi+58h]
0x18003c02b  test    rcx, rcx
0x18003c02e  jz      loc_18003BE24
0x18003c034  xor     edx, edx
0x18003c036  call    cs:__imp_NtGdiBRUSHOBJ_DeleteRbrush
0x18003c03d  nop     dword ptr [rax+rax+00h]
0x18003c042  jmp     loc_18003BE24
0x18003c047  jz      loc_18003D291
0x18003c04d  test    ebx, ebx
0x18003c04f  jnz     loc_18003C2DA
0x18003c055  mov     rdx, [rdi+18h]
0x18003c059  lea     rcx, [rsp+170h+var_F8]
0x18003c05e  call    ?FindDriverForCookie@@YA?AVUmpdPtr@@_K@Z; FindDriverForCookie(unsigned __int64)
0x18003c063  mov     rbx, [rsp+170h+var_F8]
0x18003c068  mov     r14d, 0FEDCBA98h
0x18003c06e  test    rbx, rbx
0x18003c071  jnz     loc_18003CDC3
0x18003c077  mov     r12, r13
0x18003c07a  or      r15d, 0FFFFFFFFh
0x18003c07e  mov     [rsi], r12
0x18003c081  jmp     loc_18003BE24
0x18003c086  mov     rcx, [rdi+18h]
0x18003c08a  mov     rdx, [rcx+10h]
0x18003c08e  mov     rax, [rdx+8]
0x18003c092  mov     [rcx+10h], rax
0x18003c096  lea     rcx, [rbp+70h+var_F0]
0x18003c09a  mov     rdx, [rdx]
0x18003c09d  call    ?FindDriverForCookie@@YA?AVUmpdPtr@@_K@Z; FindDriverForCookie(unsigned __int64)
0x18003c0a2  mov     rbx, [rbp+70h+var_F0]
0x18003c0a6  mov     r14d, 0FEDCBA98h
0x18003c0ac  test    rbx, rbx
0x18003c0af  jz      loc_18003BE1D
0x18003c0b5  cmp     [rbx], r14d
0x18003c0b8  jnz     loc_18003C7F0
0x18003c0be  mov     eax, [rdi+60h]
0x18003c0c1  mov     rcx, [rdi+58h]
0x18003c0c5  mov     r9, [rdi+30h]
0x18003c0c9  mov     r8, [rdi+28h]
0x18003c0cd  mov     rdx, [rdi+20h]
0x18003c0d1  mov     dword ptr [rsp+170h+var_128], eax
0x18003c0d5  mov     rax, [rbx+110h]
0x18003c0dc  mov     [rsp+170h+var_130], rcx
0x18003c0e1  mov     rcx, [rdi+50h]
0x18003c0e5  mov     [rsp+170h+var_138], rcx
0x18003c0ea  mov     rcx, [rdi+48h]
0x18003c0ee  mov     [rsp+170h+var_140], rcx
0x18003c0f3  mov     rcx, [rdi+40h]
0x18003c0f7  mov     [rsp+170h+var_148], rcx
0x18003c0fc  mov     rcx, [rdi+38h]
0x18003c100  mov     [rsp+170h+var_150], rcx
0x18003c105  mov     rcx, [rdi+18h]
0x18003c109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c10e  mov     [rsi], eax
0x18003c110  cmp     [rbp+70h+arg_8], r13d
0x18003c117  jz      loc_18003BE24
0x18003c11d  mov     rcx, [rdi+48h]
0x18003c121  jmp     loc_18003C707
0x18003c126  jnz     loc_18003D8F0
0x18003c12c  xor     r13d, r13d
0x18003c12f  mov     [rsp+170h+var_F8], r13
0x18003c134  cmp     r14d, 8
0x18003c138  jb      loc_18003C781
0x18003c13e  cmp     cs:ghSpooler, r13
0x18003c145  mov     [rsi], r13
0x18003c148  jz      loc_18003DEF3
0x18003c14e  mov     rcx, cs:fpOpenPrinterW; Pointer
0x18003c155  call    cs:__imp_RtlDecodePointer
0x18003c15c  nop     dword ptr [rax+rax+00h]
0x18003c161  mov     [rbp+70h+var_E8], rax
0x18003c165  cmp     r12d, 48h ; 'H'
0x18003c169  jb      loc_18003C781
0x18003c16f  lea     rbx, [rdi+28h]
0x18003c173  mov     [rbp+70h+var_F0], r13
0x18003c177  xorps   xmm0, xmm0
0x18003c17a  xorps   xmm1, xmm1
0x18003c17d  movdqu  [rbp+70h+var_D0], xmm0
0x18003c182  movdqu  [rbp+70h+var_E0], xmm1
0x18003c187  test    rbx, rbx
0x18003c18a  jz      short loc_18003C1F6
0x18003c18c  mov     rax, [rbx]
0x18003c18f  mov     r9d, 8; unsigned int
0x18003c195  mov     edx, r12d; unsigned int
0x18003c198  mov     [rbp+70h+var_F0], rax
0x18003c19c  mov     rcx, rdi; void *
0x18003c19f  mov     [rsp+170h+var_150], rbx; struct _OffsetPointer *
0x18003c1a4  lea     r8d, [r9+40h]; unsigned int
0x18003c1a8  call    ?PointerFromOffsetHelper@@YAHPEAXKKKPEAU_OffsetPointer@@@Z; PointerFromOffsetHelper(void *,ulong,ulong,ulong,_OffsetPointer *)
0x18003c1ad  xor     r9d, r9d
0x18003c1b0  test    eax, eax
0x18003c1b2  jz      short loc_18003C1F6
0x18003c1b4  cmp     [rbx], r9
0x18003c1b7  mov     rdx, [rsp+170h+var_100]; __int64
0x18003c1bc  mov     rcx, [rdi+28h]; struct _devicemodeW *
0x18003c1c0  cmovnz  r13, rbx
0x18003c1c4  call    ?ValidateDevModeBuffer@@YAHPEAU_devicemodeW@@_J@Z; ValidateDevModeBuffer(_devicemodeW *,__int64)
0x18003c1c9  test    eax, eax
0x18003c1cb  jz      short loc_18003C1F6
0x18003c1cd  lea     rax, [rbp+70h+var_D0]
0x18003c1d1  mov     r8d, 48h ; 'H'; unsigned int
0x18003c1d7  lea     rbx, [rdi+18h]
0x18003c1db  mov     [rsp+170h+var_150], rax; struct UMPDOffset *
0x18003c1e0  mov     r9, rbx; struct _OffsetPointer *
0x18003c1e3  mov     edx, r12d; unsigned int
0x18003c1e6  mov     rcx, rdi; void *
0x18003c1e9  call    ?UMPDStringPointerFromOffset@@YAHPEAXKKPEAU_OffsetPointer@@PEAUUMPDOffset@@@Z; UMPDStringPointerFromOffset(void *,ulong,ulong,_OffsetPointer *,UMPDOffset *)
0x18003c1ee  test    eax, eax
0x18003c1f0  jnz     loc_18003DF05
0x18003c1f6  xor     r12d, r12d
0x18003c1f9  or      r15d, 0FFFFFFFFh
0x18003c1fd  lea     rbx, [rdi+18h]
0x18003c201  mov     r9, [rsp+170h+var_F8]
0x18003c206  test    r9, r9
0x18003c209  jz      loc_18003C3BE
0x18003c20f  cmp     [rdi+40h], r12d
0x18003c213  lea     rcx, [rbp+70h+var_E8]
  ... truncated ...
```
