# UlCreateCacheEntryFromResponse

- ea: `0x1400839e0`
- end: `0x14008472b`
- name: `UlCreateCacheEntryFromResponse`
- size: `3403`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400833a0`
- `0x1400cabfc`

## callees

- `0x14000a350`
- `0x140030e6c`
- `0x140034c80`
- `0x140035010`
- `0x1400839e0`
- `0x140084740`
- `0x140084aa0`
- `0x140084c00`
- `0x1400b3350`
- `0x1400d91d0`
- `0x1400e6e70`
- `0x1400fbe30`
- `0x1400fe930`
- `0x140167940`
- `0x1401c3cbc`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c84d4`
- `0x1401d2fe0`
- `0x1401d9c5c`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400841b0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400841b0`
- `ntoskrnl!_strnicmp` at `0x140084263`
- `ntoskrnl!_strnicmp` at `0x140084263`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008402e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008402e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140084022`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140084022`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140083f78`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140083f78`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140083f63`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140083f63`

## pseudocode

```c
__int64 __fastcall UlCreateCacheEntryFromResponse(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        char a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 v6; // r14
  unsigned __int16 v8; // r12
  __int64 v9; // r8
  __int64 v11; // r13
  __int64 v12; // r10
  int v13; // eax
  int v14; // esi
  __int64 v15; // rbp
  int LogDataCacheBufferSize; // r15d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r15
  int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r15
  unsigned int v24; // eax
  bool v25; // al
  unsigned int v26; // r13d
  char v27; // r15
  __int64 v28; // r12
  char *v29; // rax
  __int64 v30; // r10
  char *v31; // r12
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned __int64 v35; // r9
  char *v36; // rcx
  volatile signed __int32 **v37; // rcx
  volatile signed __int32 ***v38; // rdx
  volatile signed __int32 *v39; // rax
  volatile signed __int32 *v40; // rax
  __int64 *v42; // rcx
  volatile signed __int32 *v43; // rdx
  int v44; // eax
  int v45; // eax
  char *v46; // rdx
  __int64 v47; // rax
  char v48; // r8
  __int64 v49; // rax
  __int64 v50; // r10
  char v51; // al
  char v52; // r15
  char v53; // bl
  int v54; // ecx
  int BugCheckOnFailurea; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailure; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailureb; // [rsp+20h] [rbp-98h]
  int BugCheckOnFailurec; // [rsp+20h] [rbp-98h]
  unsigned int v59; // [rsp+50h] [rbp-68h]
  unsigned int v60; // [rsp+50h] [rbp-68h]
  __int64 P; // [rsp+58h] [rbp-60h]
  __int64 v62; // [rsp+60h] [rbp-58h]
  volatile signed __int32 *v63; // [rsp+68h] [rbp-50h] BYREF
  volatile signed __int32 ***v64; // [rsp+70h] [rbp-48h]
  char *v65; // [rsp+C0h] [rbp+8h] BYREF
  unsigned int v66; // [rsp+C8h] [rbp+10h]
  char v67; // [rsp+D8h] [rbp+20h]

  v67 = a4;
  v66 = a2;
  v6 = *(_QWORD *)(a1 + 24);
  v62 = 0;
  v8 = 0;
  LOWORD(v65) = 0;
  v9 = a2;
  v11 = a5;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    WPP_SF_qLLlqq((_DWORD)a6, a2, a2, a1, a2, a3, a4, a5, a6);
    v9 = v66;
  }
  v12 = *(_QWORD *)(a1 + 512);
  if ( v12 )
  {
    LogDataCacheBufferSize = UlGetLogDataCacheBufferSize(v12, &v65, v9);
    if ( LogDataCacheBufferSize < 0 )
      goto LABEL_65;
    v8 = (unsigned __int16)v65;
    LODWORD(v9) = v66;
    v62 = v50;
  }
  v13 = *(_DWORD *)(v6 + 1448);
  v14 = *(_DWORD *)(v6 + 2064);
  v15 = *(unsigned int *)(a1 + 716);
  if ( v13 == 3 || v13 == 2 )
  {
    LogDataCacheBufferSize = UlGenerateRoutingToken(v6, 2);
    if ( LogDataCacheBufferSize < 0 )
      goto LABEL_65;
    LODWORD(v9) = v66;
    v14 += *(unsigned __int16 *)(v6 + 2098) - 2 * ((__int64)(*(_QWORD *)(v6 + 2048) - *(_QWORD *)(v6 + 2032)) >> 1);
  }
  if ( *(unsigned int *)(a1 + 312)
     + *(unsigned int *)(a1 + 352)
     + (unsigned __int64)*(unsigned int *)(a1 + 396)
     + 24 * v15
     + 1
     + v8 > 0xFFFFFFFF )
  {
    LogDataCacheBufferSize = -1073741675;
    goto LABEL_65;
  }
  if ( (int)v9 + *(_DWORD *)(a1 + 168) < (unsigned int)v9 )
  {
    LogDataCacheBufferSize = -1073741675;
    goto LABEL_65;
  }
  LogDataCacheBufferSize = UlAllocateCacheEntry(
                             *(_QWORD *)(*(_QWORD *)(v6 + 24) + 1096LL),
                             v11,
                             (unsigned int)(v14 + 2));
  if ( LogDataCacheBufferSize < 0 )
    goto LABEL_65;
  v17 = *(unsigned int *)(v6 + 1984);
  v18 = *(unsigned int *)(v6 + 1448);
  v19 = v6 + 2032;
  LODWORD(v65) = *(_DWORD *)(v6 + 1984);
  v59 = v18;
  if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
  {
    WPP_SF_qlqLLq(v17, 137, v18, 0, 0, v6 + 2032, v18, v17, a1 + 408);
    v17 = (unsigned int)v65;
    v19 = v6 + 2032;
    v18 = v59;
  }
  MEMORY[0x20] = 1;
  MEMORY[0x28] = 0;
  MEMORY[0x30] = 0;
  MEMORY[0x78] = 0;
  MEMORY[0x229] = 0;
  MEMORY[0x70] = 0;
  MEMORY[0x40] = 0;
  MEMORY[0x50] = 0;
  MEMORY[0x60] = 0;
  MEMORY[0x270] = 616;
  MEMORY[0x268] = 616;
  v20 = MEMORY[8];
  if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
  {
    WPP_SF_qlqLLq(v17, 135, v18, MEMORY[8], 0, v19, v18, v17, a1 + 408);
    LODWORD(v17) = (_DWORD)v65;
    v18 = v59;
  }
  *(_DWORD *)(v20 + 104) = v17;
  BugCheckOnFailurea = *(_DWORD *)(v20 + 96);
  *(_WORD *)(v20 + 100) = 0;
  v21 = UlpBuildUriKeyFromCookedUrl(v6 + 2032, 0, v18, v20 + 224, BugCheckOnFailurea, v20 + 40);
  if ( v21 >= 0 && a1 != -408 )
  {
    *(_OWORD *)(v20 + 108) = *(_OWORD *)(a1 + 408);
    *(_OWORD *)(v20 + 124) = *(_OWORD *)(a1 + 424);
    *(_OWORD *)(v20 + 140) = *(_OWORD *)(a1 + 440);
    *(_OWORD *)(v20 + 156) = *(_OWORD *)(a1 + 456);
    *(_OWORD *)(v20 + 172) = *(_OWORD *)(a1 + 472);
    *(_OWORD *)(v20 + 188) = *(_OWORD *)(a1 + 488);
    *(_QWORD *)(v20 + 204) = *(_QWORD *)(a1 + 504);
  }
  LogDataCacheBufferSize = v21;
  if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
  {
    WPP_SF_d(1044, 136, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, (unsigned int)v21);
    if ( (BYTE2(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_d(1044, 138, WPP_2c21c4a9238032e513a9d7e299618fd0_Traceguids, (unsigned int)LogDataCacheBufferSize);
  }
  if ( LogDataCacheBufferSize < 0 )
  {
LABEL_65:
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 234, WPP_173ede4a325638307373c19033e5a27a_Traceguids, (unsigned int)LogDataCacheBufferSize);
    return (unsigned int)LogDataCacheBufferSize;
  }
  MEMORY[0x22B] = *(_BYTE *)(a1 + 49);
  v22 = *(_DWORD *)(a1 + 312);
  if ( v22 )
  {
    memmove((void *)0x2A0, *(const void **)(a1 + 320), v22);
    MEMORY[0xA0] = 672;
    MEMORY[0x98] = *(_DWORD *)(a1 + 312);
    v23 = *(unsigned int *)(a1 + 312) + 672LL;
    P = v23;
  }
  else
  {
    v23 = 672;
    P = 672;
    MEMORY[0xA0] = &cchOriginalDestLength;
  }
  if ( *(_DWORD *)(a1 + 352) )
  {
    memmove((void *)v23, *(const void **)(a1 + 360), *(unsigned int *)(a1 + 352));
    MEMORY[0xB0] = v23;
    MEMORY[0xA8] = *(_DWORD *)(a1 + 352);
    v23 += *(unsigned int *)(a1 + 352);
    P = v23;
  }
  else
  {
    MEMORY[0xB0] = &cchOriginalDestLength;
  }
  MEMORY[0xB8] = *(_DWORD *)(a1 + 392);
  v24 = *(_DWORD *)(a1 + 396);
  if ( v24 )
  {
    memmove((void *)v23, *(const void **)(a1 + 400), v24);
    MEMORY[0xC0] = v23;
    MEMORY[0xBC] = *(_DWORD *)(a1 + 396);
    *(_BYTE *)(MEMORY[0xBC] + v23) = 0;
    P = *(unsigned int *)(a1 + 396) + 1LL + v23;
  }
  else
  {
    MEMORY[0xC0] = &cchOriginalDestLength;
  }
  MEMORY[0x90] = *(_QWORD *)(a1 + 280);
  v25 = *(_BYTE *)(a1 + 40) || *(_BYTE *)(a1 + 43);
  MEMORY[0x72] = v25;
  MEMORY[0x74] = *(_WORD *)(a1 + 152);
  MEMORY[0x7C] = a3;
  MEMORY[0x22A] = v67;
  if ( (_DWORD)a3 == 2 )
    MEMORY[0x88] = MEMORY[0xFFFFF78000000014] + 10000000LL * MEMORY[0x80];
  UlCopyConfigGroupInfoForCache(v6 + 1296, 200);
  v26 = v66;
  MEMORY[0x200] = *(_DWORD *)(a1 + 168);
  MEMORY[0x218] = *(_DWORD *)(a1 + 236);
  MEMORY[0x21C] = *(_DWORD *)(a1 + 240);
  MEMORY[0x220] = *(_DWORD *)(a1 + 244);
  MEMORY[0x224] = *(_DWORD *)(a1 + 248);
  MEMORY[0x228] = *(_BYTE *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 148) & 0x20) != 0 && *(_WORD *)(a1 + 152) == 206 && v66 )
  {
    if ( *(_DWORD *)(a1 + 240) < 6u )
    {
      LogDataCacheBufferSize = -1073741811;
      goto LABEL_65;
    }
    LOBYTE(BugCheckOnFailure) = 0;
    v51 = UlLargeMemSetData(MEMORY[0x208], *(_QWORD *)(a1 + 192), *(unsigned int *)(a1 + 236), v66, BugCheckOnFailure);
    LOBYTE(BugCheckOnFailureb) = 0;
    v52 = v51;
    v53 = UlLargeMemSetData(MEMORY[0x208], "200 OK", 6, v26 + *(_DWORD *)(a1 + 236), BugCheckOnFailureb);
    LOBYTE(BugCheckOnFailurec) = 0;
    v27 = v53
        | UlLargeMemSetData(
            MEMORY[0x208],
            *(_QWORD *)(a1 + 192) + *(unsigned int *)(a1 + 236) + (unsigned __int64)*(unsigned int *)(a1 + 240),
            (unsigned int)(*(_DWORD *)(a1 + 168) - *(_DWORD *)(a1 + 240) - *(_DWORD *)(a1 + 236)),
            *(_DWORD *)(a1 + 236) + v26 + 6,
            BugCheckOnFailurec)
        | v52;
    v54 = *(_DWORD *)(a1 + 240) - 6;
    v60 = v54;
    MEMORY[0x200] = *(_DWORD *)(a1 + 168) - v54;
    MEMORY[0x218] = *(_DWORD *)(a1 + 236);
    MEMORY[0x21C] = 6;
    MEMORY[0x220] = *(_DWORD *)(a1 + 244) - v54;
    MEMORY[0x224] = *(_DWORD *)(a1 + 248);
    MEMORY[0x74] = 200;
  }
  else
  {
    v60 = 0;
    LOBYTE(BugCheckOnFailure) = 0;
    v27 = UlLargeMemSetData(MEMORY[0x208], *(_QWORD *)(a1 + 192), *(unsigned int *)(a1 + 168), v66, BugCheckOnFailure);
  }
  if ( !v27 )
  {
    LogDataCacheBufferSize = -1073741670;
    goto LABEL_65;
  }
  MEMORY[0x204] = v26;
  LogDataCacheBufferSize = 0;
  if ( *(_QWORD *)(v6 + 2480) )
    UlFlCopyFlowRateParamsToCache(0);
  if ( v62 )
  {
    LogDataCacheBufferSize = UlCopyLogDataToCache(0, v62, P, v8, &v65);
    if ( LogDataCacheBufferSize < 0 )
      goto LABEL_65;
    v28 = v8 + P;
  }
  else
  {
    v28 = P;
  }
  MEMORY[0x278] = 0;
  MEMORY[0x288] = 0;
  MEMORY[0x298] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 632, v28, v15);
  if ( (_DWORD)v15 )
  {
    MEMORY[0x278] = v28;
    MEMORY[0x288] = v15;
  }
  MEMORY[0x290] = 0xFFFFFFF;
  MEMORY[0x294] = 0xFFFFFFF;
  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
  if ( (*(_BYTE *)(MEMORY[0x208] + 10LL) & 5) != 0 )
    v29 = *(char **)(MEMORY[0x208] + 24LL);
  else
    v29 = (char *)MmMapLockedPagesSpecifyCache(MEMORY[0x208], 0, MmCached, 0, 0, 0x40000000u);
  v30 = v60;
  v31 = &v29[v26];
  v32 = 0;
  while ( (unsigned int)v32 < (unsigned int)v15 )
  {
    if ( *(_DWORD *)(a1 + 720) == (_DWORD)v32 )
    {
      v65 = &v31[MEMORY[0x218]];
      LogDataCacheBufferSize = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqLqd(
          1038,
          76,
          WPP_3bc569ebedc33674d1577199996181a5_Traceguids,
          632,
          ":status",
          7,
          &v31[MEMORY[0x218]],
          3);
      if ( MEMORY[0x280] >= MEMORY[0x288] )
      {
        LogDataCacheBufferSize = -1073741670;
      }
      else
      {
        v45 = _strnicmp(":status", ":status", 7u);
        v46 = v65;
        if ( v45 )
        {
          v48 = 0;
        }
        else
        {
          v47 = (unsigned __int8)*v65;
          if ( (_BYTE)v47 == 48
            || (HttpChars[v47] & 8) == 0
            || (HttpChars[(unsigned __int8)v65[1]] & 8) == 0
            || (HttpChars[(unsigned __int8)v65[2]] & 8) == 0 )
          {
            LogDataCacheBufferSize = -1073741811;
            goto LABEL_71;
          }
          v48 = 1;
        }
        *(_QWORD *)(MEMORY[0x278] + 24LL * MEMORY[0x280]) = ":status";
        *(_DWORD *)(MEMORY[0x278] + 24LL * MEMORY[0x280] + 16) = 7;
        *(_QWORD *)(MEMORY[0x278] + 24LL * MEMORY[0x280] + 8) = v46;
        *(_DWORD *)(MEMORY[0x278] + 24LL * MEMORY[0x280] + 20) = 3;
        if ( v48 )
          MEMORY[0x290] = MEMORY[0x280];
        ++MEMORY[0x280];
        MEMORY[0x298] += 10LL;
      }
LABEL_71:
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_d(1038, 77, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, (unsigned int)LogDataCacheBufferSize);
      if ( LogDataCacheBufferSize < 0 )
        goto LABEL_65;
      v30 = v60;
      v32 = (unsigned int)(v32 + 1);
    }
    else
    {
      v33 = MEMORY[0x278] + 24 * v32;
      v34 = *(_QWORD *)(a1 + 696) + 24 * v32;
      *(_DWORD *)(v33 + 16) = *(_DWORD *)(v34 + 16);
      v35 = *(_QWORD *)(a1 + 192);
      v36 = *(char **)v34;
      if ( *(_QWORD *)v34 >= v35 && (unsigned __int64)v36 < v35 + *(unsigned int *)(a1 + 168) )
        v36 = &v31[(unsigned int)((_DWORD)v36 - v35) - v30];
      *(_QWORD *)v33 = v36;
      *(_DWORD *)(v33 + 20) = *(_DWORD *)(v34 + 20);
      *(_QWORD *)(v33 + 8) = &v31[(unsigned int)(*(_DWORD *)(v34 + 8) - *(_DWORD *)(a1 + 192)) - v30];
      ++MEMORY[0x280];
      v32 = (unsigned int)(v32 + 1);
    }
  }
  MEMORY[0x28C] = v15;
  MEMORY[0x294] = *(_DWORD *)(a1 + 724);
  MEMORY[0x298] = *(_QWORD *)(a1 + 728);
  v63 = (volatile signed __int32 *)&v63;
  v64 = (volatile signed __int32 ***)&v63;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v6 )
      v49 = *(_QWORD *)(v6 + 64);
    else
      v49 = 0;
    WPP_SF_qqP(1032, 44, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v6, v49, 0);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6 + 2808, 0);
  v37 = (volatile signed __int32 **)(v6 + 2792);
  if ( *((volatile signed __int32 ***)v63 + 1) != &v63
    || (v38 = v64, *v64 != &v63)
    || *((volatile signed __int32 ***)*v37 + 1) != v37
    || **(volatile signed __int32 ****)(v6 + 2800) != v37
    || (*v64 = v37,
        v64 = *(volatile signed __int32 ****)(v6 + 2800),
        *v64 = &v63,
        v39 = *v37,
        *(_QWORD *)(v6 + 2800) = v38,
        *((volatile signed __int32 ***)v39 + 1) != v37)
    || *v38 != v37 )
  {
LABEL_75:
    __fastfail(3u);
  }
  *v38 = (volatile signed __int32 **)v39;
  *((_QWORD *)v39 + 1) = v38;
  *(_QWORD *)(v6 + 2800) = v6 + 2792;
  *v37 = (volatile signed __int32 *)v37;
  *(_BYTE *)(v6 + 2816) = 1;
  ExReleasePushLockExclusiveEx(v6 + 2808, 0);
  KeLeaveCriticalRegion();
  while ( 1 )
  {
    v40 = v63;
    if ( v63 == (volatile signed __int32 *)&v63 )
      break;
    if ( *((volatile signed __int32 ***)v63 + 1) != &v63 )
      goto LABEL_75;
    v42 = *(__int64 **)v63;
    if ( *(volatile signed __int32 **)(*(_QWORD *)v63 + 8LL) != v63 )
      goto LABEL_75;
    v63 = *(volatile signed __int32 **)v63;
    v42[1] = (__int64)&v63;
    *(_QWORD *)v40 = 0;
    v43 = v40 - 6;
    *((_QWORD *)v40 + 1) = 0;
    v44 = _InterlockedDecrement(v40 - 6);
    if ( UxDebugCheckRefcount && v44 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v43, 0x28u, v44);
    if ( !v44 )
      UxDuoFreeDeclarePushParameters((PVOID)v43);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 45, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  *a6 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    WPP_SF_q(1033, 233, WPP_173ede4a325638307373c19033e5a27a_Traceguids, 0);
    goto LABEL_65;
  }
  return (unsigned int)LogDataCacheBufferSize;
}

```

## disassembly

```asm
0x1400839e0  mov     [rsp+arg_18], r9b
0x1400839e5  mov     [rsp+arg_8], edx
0x1400839e9  push    rbx
0x1400839ea  push    rdi
0x1400839eb  push    r12
0x1400839ed  push    r13
0x1400839ef  push    r14
0x1400839f1  sub     rsp, 90h
0x1400839f8  mov     r14, [rcx+18h]
0x1400839fc  xor     eax, eax
0x1400839fe  mov     rbx, r8
0x140083a01  mov     [rsp+0B8h+P], rax
0x140083a06  mov     [rsp+0B8h+var_58], rax
0x140083a0b  mov     r12d, eax
0x140083a0e  mov     word ptr [rsp+0B8h+arg_0], ax
0x140083a16  mov     r8d, edx
0x140083a19  mov     rdi, rcx
0x140083a1c  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140083a23  mov     r13, [rsp+0B8h+arg_20]
0x140083a2b  jnz     loc_1400844E4
0x140083a31  mov     r10, [rdi+200h]
0x140083a38  mov     [rsp+0B8h+arg_10], rbp
0x140083a40  mov     [rsp+0B8h+var_30], rsi
0x140083a48  mov     [rsp+0B8h+var_38], r15
0x140083a50  test    r10, r10
0x140083a53  jnz     loc_14008451B
0x140083a59  mov     eax, [r14+5A8h]
0x140083a60  mov     esi, [r14+810h]
0x140083a67  mov     ebp, [rdi+2CCh]
0x140083a6d  cmp     eax, 3
0x140083a70  jz      loc_1400841C8
0x140083a76  cmp     eax, 2
0x140083a79  jz      loc_1400841C8
0x140083a7f  mov     eax, [rdi+160h]
0x140083a85  lea     rcx, ds:0[rbp*2]
0x140083a8d  mov     edx, [rdi+18Ch]
0x140083a93  add     rcx, rbp
0x140083a96  add     rdx, rax
0x140083a99  movzx   r9d, r12w
0x140083a9d  mov     eax, [rdi+138h]
0x140083aa3  add     rdx, rax
0x140083aa6  mov     eax, 0FFFFFFFFh
0x140083aab  lea     rdx, [rdx+rcx*8]
0x140083aaf  inc     rdx
0x140083ab2  add     r9, rdx
0x140083ab5  cmp     r9, rax
0x140083ab8  ja      loc_140084551
0x140083abe  mov     edx, [rdi+0A8h]
0x140083ac4  add     edx, r8d
0x140083ac7  cmp     edx, r8d
0x140083aca  jb      loc_14008455C
0x140083ad0  mov     rcx, [r14+18h]
0x140083ad4  lea     rax, [rsp+0B8h+P]
0x140083ad9  mov     qword ptr [rsp+0B8h+Priority], rax
0x140083ade  lea     r8d, [rsi+2]
0x140083ae2  mov     [rsp+0B8h+BugCheckOnFailure], edx
0x140083ae6  mov     rdx, r13
0x140083ae9  mov     rcx, [rcx+448h]
0x140083af0  call    UlAllocateCacheEntry
0x140083af5  mov     rsi, [rsp+0B8h+P]
0x140083afa  mov     r15d, eax
0x140083afd  test    eax, eax
0x140083aff  js      loc_140084094
0x140083b05  mov     ecx, [r14+7C0h]
0x140083b0c  lea     r13, [rdi+198h]
0x140083b13  mov     r8d, [r14+5A8h]
0x140083b1a  lea     r9, [r14+7F0h]
0x140083b21  mov     dword ptr [rsp+0B8h+arg_0], ecx
0x140083b28  mov     [rsp+0B8h+var_68], r8d
0x140083b2d  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x140083b34  jnz     loc_140084567
0x140083b3a  xor     r10d, r10d
0x140083b3d  mov     dword ptr [rsi+20h], 1
0x140083b44  mov     [rsi+28h], r10
0x140083b48  lea     rax, [rsi+268h]
0x140083b4f  mov     [rsi+30h], r10
0x140083b53  mov     [rsi+78h], r10d
0x140083b57  mov     [rsi+229h], r10b
0x140083b5e  mov     word ptr [rsi+70h], 0
0x140083b64  mov     [rsi+40h], r10
0x140083b68  mov     [rsi+50h], r10
0x140083b6c  mov     [rsi+60h], r10
0x140083b70  mov     [rax+8], rax
0x140083b74  mov     [rax], rax
0x140083b77  mov     r15, [rsi+8]
0x140083b7b  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x140083b82  jnz     loc_1400845A7
0x140083b88  lea     rax, [r15+28h]
0x140083b8c  mov     [r15+68h], ecx
0x140083b90  mov     qword ptr [rsp+0B8h+Priority], rax
0x140083b95  lea     r9, [r15+0E0h]
0x140083b9c  mov     eax, [r15+60h]
0x140083ba0  lea     rcx, [r14+7F0h]
0x140083ba7  xor     edx, edx
0x140083ba9  mov     [rsp+0B8h+BugCheckOnFailure], eax
0x140083bad  mov     word ptr [r15+64h], 0
0x140083bb4  call    UlpBuildUriKeyFromCookedUrl
0x140083bb9  test    eax, eax
0x140083bbb  js      short loc_140083C19
0x140083bbd  test    r13, r13
0x140083bc0  jz      short loc_140083C19
0x140083bc2  movups  xmm0, xmmword ptr [r13+0]
0x140083bc7  movups  xmmword ptr [r15+6Ch], xmm0
0x140083bcc  movups  xmm1, xmmword ptr [r13+10h]
0x140083bd1  movups  xmmword ptr [r15+7Ch], xmm1
0x140083bd6  movups  xmm0, xmmword ptr [r13+20h]
0x140083bdb  movups  xmmword ptr [r15+8Ch], xmm0
0x140083be3  movups  xmm1, xmmword ptr [r13+30h]
0x140083be8  movups  xmmword ptr [r15+9Ch], xmm1
0x140083bf0  movups  xmm0, xmmword ptr [r13+40h]
0x140083bf5  movups  xmmword ptr [r15+0ACh], xmm0
0x140083bfd  movups  xmm1, xmmword ptr [r13+50h]
0x140083c02  movups  xmmword ptr [r15+0BCh], xmm1
0x140083c0a  movsd   xmm0, qword ptr [r13+60h]
0x140083c10  movsd   qword ptr [r15+0CCh], xmm0
0x140083c19  test    byte ptr cs:xmmword_1401A2CA0+2, 10h
0x140083c20  mov     r15d, eax
0x140083c23  jnz     loc_1400845DD
0x140083c29  test    r15d, r15d
0x140083c2c  js      loc_140084094
0x140083c32  movzx   eax, byte ptr [rdi+31h]
0x140083c36  lea     r13, [rsi+2A0h]
0x140083c3d  mov     [rsi+22Bh], al
0x140083c43  lea     rcx, cchOriginalDestLength
0x140083c4a  mov     eax, [rdi+138h]
0x140083c50  test    eax, eax
0x140083c52  jz      loc_140084621
0x140083c58  mov     rdx, [rdi+140h]; Src
0x140083c5f  mov     r8d, eax; Size
0x140083c62  mov     rcx, r13; void *
0x140083c65  call    memmove
0x140083c6a  mov     [rsi+0A0h], r13
0x140083c71  lea     rcx, cchOriginalDestLength
0x140083c78  mov     eax, [rdi+138h]
0x140083c7e  mov     [rsi+98h], eax
0x140083c84  mov     r15d, [rdi+138h]
0x140083c8b  add     r15, r13
0x140083c8e  mov     [rsp+0B8h+P], r15
0x140083c93  mov     eax, [rdi+160h]
0x140083c99  test    eax, eax
0x140083c9b  jnz     loc_140084635
0x140083ca1  mov     [rsi+0B0h], rcx
0x140083ca8  mov     eax, [rdi+188h]
0x140083cae  mov     [rsi+0B8h], eax
0x140083cb4  mov     eax, [rdi+18Ch]
0x140083cba  test    eax, eax
0x140083cbc  jz      loc_140084189
0x140083cc2  mov     rdx, [rdi+190h]; Src
0x140083cc9  mov     r8d, eax; Size
0x140083ccc  mov     rcx, r15; void *
0x140083ccf  call    memmove
0x140083cd4  mov     [rsi+0C0h], r15
0x140083cdb  mov     eax, [rdi+18Ch]
0x140083ce1  mov     [rsi+0BCh], eax
0x140083ce7  mov     ecx, eax
0x140083ce9  mov     rax, [rsi+0C0h]
0x140083cf0  mov     byte ptr [rcx+rax], 0
0x140083cf4  mov     eax, [rdi+18Ch]
0x140083cfa  inc     rax
0x140083cfd  add     r15, rax
0x140083d00  mov     [rsp+0B8h+P], r15
0x140083d05  mov     rax, [rdi+118h]
0x140083d0c  mov     [rsi+90h], rax
0x140083d13  cmp     byte ptr [rdi+28h], 0
0x140083d17  jnz     loc_1400841C1
0x140083d1d  cmp     byte ptr [rdi+2Bh], 0
0x140083d21  jnz     loc_1400841C1
0x140083d27  xor     al, al
0x140083d29  mov     [rsi+72h], al
0x140083d2c  movzx   eax, word ptr [rdi+98h]
0x140083d33  mov     [rsi+74h], ax
0x140083d37  movzx   eax, [rsp+0B8h+arg_18]
0x140083d3f  mov     [rsi+7Ch], rbx
0x140083d43  mov     [rsi+22Ah], al
0x140083d49  cmp     ebx, 2
0x140083d4c  jz      loc_140084674
0x140083d52  lea     rdx, [rsi+0C8h]
0x140083d59  lea     rcx, [r14+510h]
0x140083d60  call    UlCopyConfigGroupInfoForCache
0x140083d65  mov     eax, [rdi+0A8h]
0x140083d6b  mov     r13d, [rsp+0B8h+arg_8]
0x140083d73  mov     [rsi+200h], eax
0x140083d79  mov     eax, [rdi+0ECh]
0x140083d7f  mov     [rsi+218h], eax
0x140083d85  mov     eax, [rdi+0F0h]
0x140083d8b  mov     [rsi+21Ch], eax
0x140083d91  mov     eax, [rdi+0F4h]
0x140083d97  mov     [rsi+220h], eax
0x140083d9d  mov     eax, [rdi+0F8h]
0x140083da3  mov     [rsi+224h], eax
0x140083da9  movzx   eax, byte ptr [rdi+0E8h]
0x140083db0  mov     [rsi+228h], al
0x140083db6  mov     eax, [rdi+94h]
0x140083dbc  test    al, 20h
0x140083dbe  jnz     loc_1400846A4
0x140083dc4  mov     r8d, [rdi+0A8h]
0x140083dcb  mov     r9d, r13d
0x140083dce  mov     rdx, [rdi+0C0h]
0x140083dd5  mov     rcx, [rsi+208h]
0x140083ddc  mov     [rsp+0B8h+var_68], 0
0x140083de4  mov     byte ptr [rsp+0B8h+BugCheckOnFailure], 0
0x140083de9  call    UlLargeMemSetData
0x140083dee  movzx   r15d, al
0x140083df2  test    r15b, r15b
0x140083df5  jz      loc_14008408E
0x140083dfb  mov     [rsi+204h], r13d
0x140083e02  xor     r15d, r15d
0x140083e05  mov     rdx, [r14+9B0h]
0x140083e0c  test    rdx, rdx
0x140083e0f  jnz     loc_1400846D7
0x140083e15  mov     rax, [rsp+0B8h+var_58]
0x140083e1a  test    rax, rax
0x140083e1d  jnz     loc_14008420C
0x140083e23  mov     r12, [rsp+0B8h+P]
0x140083e28  lea     rbx, [rsi+278h]
0x140083e2f  xorps   xmm0, xmm0
0x140083e32  movups  xmmword ptr [rbx], xmm0
0x140083e35  xor     eax, eax
0x140083e37  movups  xmmword ptr [rbx+10h], xmm0
0x140083e3b  mov     [rbx+20h], rax
0x140083e3f  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140083e46  jnz     loc_14008440C
0x140083e4c  test    ebp, ebp
0x140083e4e  jz      short loc_140083E56
0x140083e50  mov     [rbx], r12
0x140083e53  mov     [rbx+10h], ebp
0x140083e56  mov     dword ptr [rbx+18h], 0FFFFFFFh
0x140083e5d  mov     dword ptr [rbx+1Ch], 0FFFFFFFh
0x140083e64  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140083e6b  jnz     loc_14008429F
0x140083e71  mov     rcx, [rsi+208h]; MemoryDescriptorList
0x140083e78  test    byte ptr [rcx+0Ah], 5
0x140083e7c  jz      loc_140084195
0x140083e82  mov     rax, [rcx+18h]
0x140083e86  mov     r10d, [rsp+0B8h+var_68]
0x140083e8b  mov     r12d, r13d
0x140083e8e  add     r12, rax
0x140083e91  mov     [rsp+0B8h+var_58], r10
0x140083e96  xor     ebx, ebx
0x140083e98  lea     r9, aStatus; ":status"
0x140083e9f  cmp     ebx, ebp
0x140083ea1  jnb     short loc_140083F22
0x140083ea3  cmp     [rdi+2D0h], ebx
0x140083ea9  jz      loc_1400840D6
0x140083eaf  mov     rax, [rsi+278h]
0x140083eb6  lea     rcx, [rbx+rbx*2]
0x140083eba  lea     rdx, [rax+rcx*8]
0x140083ebe  mov     rax, [rdi+2B8h]
0x140083ec5  lea     r8, [rax+rcx*8]
0x140083ec9  mov     eax, [rax+rcx*8+10h]
0x140083ecd  mov     [rdx+10h], eax
0x140083ed0  mov     r9, [rdi+0C0h]
0x140083ed7  mov     rcx, [r8]
0x140083eda  cmp     rcx, r9
0x140083edd  jb      short loc_140083EED
0x140083edf  mov     eax, [rdi+0A8h]
0x140083ee5  add     rax, r9
0x140083ee8  cmp     rcx, rax
0x140083eeb  jb      short loc_140083F15
0x140083eed  mov     [rdx], rcx
0x140083ef0  mov     eax, [r8+14h]
0x140083ef4  mov     [rdx+14h], eax
0x140083ef7  mov     eax, [r8+8]
0x140083efb  sub     eax, [rdi+0C0h]
0x140083f01  sub     rax, r10
0x140083f04  add     rax, r12
0x140083f07  mov     [rdx+8], rax
0x140083f0b  inc     dword ptr [rsi+280h]
0x140083f11  inc     ebx
0x140083f13  jmp     short loc_140083E98
0x140083f15  sub     rcx, r9
0x140083f18  mov     ecx, ecx
0x140083f1a  sub     rcx, r10
0x140083f1d  add     rcx, r12
0x140083f20  jmp     short loc_140083EED
0x140083f22  mov     [rsi+28Ch], ebp
0x140083f28  mov     eax, [rdi+2D4h]
0x140083f2e  mov     [rsi+294h], eax
0x140083f34  mov     rax, [rdi+2D8h]
0x140083f3b  mov     [rsi+298h], rax
0x140083f42  lea     rax, [rsp+0B8h+var_50]
0x140083f47  mov     [rsp+0B8h+var_50], rax
0x140083f4c  lea     rax, [rsp+0B8h+var_50]
0x140083f51  mov     [rsp+0B8h+var_48], rax
0x140083f56  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140083f5d  jnz     loc_1400843D7
0x140083f63  call    cs:__imp_KeEnterCriticalRegion
0x140083f6a  nop     dword ptr [rax+rax+00h]
0x140083f6f  xor     edx, edx
0x140083f71  lea     rcx, [r14+0AF8h]
0x140083f78  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140083f7f  nop     dword ptr [rax+rax+00h]
0x140083f84  lea     rcx, [r14+0AE8h]
0x140083f8b  test    rsi, rsi
0x140083f8e  jnz     loc_140084340
0x140083f94  mov     rax, [rsp+0B8h+var_50]
0x140083f99  lea     rdx, [rsp+0B8h+var_50]
0x140083f9e  cmp     [rax+8], rdx
0x140083fa2  jnz     loc_14008412A
0x140083fa8  mov     rdx, [rsp+0B8h+var_48]
  ... truncated ...
```
