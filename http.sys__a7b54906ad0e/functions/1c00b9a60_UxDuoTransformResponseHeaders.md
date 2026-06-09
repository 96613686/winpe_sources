# UxDuoTransformResponseHeaders

- ea: `0x1c00b9a60`
- end: `0x1c00baa9f`
- name: `UxDuoTransformResponseHeaders`
- size: `4159`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1c00c65b0`

## callees

- `0x1c0002c80`
- `0x1c0002e9c`
- `0x1c000b2f0`
- `0x1c000b4f0`
- `0x1c000b798`
- `0x1c000e710`
- `0x1c00138c0`
- `0x1c0013934`
- `0x1c00139a8`
- `0x1c001b900`
- `0x1c008f3a8`
- `0x1c009153c`
- `0x1c0094640`
- `0x1c00959d0`
- `0x1c0095a64`
- `0x1c00adc20`
- `0x1c00b83b0`
- `0x1c00b9468`
- `0x1c00b9a60`
- `0x1c00baab0`
- `0x1c010ecf0`
- `0x1c010f088`
- `0x1c010f300`
- `0x1c0112628`
- `0x1c011459c`
- `0x1c0120b34`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00ba0af`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00ba9b5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00baa04`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00ba0af`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00ba9b5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00baa04`
- `ntoskrnl!_strnicmp` at `0x1c00ba29f`
- `ntoskrnl!_strnicmp` at `0x1c00ba32a`
- `ntoskrnl!_strnicmp` at `0x1c00ba46e`
- `ntoskrnl!_strnicmp` at `0x1c00eb534`
- `ntoskrnl!_strnicmp` at `0x1c00eb554`
- `ntoskrnl!_strnicmp` at `0x1c00eb574`
- `ntoskrnl!_strnicmp` at `0x1c00eb5b2`
- `ntoskrnl!_strnicmp` at `0x1c00eb5db`
- `ntoskrnl!_strnicmp` at `0x1c00ba29f`
- `ntoskrnl!_strnicmp` at `0x1c00ba32a`
- `ntoskrnl!_strnicmp` at `0x1c00ba46e`
- `ntoskrnl!_strnicmp` at `0x1c00eb534`
- `ntoskrnl!_strnicmp` at `0x1c00eb554`
- `ntoskrnl!_strnicmp` at `0x1c00eb574`
- `ntoskrnl!_strnicmp` at `0x1c00eb5b2`
- `ntoskrnl!_strnicmp` at `0x1c00eb5db`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00b9b6f`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00b9b6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00ba4d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00baa64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00eb64d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00eb6ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00ba4d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00baa64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00eb64d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00eb6ad`

## string_xrefs

- `0x1c00ba320`: `:path`

## pseudocode

```c
__int64 __fastcall UxDuoTransformResponseHeaders(__int64 a1, __int64 **a2, _BYTE *a3)
{
  __int64 v3; // rax
  __int64 v7; // r10
  struct _MDL *v8; // r14
  __int64 v9; // rbx
  char *v10; // r12
  unsigned __int64 v11; // rdi
  __int64 *v12; // rsi
  char *MappedSystemVa; // rax
  char *v14; // rdx
  ULONG v15; // ecx
  char *v16; // rdx
  __int64 v17; // rax
  int v18; // esi
  char *PoolWithTagPriority; // rax
  char *v20; // rdi
  __int64 v21; // r13
  __int64 v22; // rsi
  int Task; // eax
  int CollectionHeaderValue; // r14d
  __int64 **v25; // r12
  __int16 v26; // bx
  unsigned int v27; // esi
  unsigned __int64 v28; // rdi
  __int64 *v29; // r15
  int v30; // ecx
  struct _MDL *v31; // r13
  char *v32; // rax
  ULONG ByteCount; // r14d
  __int64 v34; // r9
  char *v35; // r12
  int v36; // r14d
  char *v37; // r12
  __int64 v38; // rax
  unsigned __int64 v39; // rax
  __int64 *v40; // rdx
  unsigned __int64 v41; // rcx
  _BYTE *v42; // r13
  __int64 v43; // rcx
  unsigned int v44; // edi
  __int64 v45; // rsi
  _BYTE *v46; // rbx
  unsigned int v47; // edi
  int v48; // eax
  unsigned int v49; // eax
  _BYTE *v50; // rcx
  __int64 *v51; // r15
  unsigned int v52; // esi
  struct _MDL *v53; // rcx
  __int16 v54; // bx
  int v55; // edx
  unsigned __int64 v56; // rdi
  char *v57; // rax
  ULONG v58; // r14d
  char *v59; // r12
  int v60; // r14d
  char *v61; // r12
  __int64 v62; // rax
  unsigned __int64 v63; // rax
  __int64 *v64; // rcx
  unsigned __int64 v65; // rdx
  _BYTE *v66; // rax
  _BYTE *v67; // rcx
  int v68; // r9d
  _BYTE *v69; // rdx
  __int64 v70; // r9
  _BYTE *v71; // rdx
  unsigned int v72; // esi
  _BYTE *v73; // rax
  unsigned int i; // ecx
  unsigned int v75; // ebx
  __int64 v76; // r12
  char *v77; // r13
  unsigned int v78; // r11d
  __int64 v79; // rbx
  char **v80; // rdi
  __int64 *v81; // r10
  char *v82; // r15
  unsigned int v83; // ecx
  __int64 v84; // rcx
  unsigned __int8 *v85; // rcx
  __int64 v86; // rax
  unsigned __int16 *v87; // r15
  char *v88; // rdi
  char *v89; // rbx
  char *v90; // r12
  char *v91; // r10
  int v92; // ebx
  const char *v93; // r13
  const char *v94; // r14
  unsigned int v95; // edi
  int v96; // r9d
  unsigned int v97; // edx
  const char *v98; // r8
  __int64 v99; // rax
  void **v100; // rsi
  void **v101; // r15
  void **v102; // rdi
  void **v103; // rbx
  _QWORD **v104; // rdi
  _QWORD *v105; // rcx
  _QWORD *v106; // rax
  void **v107; // rcx
  __int64 v108; // r10
  unsigned __int8 *v109; // rcx
  __int64 v110; // r9
  __int64 v111; // r8
  __int64 v112; // rdx
  __int16 v113; // bx
  unsigned __int16 v114; // r15
  __int64 v115; // rax
  unsigned __int8 v116; // r13
  __int64 v117; // r12
  int v118; // r14d
  __int64 v119; // rsi
  __int64 *v120; // rdi
  unsigned int v121; // eax
  int v122; // eax
  int v123; // eax
  __int64 v124; // rdx
  int v125; // ecx
  __int64 v126; // rax
  __int64 v127; // r10
  __int64 v128; // r8
  int v129; // eax
  __int64 v130; // rax
  _QWORD *v131; // rdx
  __int64 v132; // rbx
  unsigned int v134; // r8d
  __int64 v135; // rcx
  unsigned __int64 v136; // rdx
  __int64 *v137; // rbx
  unsigned int v138; // r8d
  __int64 v139; // rcx
  __int64 v140; // r9
  int v141; // eax
  int v142; // eax
  _QWORD *v143; // rax
  _QWORD *v144; // rax
  __int64 v145; // rdx
  _QWORD *v146; // r8
  __int64 v147; // rcx
  int v148; // eax
  _QWORD **v149; // rsi
  _QWORD *v150; // rcx
  _QWORD *v151; // rax
  _QWORD *v152; // rax
  __int64 v153; // r8
  _QWORD *v154; // rdx
  _QWORD *v155; // rcx
  void **v156; // rax
  __int64 v157; // rcx
  bool v158; // di
  int v159; // eax
  _QWORD *v160; // rcx
  __int64 v161; // r8
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-A9h]
  int Priority; // [rsp+28h] [rbp-A1h]
  __int64 v164; // [rsp+50h] [rbp-79h]
  __int64 v165; // [rsp+58h] [rbp-71h]
  char *v166; // [rsp+60h] [rbp-69h]
  _QWORD *P; // [rsp+68h] [rbp-61h]
  int v168; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v169; // [rsp+74h] [rbp-55h] BYREF
  int v170; // [rsp+78h] [rbp-51h] BYREF
  __int128 v171; // [rsp+80h] [rbp-49h] BYREF
  __int128 v172; // [rsp+90h] [rbp-39h]
  __int64 v173; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v174; // [rsp+A8h] [rbp-21h] BYREF
  const char *v175; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v176; // [rsp+B8h] [rbp-11h] BYREF
  _OWORD v177[6]; // [rsp+C0h] [rbp-9h] BYREF
  unsigned __int16 *v178; // [rsp+130h] [rbp+67h] BYREF
  __int64 **v179; // [rsp+138h] [rbp+6Fh]
  char *v180; // [rsp+140h] [rbp+77h] BYREF
  struct _MDL *v181; // [rsp+148h] [rbp+7Fh] BYREF

  v179 = a2;
  v3 = *(_QWORD *)(a1 + 8);
  *a3 = 0;
  v164 = v3;
  v165 = *(_QWORD *)(v3 + 32);
  v171 = 0;
  v172 = 0;
  UxInitializeExbuffer(&v171, 1, 0xFFFFFFFFLL, 1448704085);
  v8 = (struct _MDL *)*a2;
  v9 = 0;
  LODWORD(v10) = *((_DWORD *)a2 + 4);
  v11 = 0;
  v12 = a2[1];
  if ( !v12 )
    goto LABEL_334;
  while ( 1 )
  {
    if ( !v8 )
    {
LABEL_333:
      v7 = v165;
LABEL_334:
      v76 = v164;
      if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
        WPP_SF_DD(
          14,
          WPP_bddeff2cdb6239d1dcf30a8be716afa8_Traceguids,
          *(unsigned int *)(v7 + 824),
          *(unsigned int *)(v164 + 72));
      CollectionHeaderValue = 0;
      *a3 = 1;
      goto LABEL_188;
    }
    if ( (v8->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v8->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000000u);
    if ( !MappedSystemVa )
    {
      v76 = v164;
      CollectionHeaderValue = -1073741670;
      v132 = v165;
      UxDuoSetFault(v165, v164, 27, 3221225626LL);
      goto LABEL_189;
    }
    v14 = &MappedSystemVa[(unsigned int)v10];
    v15 = v8->ByteCount - (_DWORD)v10;
    v10 = 0;
    if ( v15 )
      break;
LABEL_11:
    v8 = v8->Next;
    if ( !v12 )
      goto LABEL_333;
  }
  v16 = &v14[-v11];
  while ( 1 )
  {
    if ( !v12 )
      goto LABEL_11;
    v17 = (unsigned __int8)v16[v11];
    --v15;
    ++v11;
    v12 = (__int64 *)((char *)v12 - 1);
    v9 = (v9 << 8) | v17;
    if ( (_DWORD)v9 == 218762506 && v11 >= 4 )
      break;
    if ( !v15 )
      goto LABEL_11;
  }
  if ( *(_BYTE *)(a1 + 80) )
    v18 = 0;
  else
    v18 = *(_DWORD *)(a1 + 128);
  P = 0;
  PoolWithTagPriority = (char *)ExAllocatePoolWithTagPriority(PagedPool, 0x1C8u, 0x4E597855u, LowPoolPriority);
  v20 = PoolWithTagPriority;
  if ( !PoolWithTagPriority )
  {
    v22 = v164;
    CollectionHeaderValue = -1073741670;
    v21 = v165;
    UxDuoSetFault(v165, v164, 1000, 3221225626LL);
LABEL_229:
    if ( !*(_DWORD *)(v21 + 632) && !*(_DWORD *)(v22 + 208) )
      UxDuoSetFault(v21, 0, 1045, (unsigned int)CollectionHeaderValue);
    v76 = v164;
    goto LABEL_233;
  }
  memset(PoolWithTagPriority, 0, 0x1C8u);
  v21 = v165;
  *((_DWORD *)v20 + 22) = 2;
  *((_DWORD *)v20 + 17) = v18;
  *((_DWORD *)v20 + 8) = ++*(_DWORD *)(v165 + 832);
  if ( a1 != -112 )
    *(_OWORD *)(v20 + 72) = *(_OWORD *)(a1 + 112);
  if ( *((_DWORD *)v20 + 22) == 2 )
  {
    memset(v20 + 104, 0, 0x148u);
    *((_QWORD *)v20 + 13) = v20 + 96;
    *((_QWORD *)v20 + 12) = v20 + 96;
    *((_QWORD *)v20 + 15) = v20 + 112;
    *((_QWORD *)v20 + 14) = v20 + 112;
    *((_QWORD *)v20 + 17) = v20 + 128;
    *((_QWORD *)v20 + 16) = v20 + 128;
    *((_QWORD *)v20 + 19) = v20 + 144;
    *((_QWORD *)v20 + 18) = v20 + 144;
    *((_QWORD *)v20 + 21) = v20 + 160;
    *((_QWORD *)v20 + 20) = v20 + 160;
    *((_QWORD *)v20 + 23) = v20 + 176;
    *((_QWORD *)v20 + 22) = v20 + 176;
    *((_QWORD *)v20 + 25) = v20 + 192;
    *((_QWORD *)v20 + 24) = v20 + 192;
    *((_QWORD *)v20 + 27) = v20 + 208;
    *((_QWORD *)v20 + 26) = v20 + 208;
    *((_QWORD *)v20 + 29) = v20 + 224;
    *((_QWORD *)v20 + 28) = v20 + 224;
    *((_QWORD *)v20 + 31) = v20 + 240;
    *((_QWORD *)v20 + 30) = v20 + 240;
    *((_QWORD *)v20 + 33) = v20 + 256;
    *((_QWORD *)v20 + 32) = v20 + 256;
    *((_QWORD *)v20 + 35) = v20 + 272;
    *((_QWORD *)v20 + 34) = v20 + 272;
    *((_QWORD *)v20 + 37) = v20 + 288;
    *((_QWORD *)v20 + 36) = v20 + 288;
    *((_QWORD *)v20 + 39) = v20 + 304;
    *((_QWORD *)v20 + 38) = v20 + 304;
    *((_QWORD *)v20 + 41) = v20 + 320;
    *((_QWORD *)v20 + 40) = v20 + 320;
    *((_QWORD *)v20 + 43) = v20 + 336;
    *((_QWORD *)v20 + 42) = v20 + 336;
    *((_QWORD *)v20 + 45) = v20 + 352;
    *((_QWORD *)v20 + 44) = v20 + 352;
  }
  else if ( *((_DWORD *)v20 + 22) == 3 )
  {
    UxDuoInitializeCollection(v20 + 96);
  }
  v22 = v164;
  Task = UxDuoAllocateTask(12, v164, v165, (unsigned int)UxDuoExecuteParcelCompletion, (__int64)(v20 + 24));
  CollectionHeaderValue = Task;
  if ( Task < 0 )
  {
    UxDuoSetFault(v165, v164, 1000, (unsigned int)Task);
    UxDuoFreeParcel(v20);
  }
  else
  {
    v10 = v20;
    P = v20;
    *(_QWORD *)(*((_QWORD *)v20 + 3) + 48LL) = v20;
  }
  if ( CollectionHeaderValue < 0 )
    goto LABEL_229;
  *((_QWORD *)v10 + 56) = a1;
  _InterlockedIncrement((volatile signed __int32 *)a1);
  v25 = v179;
  v26 = 0;
  v27 = v172;
  v28 = 0;
  v29 = v179[1];
  v30 = *((_DWORD *)v179 + 4);
  v31 = (struct _MDL *)*v179;
  LODWORD(v180) = v30;
  if ( !v29 )
    goto LABEL_240;
  do
  {
    if ( !v31 )
    {
LABEL_244:
      v34 = 3221226021LL;
      CollectionHeaderValue = -1073741275;
      goto LABEL_246;
    }
    if ( (v31->MdlFlags & 5) != 0 )
    {
      v32 = (char *)v31->MappedSystemVa;
    }
    else
    {
      v32 = (char *)MmMapLockedPagesSpecifyCache(v31, 0, MmCached, 0, 0, 0x40000000u);
      v30 = (int)v180;
    }
    if ( !v32 )
    {
      v34 = 3221225626LL;
      CollectionHeaderValue = -1073741670;
      goto LABEL_246;
    }
    ByteCount = v31->ByteCount;
    v34 = 0;
    v31 = v31->Next;
    v35 = &v32[v30];
    v36 = ByteCount - v30;
    v30 = 0;
    LODWORD(v180) = 0;
    if ( !v36 )
      continue;
    v37 = &v35[-v28];
    do
    {
      if ( !v29 )
        goto LABEL_239;
      v29 = (__int64 *)((char *)v29 - 1);
      --v36;
      v26 = (unsigned __int8)v37[v28++] | (unsigned __int16)(v26 << 8);
      if ( v28 > 0x100000 )
        goto LABEL_244;
      if ( v28 )
      {
        LOBYTE(v178) = v26;
        if ( v27 >= DWORD2(v171) )
        {
          v142 = UxAppendToExbuffer(&v171, &v178, 1);
          v27 = v172;
          v34 = (unsigned int)v142;
          if ( v142 < 0 )
          {
            v25 = v179;
            goto LABEL_44;
          }
        }
        else
        {
          v38 = v27++;
          LODWORD(v172) = v27;
          v34 = 0;
          *(_BYTE *)(v38 + v171) = v26;
        }
      }
      if ( v26 == 3338 && v28 >= 2 )
      {
        v25 = v179;
        v39 = v28 + *((unsigned int *)v179 + 4);
        if ( v39 )
        {
          v40 = *v179;
          do
          {
            v41 = *((unsigned int *)v40 + 10);
            if ( v39 < v41 )
              break;
            v40 = (__int64 *)*v40;
            *v25 = v40;
            v39 -= v41;
          }
          while ( v39 );
        }
        v25[1] = (__int64 *)((char *)v25[1] - v28);
        *((_DWORD *)v25 + 4) = v39;
        goto LABEL_44;
      }
    }
    while ( v36 );
    v30 = (int)v180;
  }
  while ( v29 );
LABEL_239:
  v25 = v179;
LABEL_240:
  v34 = 3221226021LL;
LABEL_44:
  CollectionHeaderValue = v34;
  if ( (int)v34 < 0 )
  {
LABEL_246:
    v161 = 27;
    goto LABEL_247;
  }
  if ( v27 < 9 )
    goto LABEL_245;
  v42 = (_BYTE *)v171;
  v43 = *(_QWORD *)v171 - 0x312E312F50545448LL;
  if ( *(_QWORD *)v171 == 0x312E312F50545448LL )
    v43 = *(unsigned __int8 *)(v171 + 8) - 32LL;
  if ( v43 )
  {
LABEL_245:
    CollectionHeaderValue = -1073741585;
    v34 = 3221225711LL;
    goto LABEL_246;
  }
  v44 = v27 - 9;
  if ( v27 - 9 < 3 )
  {
    CollectionHeaderValue = -1073741584;
    v34 = 3221225712LL;
    goto LABEL_246;
  }
  v45 = v165;
  v46 = (_BYTE *)(v171 + 12);
  v166 = (char *)(P + 12);
  v47 = v44 - 3;
  v48 = UxDuoAddToCollection(P + 12, *(_QWORD *)(v165 + 872), ":status", 7, v171 + 9, 3);
  CollectionHeaderValue = v48;
  if ( v48 < 0 )
  {
LABEL_254:
    v76 = v164;
    v34 = (unsigned int)v48;
    v161 = 2;
    v147 = v45;
    goto LABEL_252;
  }
  v49 = v47;
  if ( v47 >= 2 )
  {
    v50 = v46;
    do
    {
      if ( *v46 == 13 && v46[1] == 10 )
        break;
      --v47;
      v46 = v50 + 1;
      v49 = v47;
      ++v50;
    }
    while ( v47 >= 2 );
  }
  if ( v49 < 2 )
  {
    CollectionHeaderValue = -1073741583;
LABEL_250:
    v161 = 27;
    goto LABEL_251;
  }
  if ( v49 != 2 )
  {
    CollectionHeaderValue = -1073741582;
    goto LABEL_250;
  }
  while ( 1 )
  {
    v51 = v25[1];
    v52 = 0;
    v53 = (struct _MDL *)*v25;
    v54 = 0;
    v55 = *((_DWORD *)v25 + 4);
    v56 = 0;
    LODWORD(v172) = 0;
    v181 = v53;
    LODWORD(v178) = v55;
    if ( !v51 )
      goto LABEL_260;
    do
    {
      if ( !v53 )
      {
LABEL_264:
        v34 = 3221226021LL;
        goto LABEL_262;
      }
      if ( (v53->MdlFlags & 5) != 0 )
      {
        v57 = (char *)v53->MappedSystemVa;
      }
      else
      {
        v57 = (char *)MmMapLockedPagesSpecifyCache(v53, 0, MmCached, 0, 0, 0x40000000u);
        v53 = v181;
        v55 = (int)v178;
      }
      if ( !v57 )
      {
        v34 = 3221225626LL;
LABEL_262:
        CollectionHeaderValue = v34;
LABEL_263:
        v161 = 28;
        goto LABEL_247;
      }
      v58 = v53->ByteCount;
      v34 = 0;
      v53 = v53->Next;
      v59 = &v57[v55];
      v181 = v53;
      v60 = v58 - v55;
      v55 = 0;
      LODWORD(v178) = 0;
      if ( !v60 )
        continue;
      v61 = &v59[-v56];
      do
      {
        if ( !v51 )
          goto LABEL_259;
        v51 = (__int64 *)((char *)v51 - 1);
        --v60;
        v54 = (unsigned __int8)v61[v56++] | (unsigned __int16)(v54 << 8);
        if ( v56 > 0x100000 )
          goto LABEL_264;
        if ( v56 )
        {
          LOBYTE(v180) = v54;
          if ( v52 >= DWORD2(v171) )
          {
            v148 = UxAppendToExbuffer(&v171, &v180, 1);
            v52 = v172;
            v34 = (unsigned int)v148;
            v42 = (_BYTE *)v171;
            if ( v148 < 0 )
            {
              v25 = v179;
              goto LABEL_79;
            }
          }
          else
          {
            v62 = v52++;
            LODWORD(v172) = v52;
            v34 = 0;
            v42[v62] = v54;
          }
        }
        if ( v54 == 3338 && v56 >= 2 )
        {
          v25 = v179;
          v63 = v56 + *((unsigned int *)v179 + 4);
          if ( v63 )
          {
            v64 = *v179;
            do
            {
              v65 = *((unsigned int *)v64 + 10);
              if ( v63 < v65 )
                break;
              v64 = (__int64 *)*v64;
              *v25 = v64;
              v63 -= v65;
            }
            while ( v63 );
          }
          v25[1] = (__int64 *)((char *)v25[1] - v56);
          *((_DWORD *)v25 + 4) = v63;
          goto LABEL_79;
        }
      }
      while ( v60 );
      v53 = v181;
      v55 = (int)v178;
    }
    while ( v51 );
LABEL_259:
    v25 = v179;
LABEL_260:
    v34 = 3221226021LL;
LABEL_79:
    CollectionHeaderValue = v34;
    if ( (int)v34 < 0 )
      goto LABEL_263;
    v66 = v42;
    if ( v52 == 2 && *v42 == 13 && v42[1] == 10 )
      break;
    if ( !v52 )
      goto LABEL_331;
    v67 = v42;
    do
    {
      v68 = (int)v67;
      v69 = v67;
      if ( *v66 == 58 )
        break;
      v66 = v67 + 1;
      v67 = v66;
      v68 = (int)v66;
      v69 = v66;
      --v52;
    }
    while ( v52 );
    if ( !v52 )
    {
LABEL_331:
      CollectionHeaderValue = -1073741585;
      v161 = 28;
      v34 = 3221225711LL;
      goto LABEL_247;
    }
    v70 = (unsigned int)(v68 - v171);
    v71 = v69 + 1;
    v72 = v52 - 1;
    v73 = v71;
    for ( i = v72; v72 >= 2; i = --v72 )
    {
      if ( *v73 == 13 && v73[1] == 10 )
        break;
      ++v73;
    }
    if ( i < 2 )
    {
      CollectionHeaderValue = -1073741584;
      v161 = 28;
      v34 = 3221225712LL;
      goto LABEL_247;
    }
    v45 = v165;
    v75 = i - 2;
    v48 = UxDuoAddToCollection(v166, *(_QWORD *)(v165 + 872), v42, v70, v71, (int)v73 - (int)v71);
    CollectionHeaderValue = v48;
    if ( v48 < 0 )
      goto LABEL_254;
    if ( v75 )
    {
      CollectionHeaderValue = -1073741583;
      v161 = 28;
LABEL_251:
      v76 = v164;
      v34 = (unsigned int)CollectionHeaderValue;
      v147 = v45;
      goto LABEL_252;
    }
  }
  v76 = v164;
  v77 = (char *)(P + 12);
  CollectionHeaderValue = 0;
  LODWORD(v179) = 0;
  v78 = 0;
  LODWORD(v181) = 0;
  v79 = 0x400000000002401LL;
  v173 = *(_QWORD *)(v164 + 32);
  v80 = (char **)(P + 14);
  v178 = *(unsigned __int16 **)(v173 + 872);
  while ( 1 )
  {
    v81 = (__int64 *)*v80;
    v82 = &v166[16 * v78 + 16];
    if ( *v80 != v82 )
      break;
LABEL_102:
    ++v78;
    v80 += 2;
    if ( v78 >= 0x10 )
    {
      v83 = (unsigned int)v179;
      goto LABEL_104;
    }
  }
  while ( 1 )
  {
    v134 = *((_DWORD *)v81 + 10);
    if ( !v134 )
    {
      v83 = 13;
      CollectionHeaderValue = -1073741811;
      goto LABEL_266;
    }
    if ( v81 != (__int64 *)P[46]
      && v81 != (__int64 *)P[47]
      && v81 != (__int64 *)P[49]
      && v81 != (__int64 *)P[50]
      && v81 != (__int64 *)P[48] )
    {
      v135 = 0;
      while ( 1 )
      {
        v136 = *(char *)(v135 + v81[4]);
        if ( (unsigned __int8)v136 <= 0x3Au )
        {
          if ( _bittest64(&v79, v136) )
            break;
        }
        v135 = (unsigned int)(v135 + 1);
        if ( (unsigned int)v135 >= v134 )
          goto LABEL_201;
      }
      v83 = 42;
      CollectionHeaderValue = -1073741811;
LABEL_266:
      UxDuoSetFault(v173, v76, v83, (unsigned int)CollectionHeaderValue);
      goto LABEL_151;
    }
LABEL_201:
    v137 = (__int64 *)v81[2];
    if ( v137 != v81 + 2 )
      break;
LABEL_208:
    v81 = (__int64 *)*v81;
    v79 = 0x400000000002401LL;
    if ( v81 == (__int64 *)v82 )
      goto LABEL_102;
  }
  while ( 1 )
  {
    v138 = *((_DWORD *)v137 + 12);
    v139 = 0;
    if ( v138 )
      break;
LABEL_207:
    v137 = (__int64 *)*v137;
    if ( v137 == v81 + 2 )
      goto LABEL_208;
  }
  v140 = v137[5];
  while ( 1 )
  {
    if ( *(_BYTE *)(v139 + v140) <= 0xDu )
    {
      v141 = 9217;
      if ( _bittest(&v141, *(char *)(v139 + v140)) )
        break;
    }
    v139 = (unsigned int)(v139 + 1);
    if ( (unsigned int)v139 >= v138 )
      goto LABEL_207;
  }
  v83 = 43;
  CollectionHeaderValue = -1073741811;
  LODWORD(v179) = 43;
  LODWORD(v181) = 43;
LABEL_104:
  if ( CollectionHeaderValue < 0 )
    goto LABEL_150;
  v84 = P[50];
  v174 = 0;
  CollectionHeaderValue = UxDuoGetCollectionHeaderValue(v84, &v174);
  if ( CollectionHeaderValue < 0 )
  {
    v83 = 47;
    LODWORD(v179) = 47;
    LODWORD(v181) = 47;
  }
  else if ( *(_DWORD *)(v174 + 48) == 3
         && (v85 = *(unsigned __int8 **)(v174 + 40), v86 = *v85, (_BYTE)v86 != 48)
         && (HttpChars[v86] & 8) != 0
         && (HttpChars[v85[1]] & 8) != 0
         && (HttpChars[v85[2]] & 8) != 0 )
  {
    v83 = (unsigned int)v179;
  }
  else
  {
    v83 = 47;
    CollectionHeaderValue = -1073741585;
    LODWORD(v179) = 47;
    LODWORD(v181) = 47;
  }
  if ( CollectionHeaderValue < 0 )
    goto LABEL_150;
  v87 = v178;
  CollectionHeaderValue = 0;
  v88 = &v166[16
            * (((413293
               * (1020325190 * v178[3043]
                + 1920165909 * v178[3033]
                + 10201 * (v178[3037] + 101 * (v178[3048] + 101 * v178[3031]))
                - 26381115 * v178[3031]
                - 1070170857 * (unsigned int)v178[3042])
               + 12345) >> 16)
             & 0xF)
            + 16];
  v89 = *(char **)v88;
  if ( *(char **)v88 == v88 )
  {
LABEL_302:
    v83 = (unsigned int)v179;
LABEL_303:
    if ( CollectionHeaderValue >= 0 )
      goto LABEL_141;
    goto LABEL_150;
  }
  while ( *((_DWORD *)v89 + 10) != 10 || _strnicmp(*((const char **)v89 + 4), "connection", 0xAu) )
  {
    v89 = *(char **)v89;
    if ( v89 == v88 )
      goto LABEL_302;
  }
  v90 = (char *)*((_QWORD *)v89 + 2);
  v91 = v89 + 16;
  v180 = v89 + 16;
  if ( v90 == v89 + 16 )
    goto LABEL_133;
  do
  {
    v92 = *((_DWORD *)v90 + 12);
    v93 = (const char *)*((_QWORD *)v90 + 5);
    if ( !v92 )
      goto LABEL_131;
    while ( 1 )
    {
      v94 = v93;
      v95 = 0;
      do
      {
        if ( (HttpChars[*(unsigned __int8 *)v94] & 0x100) == 0 )
          break;
        ++v94;
        ++v95;
        --v92;
      }
      while ( v92 );
      if ( !v95 )
      {
        v76 = v164;
        v83 = 45;
        CollectionHeaderValue = -1073741585;
        goto LABEL_266;
      }
      for ( ; v92; --v92 )
      {
        if ( (HttpChars[*(unsigned __int8 *)v94] & 0x20) == 0 )
          break;
        ++v94;
      }
      if ( v95 == 7 )
      {
        if ( !_strnicmp(":method", v93, 7u) || !_strnicmp(":scheme", v93, 7u) || !_strnicmp(":status", v93, 7u) )
        {
LABEL_277:
          v76 = v164;
          v83 = 45;
          CollectionHeaderValue = -1073741790;
          goto LABEL_266;
        }
      }
      else if ( v95 == 5 )
      {
        if ( !_strnicmp(":path", v93, 5u) )
          goto LABEL_277;
      }
      else if ( v95 == 10 && !_strnicmp(":authority", v93, 0xAu) )
      {
        goto LABEL_277;
      }
      v96 = 0;
      v97 = v95;
      v98 = v93;
      do
      {
        v99 = *(unsigned __int8 *)v98++;
        v96 = v87[v99 + 2932] + 101 * v96;
        --v97;
      }
      while ( v97 );
      v100 = (void **)&v166[16 * (((unsigned int)(413293 * v96 + 12345) >> 16) & 0xF) + 16];
      v101 = (void **)*v100;
      if ( *v100 != v100 )
      {
        while ( *((_DWORD *)v101 + 10) != v95 || _strnicmp((const char *)v101[4], v93, v95) )
        {
          v101 = (void **)*v101;
          if ( v101 == v100 )
            goto LABEL_129;
        }
        v149 = (_QWORD **)(v101 + 2);
        while ( 1 )
        {
          v150 = *v149;
          if ( *v149 == v149 )
            break;
          if ( (_QWORD **)v150[1] != v149 )
            goto LABEL_213;
          v151 = (_QWORD *)*v150;
          if ( *(_QWORD **)(*v150 + 8LL) != v150 )
            goto LABEL_213;
          *v149 = v151;
          v151[1] = v149;
          v152 = v150 + 2;
          *v150 = 0;
          v150[1] = 0;
          v153 = v150[2];
          if ( *(_QWORD **)(v153 + 8) != v150 + 2 )
            goto LABEL_213;
          v154 = (_QWORD *)v150[3];
          if ( (_QWORD *)*v154 != v152 )
            goto LABEL_213;
          *v154 = v153;
          *(_QWORD *)(v153 + 8) = v154;
          *v152 = 0;
          v150[3] = 0;
          ExFreePoolWithTag(v150, 0);
        }
        UxDuoUpdateCollectionFastHeaderLookup(v166, v93, v95);
        v155 = *v101;
        if ( *((void ***)*v101 + 1) != v101 )
          goto LABEL_213;
        v156 = (void **)v101[1];
        if ( *v156 != v101 )
          goto LABEL_213;
        *v156 = v155;
        v155[1] = v156;
        *v101 = 0;
        v101[1] = 0;
        ExFreePoolWithTag(v101, 0);
      }
LABEL_129:
      if ( !v92 )
        break;
      if ( *v94 != 44 )
      {
        v76 = v164;
        v83 = 45;
        CollectionHeaderValue = -1073741584;
        goto LABEL_266;
      }
      v175 = v94 + 1;
      v168 = v92 - 1;
      UxDuoParseCollectionSpace(&v175, &v168, v98);
      v92 = v168;
      if ( !v168 )
      {
        v76 = v164;
        v83 = 45;
        CollectionHeaderValue = -1073741583;
        goto LABEL_266;
      }
      v93 = v175;
      v87 = v178;
    }
    v91 = v180;
    v87 = v178;
LABEL_131:
    v90 = *(char **)v90;
  }
  while ( v90 != v91 );
  v77 = (char *)(P + 12);
LABEL_133:
  v102 = (void **)&v77[16
                     * (((413293
                        * (1020325190 * v87[3043]
                         + 1920165909 * v87[3033]
                         + 10201 * (v87[3037] + 101 * (v87[3048] + 101 * v87[3031]))
                         - 26381115 * v87[3031]
                         - 1070170857 * (unsigned int)v87[3042])
                        + 12345) >> 16)
                      & 0xF)
                     + 16];
  v103 = (void **)*v102;
  if ( *v102 == v102 )
  {
LABEL_301:
    v76 = v164;
    v83 = 45;
    LODWORD(v179) = 45;
    CollectionHeaderValue = -1073741275;
    LODWORD(v181) = 45;
    goto LABEL_303;
  }
  while ( *((_DWORD *)v103 + 10) != 10 || _strnicmp((const char *)v103[4], "connection", 0xAu) )
  {
    v103 = (void **)*v103;
    if ( v103 == v102 )
      goto LABEL_301;
  }
  v104 = (_QWORD **)(v103 + 2);
  while ( 1 )
  {
    v105 = *v104;
    if ( *v104 == v104 )
      break;
    if ( (_QWORD **)v105[1] != v104 )
      goto LABEL_213;
    v143 = (_QWORD *)*v105;
    if ( *(_QWORD **)(*v105 + 8LL) != v105 )
      goto LABEL_213;
    *v104 = v143;
    v143[1] = v104;
    v144 = v105 + 2;
    *v105 = 0;
    v105[1] = 0;
    v145 = v105[2];
    if ( *(_QWORD **)(v145 + 8) != v105 + 2 )
      goto LABEL_213;
    v146 = (_QWORD *)v105[3];
    if ( (_QWORD *)*v146 != v144 )
      goto LABEL_213;
    *v146 = v145;
    *(_QWORD *)(v145 + 8) = v146;
    *v144 = 0;
    v105[3] = 0;
    ExFreePoolWithTag(v105, 0);
  }
  UxDuoUpdateCollectionFastHeaderLookup(v77, "connection", 10);
  v106 = *v103;
  if ( *((void ***)*v103 + 1) != v103 )
    goto LABEL_213;
  v107 = (void **)v103[1];
  if ( *v107 != v103 )
    goto LABEL_213;
  *v107 = v106;
  v106[1] = v107;
  *v103 = 0;
  v103[1] = 0;
  ExFreePoolWithTag(v103, 0);
  v76 = v164;
LABEL_141:
  memset(v177, 0, 32);
  UxInitializeExbuffer(v177, 1, 0xFFFFFFFFLL, 1465481301);
  UxTerminateExbuffer(v177);
  v169 = 0;
  CollectionHeaderValue = UxDuoParseCollectionTransferEncoding(v77, &v169);
  if ( CollectionHeaderValue < 0 )
  {
    v83 = 36;
    LODWORD(v181) = 36;
  }
  else if ( v169 > 1 )
  {
    v83 = 37;
    CollectionHeaderValue = -1073741637;
    LODWORD(v181) = 37;
  }
  else
  {
    v83 = (unsigned int)v179;
  }
  if ( CollectionHeaderValue >= 0 )
  {
    CollectionHeaderValue = UxDuoSanitizeCollectionAuthentication(v77, v87, 1, &v181);
    if ( CollectionHeaderValue >= 0 )
    {
      CollectionHeaderValue = UxDuoSanitizeCollectionUpgrade(v77, v87, 1, &v181);
      if ( CollectionHeaderValue >= 0 )
      {
        CollectionHeaderValue = UxDuoSanitizeCollectionKeepAlive(v77, v87, 1, &v181);
        if ( CollectionHeaderValue >= 0 )
          CollectionHeaderValue = UxDuoSanitizeCollectionProxyConnection(v77, v87, 1, &v181);
      }
    }
    v83 = (unsigned int)v181;
  }
LABEL_150:
  if ( v83 )
    goto LABEL_266;
LABEL_151:
  if ( CollectionHeaderValue < 0 )
  {
    v157 = *(_QWORD *)(v76 + 32);
    if ( !*(_DWORD *)(v157 + 632) && !*(_DWORD *)(v76 + 208) )
      UxDuoSetFault(v157, 0, 1045, (unsigned int)CollectionHeaderValue);
    goto LABEL_233;
  }
  v176 = 0;
  if ( (int)UxDuoGetCollectionHeaderValue(P[50], &v176) < 0
    || *(_DWORD *)(v176 + 48) != 3
    || (v109 = *(unsigned __int8 **)(v176 + 40), v110 = *v109, (HttpChars[v110] & 8) == 0)
    || (v111 = v109[1], (HttpChars[v111] & 8) == 0)
    || (v112 = v109[2], (HttpChars[v112] & 8) == 0)
    || (v113 = (char)v112 + 10 * ((char)v111 + 10 * (char)v110) - 5328,
        v114 = (char)v112 + 10 * ((char)v111 + 10 * (char)v110) - 5428,
        v114 > 0x383u) )
  {
    CollectionHeaderValue = -1073741581;
    v161 = 27;
    v34 = 3221225715LL;
    goto LABEL_248;
  }
  v115 = *(_QWORD *)(v108 + 424);
  v116 = 0;
  v173 = 0;
  v34 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  if ( !v115 )
  {
LABEL_165:
    CollectionHeaderValue = v34;
    if ( (int)v34 < 0 )
      goto LABEL_315;
    v170 = 0;
    v123 = UxDuoParseCollectionTransferEncoding(v166, &v170);
    CollectionHeaderValue = v123;
    if ( v123 < 0 )
    {
      v34 = (unsigned int)v123;
      v161 = 24;
      goto LABEL_247;
    }
    v158 = v170 != 0;
    if ( v170 )
    {
      v159 = UxDuoRemoveNameFromCollection(v166, *(_QWORD *)(v165 + 872), "Transfer-Encoding", 17);
      CollectionHeaderValue = v159;
      if ( v159 < 0 )
      {
        v34 = (unsigned int)v159;
        v161 = 26;
        goto LABEL_247;
      }
    }
    v76 = v164;
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
    {
      LOWORD(Priority) = v113;
      BugCheckOnFailure[0] = *(_DWORD *)(v164 + 328);
      WPP_SF_DDLHllI(
        v158,
        v124,
        *(unsigned int *)(v165 + 824),
        *(unsigned int *)(v164 + 72),
        *(_QWORD *)BugCheckOnFailure,
        Priority,
        v158,
        v116,
        v119);
    }
    v125 = *(_DWORD *)(v164 + 328);
    if ( v125 == 10 )
    {
      v124 = 199;
      if ( (unsigned __int16)(v113 - 400) > 0xC7u )
      {
        CollectionHeaderValue = -1073741637;
        v161 = 29;
        v34 = 3221225659LL;
        goto LABEL_248;
      }
    }
    if ( v114 <= 0x63u )
    {
      UxDuoSetResponseTransformerState(v164, 0);
    }
    else if ( v125 == 5 || v113 == 204 || v113 == 304 )
    {
      *(_WORD *)(v164 + 440) = v113;
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x4000000) != 0 )
      {
        BugCheckOnFailure[0] = *(_DWORD *)(v164 + 368);
        WPP_SF_DDLL(
          *(_QWORD *)(v164 + 32),
          v124,
          *(unsigned int *)(*(_QWORD *)(v164 + 32) + 824LL),
          *(unsigned int *)(v164 + 72),
          *(_QWORD *)BugCheckOnFailure,
          6);
      }
      *(_DWORD *)(v164 + 368) = 6;
    }
    else if ( v158 )
    {
      *(_WORD *)(v164 + 440) = v113;
      UxDuoSetResponseTransformerState(v164, 2);
    }
    else if ( v116 && v119 )
    {
      *(_WORD *)(v164 + 440) = v113;
      *(_QWORD *)(v164 + 408) = v119;
      *(_QWORD *)(v164 + 416) = v119;
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x4000000) != 0 )
      {
        BugCheckOnFailure[0] = *(_DWORD *)(v164 + 368);
        WPP_SF_DDLL(
          *(_QWORD *)(v164 + 32),
          v124,
          *(unsigned int *)(*(_QWORD *)(v164 + 32) + 824LL),
          *(unsigned int *)(v164 + 72),
          *(_QWORD *)BugCheckOnFailure,
          1);
      }
      *(_DWORD *)(v164 + 368) = 1;
    }
    else
    {
      *(_WORD *)(v164 + 440) = v113;
      UxDuoSetResponseTransformerState(v164, 5);
    }
    v126 = P[3];
    v127 = *(_QWORD *)(v126 + 32);
    v128 = *(_QWORD *)(v126 + 24);
    v129 = *((_DWORD *)P + 22);
    *((_BYTE *)P + 64) = 1;
    *((_DWORD *)P + 9) = 1;
    if ( v129 != 2 )
    {
      switch ( v129 )
      {
        case 0:
        case 3:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        case 10:
        case 11:
          v130 = v127 + 584;
          v160 = *(_QWORD **)(v127 + 592);
          if ( *v160 != v127 + 584 )
            goto LABEL_213;
          *P = v130;
          P[1] = v160;
          *v160 = P;
          break;
        case 1:
        case 4:
          goto LABEL_182;
        default:
          goto LABEL_185;
      }
      goto LABEL_184;
    }
LABEL_182:
    v130 = v128 + 248;
    v131 = *(_QWORD **)(v128 + 256);
    if ( *v131 == v128 + 248 )
    {
      *P = v130;
      P[1] = v131;
      *v131 = P;
LABEL_184:
      *(_QWORD *)(v130 + 8) = P;
LABEL_185:
      if ( v128 )
      {
        if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
        {
          BugCheckOnFailure[0] = *((_DWORD *)P + 8);
          WPP_SF_DDDL(
            20,
            WPP_a61fa22a7b2635c08b9a89a383806988_Traceguids,
            *(unsigned int *)(v127 + 824),
            *(unsigned int *)(v128 + 72),
            *(_QWORD *)BugCheckOnFailure,
            *((_DWORD *)P + 22));
        }
      }
      else if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
      {
        WPP_SF_DLd(
          21,
          WPP_a61fa22a7b2635c08b9a89a383806988_Traceguids,
          *(unsigned int *)(v127 + 824),
          *((unsigned int *)P + 8),
          *((_DWORD *)P + 22));
      }
      goto LABEL_188;
    }
LABEL_213:
    __fastfail(3u);
  }
  v120 = *(__int64 **)(v115 + 16);
  if ( v120 == (__int64 *)(v115 + 16) )
  {
LABEL_164:
    v116 = 1;
    v119 = v117;
    goto LABEL_165;
  }
  while ( 1 )
  {
    v121 = *((_DWORD *)v120 + 12);
    if ( v121 > 0xFFFF )
      break;
    LOBYTE(v34) = 1;
    v122 = HttpStringToULongLong(0, v120[5], (unsigned __int16)v121, v34, 10, 0, (__int64)&v173);
    v34 = (unsigned int)v122;
    if ( v122 < 0 )
      goto LABEL_165;
    if ( v118 && v173 != v117 )
    {
      CollectionHeaderValue = -1073741182;
      v34 = 3221226114LL;
      goto LABEL_315;
    }
    v120 = (__int64 *)*v120;
    v117 = v173;
    ++v118;
    if ( v120 == (__int64 *)(P[53] + 16LL) )
      goto LABEL_164;
  }
  CollectionHeaderValue = -1073741675;
  v34 = 3221225621LL;
LABEL_315:
  v161 = 25;
LABEL_247:
  v76 = v164;
LABEL_248:
  v147 = v165;
LABEL_252:
  UxDuoSetFault(v147, v76, v161, v34);
LABEL_233:
  if ( P )
    UxDuoFreeParcel(P);
LABEL_188:
  v132 = v165;
LABEL_189:
  UxTerminateExbuffer(&v171);
  if ( CollectionHeaderValue < 0 && !*(_DWORD *)(v132 + 632) && !*(_DWORD *)(v76 + 208) )
    UxDuoSetFault(v132, 0, 1045, (unsigned int)CollectionHeaderValue);
  return (unsigned int)CollectionHeaderValue;
}

```

## disassembly

```asm
0x1c00b9a60  mov     [rsp-8+arg_8], rdx
0x1c00b9a65  push    rbp
0x1c00b9a66  push    rbx
0x1c00b9a67  push    rsi
0x1c00b9a68  push    rdi
0x1c00b9a69  push    r12
0x1c00b9a6b  push    r13
0x1c00b9a6d  push    r14
0x1c00b9a6f  push    r15
0x1c00b9a71  lea     rbp, [rsp-1Fh]
0x1c00b9a76  sub     rsp, 0E8h
0x1c00b9a7d  mov     rax, [rcx+8]
0x1c00b9a81  xorps   xmm0, xmm0
0x1c00b9a84  mov     byte ptr [r8], 0
0x1c00b9a88  mov     r13, r8
0x1c00b9a8b  mov     rsi, rdx
0x1c00b9a8e  mov     [rbp+57h+var_D0], rax
0x1c00b9a92  mov     r15, rcx
0x1c00b9a95  mov     edx, 1
0x1c00b9a9a  mov     r10, [rax+20h]
0x1c00b9a9e  lea     rcx, [rbp+57h+var_A0]
0x1c00b9aa2  mov     r9d, 56597855h
0x1c00b9aa8  mov     [rbp+57h+var_C8], r10
0x1c00b9aac  mov     r8d, 0FFFFFFFFh
0x1c00b9ab2  movups  [rbp+57h+var_A0], xmm0
0x1c00b9ab6  movups  [rbp+57h+var_90], xmm0
0x1c00b9aba  call    UxInitializeExbuffer
0x1c00b9abf  mov     r14, [rsi]
0x1c00b9ac2  xor     ebx, ebx
0x1c00b9ac4  mov     r12d, [rsi+10h]
0x1c00b9ac8  xor     edi, edi
0x1c00b9aca  mov     rsi, [rsi+8]
0x1c00b9ace  test    rsi, rsi
0x1c00b9ad1  jz      loc_1C00EBA63
0x1c00b9ad7  test    r14, r14
0x1c00b9ada  jz      loc_1C00EBA5F
0x1c00b9ae0  test    byte ptr [r14+0Ah], 5
0x1c00b9ae5  jz      loc_1C00BA999
0x1c00b9aeb  mov     rax, [r14+18h]
0x1c00b9aef  test    rax, rax
0x1c00b9af2  jz      loc_1C00EBA37
0x1c00b9af8  mov     ecx, [r14+28h]
0x1c00b9afc  mov     edx, r12d
0x1c00b9aff  add     rdx, rax
0x1c00b9b02  sub     ecx, r12d
0x1c00b9b05  mov     r12d, 0
0x1c00b9b0b  jz      short loc_1C00B9B36
0x1c00b9b0d  sub     rdx, rdi
0x1c00b9b10  test    rsi, rsi
0x1c00b9b13  jz      short loc_1C00B9B36
0x1c00b9b15  movzx   eax, byte ptr [rdx+rdi]
0x1c00b9b19  dec     ecx
0x1c00b9b1b  shl     rbx, 8
0x1c00b9b1f  inc     rdi
0x1c00b9b22  or      rax, rbx
0x1c00b9b25  dec     rsi
0x1c00b9b28  mov     rbx, rax
0x1c00b9b2b  cmp     eax, 0D0A0D0Ah
0x1c00b9b30  jz      short loc_1C00B9B43
0x1c00b9b32  test    ecx, ecx
0x1c00b9b34  jnz     short loc_1C00B9B10
0x1c00b9b36  mov     r14, [r14]
0x1c00b9b39  test    rsi, rsi
0x1c00b9b3c  jnz     short loc_1C00B9AD7
0x1c00b9b3e  jmp     loc_1C00EBA5F
0x1c00b9b43  cmp     rdi, 4
0x1c00b9b47  jb      short loc_1C00B9B32
0x1c00b9b49  cmp     [r15+50h], r12b
0x1c00b9b4d  jz      loc_1C00EB29E
0x1c00b9b53  xor     esi, esi
0x1c00b9b55  xor     r9d, r9d; Priority
0x1c00b9b58  mov     [rbp+57h+P], r12
0x1c00b9b5c  mov     edx, 1C8h; NumberOfBytes
0x1c00b9b61  lea     rbx, [r15+70h]
0x1c00b9b65  mov     r8d, 4E597855h; Tag
0x1c00b9b6b  lea     ecx, [r9+1]; PoolType
0x1c00b9b6f  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00b9b76  nop     dword ptr [rax+rax+00h]
0x1c00b9b7b  mov     rdi, rax
0x1c00b9b7e  test    rax, rax
0x1c00b9b81  jz      loc_1C00EB2AA
0x1c00b9b87  xor     edx, edx; Val
0x1c00b9b89  mov     r8d, 1C8h; Size
0x1c00b9b8f  mov     rcx, rax; void *
0x1c00b9b92  call    memset
0x1c00b9b97  mov     r13, [rbp+57h+var_C8]
0x1c00b9b9b  mov     dword ptr [rdi+58h], 2
0x1c00b9ba2  mov     [rdi+44h], esi
0x1c00b9ba5  inc     dword ptr [r13+340h]
0x1c00b9bac  mov     eax, [r13+340h]
0x1c00b9bb3  mov     [rdi+20h], eax
0x1c00b9bb6  test    rbx, rbx
0x1c00b9bb9  jz      short loc_1C00B9BC2
0x1c00b9bbb  movups  xmm0, xmmword ptr [rbx]
0x1c00b9bbe  movups  xmmword ptr [rdi+48h], xmm0
0x1c00b9bc2  mov     ecx, [rdi+58h]
0x1c00b9bc5  sub     ecx, 2
0x1c00b9bc8  jnz     loc_1C00EB31A
0x1c00b9bce  lea     rcx, [rdi+68h]; void *
0x1c00b9bd2  xor     edx, edx; Val
0x1c00b9bd4  mov     r8d, 148h; Size
0x1c00b9bda  lea     rbx, [rdi+60h]
0x1c00b9bde  call    memset
0x1c00b9be3  mov     [rbx+8], rbx
0x1c00b9be7  lea     rax, [rbx+10h]
0x1c00b9beb  mov     [rbx], rbx
0x1c00b9bee  mov     [rax+8], rax
0x1c00b9bf2  mov     [rax], rax
0x1c00b9bf5  add     rax, 10h
0x1c00b9bf9  mov     [rax+8], rax
0x1c00b9bfd  mov     [rax], rax
0x1c00b9c00  lea     rax, [rbx+30h]
0x1c00b9c04  mov     [rax+8], rax
0x1c00b9c08  mov     [rax], rax
0x1c00b9c0b  lea     rax, [rbx+40h]
0x1c00b9c0f  mov     [rax+8], rax
0x1c00b9c13  mov     [rax], rax
0x1c00b9c16  lea     rax, [rbx+50h]
0x1c00b9c1a  mov     [rax+8], rax
0x1c00b9c1e  mov     [rax], rax
0x1c00b9c21  lea     rax, [rbx+60h]
0x1c00b9c25  mov     [rax+8], rax
0x1c00b9c29  mov     [rax], rax
0x1c00b9c2c  lea     rax, [rbx+70h]
0x1c00b9c30  mov     [rax+8], rax
0x1c00b9c34  mov     [rax], rax
0x1c00b9c37  lea     rax, [rbx+80h]
0x1c00b9c3e  mov     [rax+8], rax
0x1c00b9c42  mov     [rax], rax
0x1c00b9c45  lea     rax, [rbx+90h]
0x1c00b9c4c  mov     [rax+8], rax
0x1c00b9c50  mov     [rax], rax
0x1c00b9c53  lea     rax, [rbx+0A0h]
0x1c00b9c5a  mov     [rax+8], rax
0x1c00b9c5e  mov     [rax], rax
0x1c00b9c61  lea     rax, [rbx+0B0h]
0x1c00b9c68  mov     [rax+8], rax
0x1c00b9c6c  mov     [rax], rax
0x1c00b9c6f  lea     rax, [rbx+0C0h]
0x1c00b9c76  mov     [rax+8], rax
0x1c00b9c7a  mov     [rax], rax
0x1c00b9c7d  lea     rax, [rbx+0D0h]
0x1c00b9c84  mov     [rax+8], rax
0x1c00b9c88  mov     [rax], rax
0x1c00b9c8b  lea     rax, [rbx+0E0h]
0x1c00b9c92  mov     [rax+8], rax
0x1c00b9c96  mov     [rax], rax
0x1c00b9c99  lea     rax, [rbx+0F0h]
0x1c00b9ca0  mov     [rax+8], rax
0x1c00b9ca4  mov     [rax], rax
0x1c00b9ca7  lea     rax, [rbx+100h]
0x1c00b9cae  mov     [rax+8], rax
0x1c00b9cb2  mov     [rax], rax
0x1c00b9cb5  mov     rsi, [rbp+57h+var_D0]
0x1c00b9cb9  lea     rbx, [rdi+18h]
0x1c00b9cbd  mov     rdx, rsi
0x1c00b9cc0  mov     qword ptr [rsp+120h+BugCheckOnFailure], rbx
0x1c00b9cc5  lea     r9, UxDuoExecuteParcelCompletion
0x1c00b9ccc  mov     r8, r13
0x1c00b9ccf  mov     ecx, 0Ch
0x1c00b9cd4  call    UxDuoAllocateTask
0x1c00b9cd9  mov     r14d, eax
0x1c00b9cdc  test    eax, eax
0x1c00b9cde  js      loc_1C00EB332
0x1c00b9ce4  mov     rax, [rbx]
0x1c00b9ce7  mov     r12, rdi
0x1c00b9cea  mov     [rbp+57h+P], rdi
0x1c00b9cee  mov     [rax+30h], rdi
0x1c00b9cf2  test    r14d, r14d
0x1c00b9cf5  js      loc_1C00EB2CC
0x1c00b9cfb  mov     [r12+1C0h], r15
0x1c00b9d03  lock inc dword ptr [r15]
0x1c00b9d07  mov     r12, [rbp+57h+arg_8]
0x1c00b9d0b  xor     ebx, ebx
0x1c00b9d0d  mov     esi, dword ptr [rbp+57h+var_90]
0x1c00b9d10  xor     edi, edi
0x1c00b9d12  mov     r15, [r12+8]
0x1c00b9d17  mov     ecx, [r12+10h]
0x1c00b9d1c  mov     r13, [r12]
0x1c00b9d20  mov     dword ptr [rbp+57h+arg_10], ecx
0x1c00b9d23  test    r15, r15
0x1c00b9d26  jz      loc_1C00EB364
0x1c00b9d2c  test    r13, r13
0x1c00b9d2f  jz      loc_1C00EB398
0x1c00b9d35  test    byte ptr [r13+0Ah], 5
0x1c00b9d3a  jz      loc_1C00BA9E8
0x1c00b9d40  mov     rax, [r13+18h]
0x1c00b9d44  test    rax, rax
0x1c00b9d47  jz      loc_1C00EB38D
0x1c00b9d4d  mov     r14d, [r13+28h]
0x1c00b9d51  xor     r9d, r9d
0x1c00b9d54  mov     r13, [r13+0]
0x1c00b9d58  mov     r12d, ecx
0x1c00b9d5b  add     r12, rax
0x1c00b9d5e  sub     r14d, ecx
0x1c00b9d61  mov     ecx, r9d
0x1c00b9d64  mov     dword ptr [rbp+57h+arg_10], ecx
0x1c00b9d67  jz      loc_1C00EB357
0x1c00b9d6d  sub     r12, rdi
0x1c00b9d70  test    r15, r15
0x1c00b9d73  jz      loc_1C00EB360
0x1c00b9d79  movzx   eax, byte ptr [r12+rdi]
0x1c00b9d7e  dec     r15
0x1c00b9d81  shl     rbx, 8
0x1c00b9d85  dec     r14d
0x1c00b9d88  or      rbx, rax
0x1c00b9d8b  inc     rdi
0x1c00b9d8e  cmp     rdi, 100000h
0x1c00b9d95  ja      loc_1C00EB398
0x1c00b9d9b  test    rdi, rdi
0x1c00b9d9e  jz      short loc_1C00B9DBD
0x1c00b9da0  mov     byte ptr [rbp+57h+arg_0], bl
0x1c00b9da3  cmp     esi, dword ptr [rbp+57h+var_A0+8]
0x1c00b9da6  jnb     loc_1C00BA962
0x1c00b9dac  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1c00b9db0  mov     eax, esi
0x1c00b9db2  inc     esi
0x1c00b9db4  mov     dword ptr [rbp+57h+var_90], esi
0x1c00b9db7  xor     r9d, r9d
0x1c00b9dba  mov     [rax+rcx], bl
0x1c00b9dbd  cmp     bx, 0D0Ah
0x1c00b9dc2  jz      short loc_1C00B9DCE
0x1c00b9dc4  test    r14d, r14d
0x1c00b9dc7  jnz     short loc_1C00B9D70
0x1c00b9dc9  jmp     loc_1C00EB354
0x1c00b9dce  cmp     rdi, 2
0x1c00b9dd2  jb      short loc_1C00B9DC4
0x1c00b9dd4  mov     r12, [rbp+57h+arg_8]
0x1c00b9dd8  mov     eax, [r12+10h]
0x1c00b9ddd  add     rax, rdi
0x1c00b9de0  jz      short loc_1C00B9DF2
0x1c00b9de2  mov     rdx, [r12]
0x1c00b9de6  mov     ecx, [rdx+28h]
0x1c00b9de9  cmp     rax, rcx
0x1c00b9dec  jnb     loc_1C00EB378
0x1c00b9df2  sub     [r12+8], rdi
0x1c00b9df7  mov     [r12+10h], eax
0x1c00b9dfc  mov     r14d, r9d
0x1c00b9dff  test    r9d, r9d
0x1c00b9e02  js      loc_1C00EB3AC
0x1c00b9e08  cmp     esi, 9
0x1c00b9e0b  jb      loc_1C00EB3A3
0x1c00b9e11  mov     r13, qword ptr [rbp+57h+var_A0]
0x1c00b9e15  mov     rax, 312E312F50545448h
0x1c00b9e1f  mov     rcx, [r13+0]
0x1c00b9e23  sub     rcx, rax
0x1c00b9e26  jnz     short loc_1C00B9E38
0x1c00b9e28  movzx   ecx, byte ptr [r13+8]
0x1c00b9e2d  mov     eax, 20h ; ' '
0x1c00b9e32  movzx   eax, al
0x1c00b9e35  sub     rcx, rax
0x1c00b9e38  test    rcx, rcx
0x1c00b9e3b  jnz     loc_1C00EB3A3
0x1c00b9e41  lea     edi, [rsi-9]
0x1c00b9e44  lea     rax, [r13+9]
0x1c00b9e48  cmp     edi, 3
0x1c00b9e4b  jb      loc_1C00EB3FB
0x1c00b9e51  mov     rsi, [rbp+57h+var_C8]
0x1c00b9e55  lea     r8, aStatus; ":status"
0x1c00b9e5c  mov     rcx, [rbp+57h+P]
0x1c00b9e60  lea     rbx, [rax+3]
0x1c00b9e64  add     rcx, 60h ; '`'
0x1c00b9e68  mov     [rsp+120h+Priority], 3
0x1c00b9e70  mov     r9d, 7
0x1c00b9e76  mov     [rbp+57h+var_C0], rcx
0x1c00b9e7a  mov     rdx, [rsi+368h]
0x1c00b9e81  add     edi, 0FFFFFFFDh
0x1c00b9e84  mov     qword ptr [rsp+120h+BugCheckOnFailure], rax
0x1c00b9e89  call    UxDuoAddToCollection
0x1c00b9e8e  mov     r14d, eax
0x1c00b9e91  test    eax, eax
0x1c00b9e93  js      loc_1C00EB406
0x1c00b9e99  mov     eax, edi
0x1c00b9e9b  cmp     edi, 2
0x1c00b9e9e  jb      short loc_1C00B9EC0
0x1c00b9ea0  mov     rcx, rbx
0x1c00b9ea3  cmp     byte ptr [rbx], 0Dh
0x1c00b9ea6  jz      short loc_1C00B9EBA
0x1c00b9ea8  dec     edi
0x1c00b9eaa  lea     rbx, [rcx+1]
0x1c00b9eae  mov     eax, edi
0x1c00b9eb0  mov     rcx, rbx
0x1c00b9eb3  cmp     edi, 2
0x1c00b9eb6  jnb     short loc_1C00B9EA3
0x1c00b9eb8  jmp     short loc_1C00B9EC0
0x1c00b9eba  cmp     byte ptr [rbx+1], 0Ah
0x1c00b9ebe  jnz     short loc_1C00B9EA8
0x1c00b9ec0  cmp     eax, 2
0x1c00b9ec3  jb      loc_1C00EB3D8
0x1c00b9ec9  add     eax, 0FFFFFFFEh
0x1c00b9ecc  jnz     loc_1C00EB418
0x1c00b9ed2  mov     r15, [r12+8]
0x1c00b9ed7  xor     esi, esi
0x1c00b9ed9  mov     rcx, [r12]; MemoryDescriptorList
0x1c00b9edd  xor     ebx, ebx
0x1c00b9edf  mov     edx, [r12+10h]
0x1c00b9ee4  xor     edi, edi
0x1c00b9ee6  mov     dword ptr [rbp+57h+var_90], esi
0x1c00b9ee9  mov     [rbp+57h+arg_18], rcx
0x1c00b9eed  mov     dword ptr [rbp+57h+arg_0], edx
  ... truncated ...
```
