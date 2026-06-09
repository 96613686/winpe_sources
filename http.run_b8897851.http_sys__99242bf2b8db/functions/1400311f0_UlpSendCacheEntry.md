# UlpSendCacheEntry

- ea: `0x1400311f0`
- end: `0x140031dc5`
- name: `UlpSendCacheEntry`
- size: `3029`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002ebb0`
- `0x140032fd0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x140022610`
- `0x1400311f0`
- `0x140032180`
- `0x140048f00`
- `0x140049d28`
- `0x140051410`
- `0x14005fe50`
- `0x1400b1bac`
- `0x1400e879c`
- `0x14011ae98`
- `0x14011b304`
- `0x14011bdc0`
- `0x14011d45c`
- `0x140167700`
- `0x1401677e0`
- `0x140167840`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401ccecc`
- `0x1401d2b88`
- `0x1401d9e44`
- `0x1401da550`
- `0x1401da5a4`
- `0x1401da5dc`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400316c9`
- `ntoskrnl!IoBuildPartialMdl` at `0x140031814`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400316c9`
- `ntoskrnl!IoBuildPartialMdl` at `0x140031814`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140174d2b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140174d2b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003149f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003149f`
- `ntoskrnl!MmSizeOfMdl` at `0x140174b19`
- `ntoskrnl!MmSizeOfMdl` at `0x140174b3d`
- `ntoskrnl!MmSizeOfMdl` at `0x140174b19`
- `ntoskrnl!MmSizeOfMdl` at `0x140174b3d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140031b76`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140031b76`
- `ntoskrnl!ExAllocatePool3` at `0x140174bba`
- `ntoskrnl!ExAllocatePool3` at `0x140174bba`

## pseudocode

```c
__int64 __fastcall UlpSendCacheEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned int *a6)
{
  unsigned int *v6; // r12
  int v8; // edi
  __int64 v9; // rbx
  __int64 v10; // r14
  unsigned int v11; // r13d
  __int64 v12; // rax
  unsigned int v13; // r10d
  int *v14; // r9
  int v15; // r11d
  int v16; // r8d
  __int64 v17; // rax
  unsigned __int8 v18; // bl
  unsigned int v19; // eax
  unsigned __int32 v20; // eax
  unsigned __int32 v21; // ett
  __int16 v22; // ax
  __int64 v23; // r8
  SIZE_T v24; // rsi
  unsigned int v25; // ebx
  unsigned int v26; // edi
  int LockArray_high; // r13d
  unsigned __int64 v28; // rbx
  char *v29; // rax
  SIZE_T v30; // rdx
  int v31; // r9d
  char *v32; // rbx
  __int64 v33; // r12
  int v34; // esi
  int v35; // esi
  __int64 v36; // r12
  volatile signed __int32 *v37; // r12
  int v38; // eax
  void **v39; // rsi
  int VariableHeaders; // edi
  __int64 v41; // rsi
  __int64 v42; // r10
  __int64 v43; // r9
  unsigned __int64 v44; // rcx
  int v45; // edx
  __int64 v46; // rcx
  __int64 v47; // r9
  int v48; // eax
  __int64 v49; // r10
  __int64 v50; // r9
  unsigned __int64 v51; // r8
  int v52; // edx
  unsigned __int64 v53; // rcx
  int v54; // edx
  __int64 v55; // rax
  __int64 *v56; // rsi
  const char *v57; // rcx
  int v58; // r8d
  unsigned int v59; // r13d
  __int64 v60; // rdx
  ULONG_PTR v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rax
  int v64; // r13d
  bool v65; // sf
  __int64 v67; // rcx
  __int64 v68; // rbx
  USHORT CurrentNodeNumber; // ax
  SIZE_T v70; // r12
  unsigned __int64 v71; // rax
  __int64 Pool3; // rax
  int v73; // esi
  unsigned int v74; // esi
  __int64 v75; // rcx
  __int64 v76; // rcx
  SIZE_T v77; // rdi
  __int64 v78; // r12
  SIZE_T v79; // rdi
  __int64 v80; // r9
  __int64 v81; // r10
  __int64 v82; // r8
  __int64 RangeCacheTracker; // rax
  int v84; // eax
  __int64 v85; // r9
  __int64 v86; // rax
  __int64 v87; // [rsp+28h] [rbp-D8h]
  int v88; // [rsp+28h] [rbp-D8h]
  int v89; // [rsp+40h] [rbp-C0h]
  unsigned int v90; // [rsp+70h] [rbp-90h]
  int v91; // [rsp+70h] [rbp-90h]
  int v92; // [rsp+78h] [rbp-88h]
  const char *v93; // [rsp+78h] [rbp-88h]
  __int64 v94; // [rsp+88h] [rbp-78h] BYREF
  __int64 v95; // [rsp+90h] [rbp-70h]
  int v96[2]; // [rsp+98h] [rbp-68h]
  __int64 v97; // [rsp+A0h] [rbp-60h]
  __int64 v98; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v99; // [rsp+B0h] [rbp-50h]
  __int64 v100[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v101[24]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = a6;
  v98 = 0;
  v8 = a2;
  LODWORD(v94) = 0;
  v9 = a1;
  v97 = a4;
  v92 = a2;
  v99 = a1;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( a1 )
      v67 = *(_QWORD *)(a1 + 48);
    else
      LODWORD(v67) = 0;
    WPP_SF_qiLqqlq(v67, a2, a3, v9, v67, a2, a3, a4, a5);
    LODWORD(a4) = v97;
  }
  *a6 = 0;
  if ( (*(_DWORD *)(v9 + 632) & 2) == 0 )
  {
    v10 = *(_QWORD *)(v9 + 568);
    v11 = 0;
    if ( *(_BYTE *)(v10 + 3214) )
    {
      v11 = *(_DWORD *)(a3 + 640);
      if ( *(_DWORD *)(v10 + 2676) )
      {
        if ( !*(_BYTE *)(v10 + 2704) )
          v11 += 2;
      }
    }
    if ( *(_DWORD *)(v10 + 2676) > 1u && *(_WORD *)(a3 + 116) == 200 && !*(_BYTE *)(v10 + 2704) )
    {
      v32 = 0;
      VariableHeaders = UlSendMultiRangeFromFlatCache(a3, v10, v8, a4, (__int64)a6);
      v37 = (volatile signed __int32 *)(v10 + 48);
LABEL_108:
      v65 = VariableHeaders < 0;
      goto LABEL_109;
    }
    if ( *(_BYTE *)(a3 + 114)
      || ((v12 = *(_QWORD *)(a3 + 8)) == 0 ? (a2 = 0) : (a2 = *(unsigned int *)(v12 + 104)),
          (v8 & 2) != 0
       || (v8 & 0x40) != 0
       || (a1 = *(unsigned __int16 *)(a3 + 116), (unsigned __int16)(a1 - 100) <= 0x63u)
       || (_WORD)a1 == 204
       || (_WORD)a1 == 304
       || (_DWORD)a2 == 5) )
    {
      v101[0] = 0;
      v96[0] = 0;
    }
    else
    {
      v13 = *(_DWORD *)(a3 + 516);
      v14 = (int *)v101;
      LOBYTE(v100[0]) = 0;
      v15 = 1;
      do
      {
        v16 = v15;
        v17 = v15++;
        *((_BYTE *)v100 + v17) = v13 % 0xA + 48;
        v13 /= 0xAu;
        a2 = v13;
      }
      while ( v13 );
      for ( ; v16 >= 0; --v16 )
      {
        *(_BYTE *)v14 = *((_BYTE *)v100 + (unsigned int)v16);
        v14 = (int *)((char *)v14 + 1);
      }
      a1 = (_DWORD)v14 - 1 - (unsigned int)v101;
      *(_QWORD *)v96 = a1;
    }
    v18 = v8 & 1;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qqD(1033, 240, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v10, *(_QWORD *)(v10 + 64), v18);
    v19 = *(_DWORD *)(v10 + 2752);
    v90 = v19;
    if ( v19 == 3 )
    {
      _m_prefetchw((const void *)(v10 + 2208));
      v20 = *(_DWORD *)(v10 + 2208);
      do
      {
        a1 = v20;
        v21 = v20;
        v20 = _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 2208), v20, v20);
      }
      while ( v21 != v20 );
      if ( (v20 & 1) != 0 )
        goto LABEL_72;
      v22 = *(_WORD *)(v10 + 2112);
      if ( !v18 )
      {
        if ( v22 == 1 && !*(_WORD *)(v10 + 2114) )
        {
          v23 = 2;
          v90 = 2;
          goto LABEL_30;
        }
        goto LABEL_72;
      }
      if ( !v22 && *(_WORD *)(v10 + 2114) )
      {
LABEL_72:
        v23 = 0;
        v90 = 0;
        goto LABEL_30;
      }
      v23 = 1;
      v90 = 1;
    }
    else
    {
      v23 = v19;
    }
LABEL_30:
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 241, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, (unsigned int)v23);
    v24 = *(unsigned int *)(a3 + 516);
    v25 = *(_DWORD *)(a3 + 512);
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_LLlL(a1, a2, v23, v25, v24, a5, v11);
    if ( v11 )
      v11 += UlH3ExtraHeaderCount + 2;
    v26 = v25 + 177;
    if ( v25 + 177 > 0x200 || (unsigned int)v24 > 0x40000 || v11 > 0x14 )
    {
      v95 = (MmSizeOfMdl((PVOID)0xFFF, v26) + 7) & 0xFFFFFFF8;
      v70 = (MmSizeOfMdl((PVOID)0xFFF, v24) + 7) & 0xFFFFFFF8;
      v100[0] = 24LL * v11;
      v30 = v70 + (unsigned int)UlVariableHeadersMdlLength + 352LL;
      v71 = v26 + v95 + v30 + 2 * ((unsigned int)UlVariableHeaderSize + v100[0]);
      if ( v71 <= 0xFFFFFFFF )
      {
        Pool3 = ExAllocatePool3(66, (unsigned int)v71, 1094937685, UxLowPriorityPool, 1);
        v32 = (char *)Pool3;
        if ( Pool3 )
        {
          v73 = UlVariableHeaderSize;
          strcpy((char *)(Pool3 + 16), "UlCA");
          *(_QWORD *)(Pool3 + 136) = 0;
          *(_QWORD *)(Pool3 + 80) = 0;
          *(_QWORD *)(Pool3 + 128) = 0;
          v74 = v26 + v73;
          *(_QWORD *)(Pool3 + 144) = 0;
          *(_BYTE *)(Pool3 + 21) = a5;
          *(_DWORD *)(Pool3 + 152) = 0;
          *(_OWORD *)(Pool3 + 160) = 0;
          *(_DWORD *)(Pool3 + 176) = 0;
          memset((void *)(Pool3 + 272), 0, 0x50u);
          v75 = (__int64)&v32[v95 + 352];
          *((_QWORD *)v32 + 4) = 0;
          *((_QWORD *)v32 + 6) = 0;
          *((_QWORD *)v32 + 8) = 0;
          *((_QWORD *)v32 + 14) = v75;
          *((_QWORD *)v32 + 13) = v32 + 352;
          v76 = (unsigned int)UlVariableHeadersMdlLength + v75;
          *((_QWORD *)v32 + 15) = v76;
          v77 = v76 + v70;
          UlInitializeParsedHeaders(v32 + 192, v76 + v70, v11);
          v78 = v100[0];
          v79 = v100[0] + v77;
          UlInitializeParsedHeaders(v32 + 232, v79, v11);
          v80 = *((_QWORD *)v32 + 14);
          v81 = (unsigned int)UlVariableHeaderSize;
          *((_QWORD *)v32 + 23) = v79 + v78;
          *((_DWORD *)v32 + 45) = v74;
          *((_DWORD *)v32 + 22) = v81;
          v82 = v79 + v78 + v74;
          *((_QWORD *)v32 + 12) = v82;
          *(_QWORD *)v80 = 0;
          *(_WORD *)(v80 + 8) = 8
                              * ((((unsigned __int64)(((_WORD)v79 + (_WORD)v78 + (_WORD)v74) & 0xFFF) + v81 + 4095) >> 12)
                               + 6);
          *(_WORD *)(v80 + 10) = 0;
          *(_QWORD *)(v80 + 32) = v82 & 0xFFFFFFFFFFFFF000uLL;
          *(_DWORD *)(v80 + 44) = ((_WORD)v79 + (_WORD)v78 + (_WORD)v74) & 0xFFF;
          *(_DWORD *)(v80 + 40) = v81;
          MmBuildMdlForNonPagedPool(*((PMDL *)v32 + 14));
        }
      }
      else
      {
        v32 = 0;
      }
    }
    else
    {
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      if ( UxDebugDisableLookaside )
      {
        v29 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0210[0])(
                        (unsigned int)dword_1401A01F8,
                        qword_1401A0200,
                        (unsigned int)dword_1401A0208,
                        0);
      }
      else if ( UxCompactMode )
      {
        v68 = qword_1401A01F0;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        v29 = (char *)PplAllocateFromLookasideListProcessor(v68, CurrentNodeNumber);
      }
      else
      {
        v28 = qword_1401A01F0 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
        if ( !*(_BYTE *)(v28 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A01F0, v28 + 64);
        v29 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v28 + 64));
      }
      v32 = v29;
      if ( v29 )
      {
        *((_DWORD *)v29 + 4) = 1094937685;
        v29[21] = a5;
        *((_QWORD *)v29 + 17) = 0;
        *((_QWORD *)v29 + 10) = 0;
        *((_QWORD *)v29 + 16) = 0;
        *((_QWORD *)v29 + 18) = 0;
        *((_DWORD *)v29 + 38) = 0;
        *((_OWORD *)v29 + 10) = 0;
        *((_DWORD *)v29 + 44) = 0;
        v29[20] = 1;
        memset(v29 + 272, 0, 0x50u);
        *((_QWORD *)v32 + 4) = 0;
        *((_QWORD *)v32 + 6) = 0;
        *((_QWORD *)v32 + 8) = 0;
        v33 = *((_QWORD *)v32 + 24);
        v34 = *((_DWORD *)v32 + 52);
        *((_OWORD *)v32 + 12) = 0;
        *((_OWORD *)v32 + 13) = 0;
        *((_QWORD *)v32 + 28) = 0;
        if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
          WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v32 + 192, v33, v34);
        if ( v34 )
        {
          *((_QWORD *)v32 + 24) = v33;
          *((_DWORD *)v32 + 52) = v34;
        }
        *((_DWORD *)v32 + 54) = 0xFFFFFFF;
        *((_DWORD *)v32 + 55) = 0xFFFFFFF;
        if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
          WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
        v35 = *((_DWORD *)v32 + 62);
        v36 = *((_QWORD *)v32 + 29);
        *(_OWORD *)(v32 + 232) = 0;
        *(_OWORD *)(v32 + 248) = 0;
        *((_QWORD *)v32 + 33) = 0;
        if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
          WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v32 + 232, v36, v35);
        if ( v35 )
        {
          *((_QWORD *)v32 + 29) = v36;
          *((_DWORD *)v32 + 62) = v35;
        }
        *((_DWORD *)v32 + 64) = 0xFFFFFFF;
        *((_DWORD *)v32 + 65) = 0xFFFFFFF;
        if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
          WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
        *(_DWORD *)v32 = LockArray_high;
      }
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1033, 202, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v32);
    if ( !v32 )
    {
      VariableHeaders = -1073741670;
      goto LABEL_110;
    }
    v37 = (volatile signed __int32 *)(v10 + 48);
    v38 = _InterlockedIncrement((volatile signed __int32 *)(v10 + 48));
    if ( UxDebugCheckRefcount && v38 <= -1 )
      UlBugCheckEx(3u, v10 + 48, 0x22u, v38);
    v39 = 0;
    *((_DWORD *)v32 + 38) = v92;
    VariableHeaders = -1073741670;
    *((_QWORD *)v32 + 10) = a3;
    *((_QWORD *)v32 + 16) = v10;
    v95 = 0;
    if ( *(_BYTE *)(v10 + 3214) )
    {
      v39 = (void **)(v32 + 192);
      v95 = (__int64)(v32 + 192);
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qq(1038, 80, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v32 + 192, a3 + 632);
      v63 = *(unsigned int *)(a3 + 640);
      if ( *((_DWORD *)v32 + 52) < (unsigned int)v63 )
      {
        v64 = -1073741670;
      }
      else
      {
        memmove(*v39, *(const void **)(a3 + 632), 24 * v63);
        *((_DWORD *)v32 + 50) = *(_DWORD *)(a3 + 640);
        *((_DWORD *)v32 + 53) = *(_DWORD *)(a3 + 652);
        *((_DWORD *)v32 + 54) = *(_DWORD *)(a3 + 656);
        *((_DWORD *)v32 + 55) = *(_DWORD *)(a3 + 660);
        v64 = 0;
        *((_QWORD *)v32 + 28) = *(_QWORD *)(a3 + 664);
      }
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_d(1038, 81, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, (unsigned int)v64);
      if ( v64 < 0 )
      {
        VariableHeaders = v64;
        goto LABEL_68;
      }
    }
    if ( *(_DWORD *)(v10 + 2676) == 1 && *(_WORD *)(a3 + 116) == 200 && !*(_BYTE *)(v10 + 2704) )
    {
      LOBYTE(v31) = *(_BYTE *)(a3 + 552) == 0;
      RangeCacheTracker = UlFastCreateRangeCacheTracker(
                            *(_QWORD *)(v10 + 2680),
                            v30,
                            *(_DWORD *)(a3 + 516),
                            v31,
                            (__int64)v39);
      if ( !RangeCacheTracker )
      {
LABEL_68:
        v48 = _InterlockedDecrement(v37);
        if ( UxDebugCheckRefcount && v48 <= -1 )
          UlBugCheckEx(3u, (ULONG_PTR)v37, 0x22u, v48);
        if ( !v48 )
          UlpQueueFreeHttpRequest(v10);
        UlFreeCacheTracker(v32);
        goto LABEL_110;
      }
      *((_QWORD *)v32 + 18) = RangeCacheTracker;
      if ( *(_BYTE *)(v10 + 3214) )
      {
        v84 = UlBuildParsedHeaderFastRangeResponse(v32, a3, v90, v10, a6);
      }
      else
      {
        v87 = *(_QWORD *)(v10 + 2680);
        v85 = *(unsigned __int8 *)(*(_QWORD *)(v10 + 24) + 936LL);
        *(_OWORD *)v100 = *(_OWORD *)(v10 + 88);
        v84 = UlBuildFastRangeCacheMdlChain(v32, a3, v90, v85, v100, v87);
      }
      VariableHeaders = v84;
      v65 = v84 < 0;
      if ( v84 )
      {
LABEL_109:
        if ( v65 && v32 )
          goto LABEL_68;
LABEL_110:
        v6 = a6;
        goto LABEL_111;
      }
    }
    else
    {
      v41 = *(_QWORD *)(a3 + 520);
      if ( !*(_BYTE *)(v10 + 3214) )
      {
        v42 = *(unsigned int *)(a3 + 512);
        v43 = *((_QWORD *)v32 + 13);
        v44 = ((*(_WORD *)(v41 + 32) + (unsigned __int16)*(_DWORD *)(v41 + 44) + (unsigned __int16)*(_DWORD *)(a3 + 516))
             & 0xFFF)
            + v42
            + 4095;
        v45 = (*(_WORD *)(v41 + 32) + (unsigned __int16)*(_DWORD *)(v41 + 44) + (unsigned __int16)*(_DWORD *)(a3 + 516))
            & 0xFFF;
        *(_QWORD *)(v43 + 32) = (*(_QWORD *)(v41 + 32)
                               + *(unsigned int *)(v41 + 44)
                               + (unsigned __int64)*(unsigned int *)(a3 + 516))
                              & 0xFFFFFFFFFFFFF000uLL;
        *(_QWORD *)v43 = 0;
        *(_WORD *)(v43 + 10) = 0;
        *(_DWORD *)(v43 + 44) = v45;
        *(_DWORD *)(v43 + 40) = v42;
        *(_WORD *)(v43 + 8) = 8 * ((v44 >> 12) + 6);
        IoBuildPartialMdl(
          (PMDL)v41,
          *((PMDL *)v32 + 13),
          (PVOID)(*(_QWORD *)(v41 + 32) + *(unsigned int *)(v41 + 44) + (unsigned __int64)*(unsigned int *)(a3 + 516)),
          *(_DWORD *)(a3 + 512));
      }
      v46 = *(_QWORD *)(v10 + 24);
      LOBYTE(v30) = 1;
      *(_OWORD *)v100 = *(_OWORD *)(v10 + 88);
      VariableHeaders = UlGenerateVariableHeaders(
                          v90,
                          v30,
                          (int)v101,
                          v96[0],
                          *(_BYTE *)(v46 + 936),
                          (__int64)v100,
                          0,
                          *((_QWORD *)v32 + 12),
                          v89,
                          v95,
                          0,
                          (__int64)&v94,
                          (__int64)&v98);
      if ( VariableHeaders < 0 )
      {
        v37 = (volatile signed __int32 *)(v10 + 48);
        goto LABEL_68;
      }
      *(_DWORD *)(*((_QWORD *)v32 + 14) + 40LL) = v94;
      **((_QWORD **)v32 + 13) = *((_QWORD *)v32 + 14);
      v49 = *(unsigned int *)(a3 + 516);
      if ( (_DWORD)v49 )
      {
        v50 = *((_QWORD *)v32 + 15);
        v51 = (*(_QWORD *)(v41 + 32) + *(unsigned int *)(v41 + 44)) & 0xFFFFFFFFFFFFF000uLL;
        v52 = (*(_WORD *)(v41 + 32) + (unsigned __int16)*(_DWORD *)(v41 + 44)) & 0xFFF;
        v53 = v49 + ((*(_WORD *)(v41 + 32) + (unsigned __int16)*(_DWORD *)(v41 + 44)) & 0xFFF) + 4095LL;
        *(_QWORD *)v50 = 0;
        *(_WORD *)(v50 + 10) = 0;
        *(_QWORD *)(v50 + 32) = v51;
        *(_DWORD *)(v50 + 44) = v52;
        *(_DWORD *)(v50 + 40) = v49;
        *(_WORD *)(v50 + 8) = 8 * ((v53 >> 12) + 6);
        IoBuildPartialMdl(
          (PMDL)v41,
          *((PMDL *)v32 + 15),
          (PVOID)(*(_QWORD *)(v41 + 32) + *(unsigned int *)(v41 + 44)),
          *(_DWORD *)(a3 + 516));
        **((_QWORD **)v32 + 14) = *((_QWORD *)v32 + 15);
      }
      else
      {
        **((_QWORD **)v32 + 14) = 0;
      }
      *((_DWORD *)v32 + 68) = 3;
      if ( *(_BYTE *)(v10 + 3214) )
      {
        if ( *(_DWORD *)(a3 + 516) )
        {
          v62 = *((_QWORD *)v32 + 15);
          *((_DWORD *)v32 + 44) = 0;
          *((_QWORD *)v32 + 35) = v62;
          *a6 = *(_DWORD *)(a3 + 516);
        }
      }
      else
      {
        v54 = v94 + *(_DWORD *)(a3 + 512);
        v55 = *((_QWORD *)v32 + 13);
        *((_DWORD *)v32 + 44) = v54;
        *((_QWORD *)v32 + 35) = v55;
        *a6 = v54 + *(_DWORD *)(a3 + 516);
      }
      v37 = (volatile signed __int32 *)(v10 + 48);
    }
    v56 = (__int64 *)(v10 + 24);
    if ( *(_BYTE *)(a3 + 576) && v97 )
      *((_QWORD *)v32 + 17) = v97;
    v57 = "NULL";
    v58 = *(_DWORD *)(a3 + 516) + *(_DWORD *)(a3 + 512);
    v59 = 4;
    v91 = v58;
    v93 = "NULL";
    if ( *(_QWORD *)(a3 + 192) && *(_DWORD *)(a3 + 188) )
    {
      v57 = *(const char **)(a3 + 192);
      v93 = v57;
      v59 = *(_DWORD *)(a3 + 188);
    }
    v60 = *v56;
    if ( *v56 )
    {
      v47 = *(_QWORD *)(v60 + 1096);
      if ( (*(_BYTE *)(v47 + 1760) & 0x10) != 0 )
      {
        if ( !*(_QWORD *)(v47 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v10, v60, 0) )
          McTemplateK0pqqxs_EtwWriteTransfer(
            *(_QWORD *)(*v56 + 1096) + 1688,
            (unsigned int)HTTP_EVENT_SERVED_FROM_CACHE_LEGACY_V1,
            v10 + 72,
            v10,
            *(_DWORD *)(a3 + 312),
            v91,
            *(_QWORD *)(v10 + 56),
            (__int64)v93);
        v58 = v91;
        v57 = v93;
      }
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
    {
      v100[1] = (__int64)v57;
      HIDWORD(v100[0]) = 0;
      if ( v59 > 0x1F40 )
        LOWORD(v59) = 8000;
      LOWORD(v100[0]) = v59;
      v88 = *(_DWORD *)(a3 + 312);
      v86 = *(_QWORD *)(v10 + 56);
      WORD1(v100[0]) = v59;
      WPP_SF_qiLL_CTDSTR_(
        1040,
        189,
        (unsigned int)WPP_15f48f3705be3aa367958d68836c6e27_Traceguids,
        v10,
        v86,
        v88,
        v58,
        (__int64)v100);
    }
    v61 = (ULONG_PTR)(v32 + 32);
    if ( *((_QWORD *)v32 + 4) || *((_QWORD *)v32 + 6) || *((_QWORD *)v32 + 8) )
      UlBugCheckEx(1u, v61, (ULONG_PTR)"minio\\http\\sys\\sendresponse.c", 0x2F19u);
    LOBYTE(v47) = 1;
    UlThreadPoolEnqueueWorkItem(0, v61, UlSendCacheEntryWorker, v47, *(_QWORD *)(v99 + 1088), -1);
    goto LABEL_108;
  }
  VariableHeaders = -1073741247;
LABEL_111:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_Dd(1033, 190, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, *v6, VariableHeaders);
  return (unsigned int)VariableHeaders;
}

```

## disassembly

```asm
0x1400311f0  push    rbp
0x1400311f2  push    rbx
0x1400311f3  push    rsi
0x1400311f4  push    rdi
0x1400311f5  push    r12
0x1400311f7  push    r15
0x1400311f9  lea     rbp, [rsp-8]
0x1400311fe  sub     rsp, 108h
0x140031205  mov     rax, cs:__security_cookie
0x14003120c  xor     rax, rsp
0x14003120f  mov     [rbp+30h+var_48], rax
0x140031213  mov     r12, [rbp+30h+arg_28]
0x140031217  xor     esi, esi
0x140031219  mov     [rbp+30h+var_B0], r12
0x14003121d  mov     r15, r8
0x140031220  mov     [rbp+30h+var_88], rsi
0x140031224  mov     edi, edx
0x140031226  mov     dword ptr [rbp+30h+var_A8], esi
0x140031229  mov     rbx, rcx
0x14003122c  mov     [rbp+30h+var_90], r9
0x140031230  mov     dword ptr [rsp+130h+var_B8], edx
0x140031234  mov     [rbp+30h+var_80], rcx
0x140031238  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003123f  jnz     loc_140031B30
0x140031245  mov     [r12], esi
0x140031249  mov     eax, [rbx+278h]
0x14003124f  mov     [rsp+130h+var_30], r13
0x140031257  mov     [rsp+130h+var_38], r14
0x14003125f  test    al, 2
0x140031261  jnz     loc_140031C4F
0x140031267  mov     r14, [rbx+238h]
0x14003126e  mov     r13d, esi
0x140031271  cmp     [r14+0C8Eh], sil
0x140031278  jz      short loc_14003128E
0x14003127a  mov     r13d, [r15+280h]
0x140031281  cmp     [r14+0A74h], esi
0x140031288  jnz     loc_140031C59
0x14003128e  cmp     dword ptr [r14+0A74h], 1
0x140031296  mov     eax, 0C8h
0x14003129b  ja      loc_140031C6F
0x1400312a1  cmp     [r15+72h], sil
0x1400312a5  jnz     loc_140031929
0x1400312ab  mov     rax, [r15+8]
0x1400312af  test    rax, rax
0x1400312b2  jz      loc_140031CA8
0x1400312b8  mov     edx, [rax+68h]
0x1400312bb  test    dil, 2
0x1400312bf  jnz     loc_140031929
0x1400312c5  test    dil, 40h
0x1400312c9  jnz     loc_140031929
0x1400312cf  movzx   ecx, word ptr [r15+74h]
0x1400312d4  lea     eax, [rcx-64h]
0x1400312d7  cmp     ax, 63h ; 'c'
0x1400312db  jbe     loc_140031929
0x1400312e1  mov     eax, 0CCh
0x1400312e6  cmp     cx, ax
0x1400312e9  jz      loc_140031929
0x1400312ef  mov     eax, 130h
0x1400312f4  cmp     cx, ax
0x1400312f7  jz      loc_140031929
0x1400312fd  cmp     edx, 5
0x140031300  jz      loc_140031929
0x140031306  mov     r10d, [r15+204h]
0x14003130d  lea     r9, [rbp+30h+var_60]
0x140031311  mov     byte ptr [rbp+30h+var_70], sil
0x140031315  mov     r11d, 1
0x14003131b  mov     eax, 0CCCCCCCDh
0x140031320  mov     r8d, r11d
0x140031323  mul     r10d
0x140031326  shr     edx, 3
0x140031329  movzx   eax, dl
0x14003132c  shl     al, 2
0x14003132f  lea     ecx, [rax+rdx]
0x140031332  movsxd  rax, r11d
0x140031335  add     cl, cl
0x140031337  inc     r11d
0x14003133a  sub     r10b, cl
0x14003133d  add     r10b, 30h ; '0'
0x140031341  mov     byte ptr [rbp+rax+30h+var_70], r10b
0x140031346  mov     r10d, edx
0x140031349  test    edx, edx
0x14003134b  jnz     short loc_14003131B
0x14003134d  test    r8d, r8d
0x140031350  js      short loc_140031366
0x140031352  mov     eax, r8d
0x140031355  movzx   ecx, byte ptr [rbp+rax+30h+var_70]
0x14003135a  mov     [r9], cl
0x14003135d  inc     r9
0x140031360  sub     r8d, 1
0x140031364  jns     short loc_140031352
0x140031366  lea     rcx, [r9-1]
0x14003136a  lea     rax, [rbp+30h+var_60]
0x14003136e  sub     ecx, eax
0x140031370  mov     qword ptr [rbp+30h+var_98], rcx
0x140031374  mov     ebx, edi
0x140031376  and     bl, 1
0x140031379  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140031380  jnz     loc_140031CAF
0x140031386  mov     eax, [r14+0AC0h]
0x14003138d  mov     [rsp+130h+var_C0], eax
0x140031391  cmp     eax, 3
0x140031394  jnz     loc_140031A5B
0x14003139a  prefetchw byte ptr [r14+8A0h]
0x1400313a2  mov     eax, [r14+8A0h]
0x1400313a9  mov     ecx, eax
0x1400313ab  lock cmpxchg [r14+8A0h], ecx
0x1400313b4  jnz     short loc_1400313A9
0x1400313b6  test    al, 1
0x1400313b8  jnz     loc_140031774
0x1400313be  movzx   eax, word ptr [r14+840h]
0x1400313c6  test    bl, bl
0x1400313c8  jnz     loc_140031A41
0x1400313ce  cmp     ax, 1
0x1400313d2  jnz     loc_140031774
0x1400313d8  cmp     [r14+842h], si
0x1400313e0  jnz     loc_140031774
0x1400313e6  mov     r8d, 2
0x1400313ec  mov     [rsp+130h+var_C0], r8d
0x1400313f1  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400313f8  jnz     loc_140031CF0
0x1400313fe  mov     esi, [r15+204h]
0x140031405  mov     ebx, [r15+200h]
0x14003140c  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140031413  jnz     loc_140031D0E
0x140031419  movzx   r12d, [rbp+30h+arg_20]
0x14003141e  test    r13d, r13d
0x140031421  jz      short loc_14003142F
0x140031423  mov     eax, cs:UlH3ExtraHeaderCount
0x140031429  add     eax, 2
0x14003142c  add     r13d, eax
0x14003142f  lea     edi, [rbx+0B1h]
0x140031435  cmp     edi, 200h
0x14003143b  ja      loc_140174B10
0x140031441  cmp     esi, 40000h
0x140031447  ja      loc_140174B10
0x14003144d  cmp     r13d, 14h
0x140031451  ja      loc_140174B10
0x140031457  mov     r13d, gs:1A4h
0x140031460  cmp     cs:UxDebugDisableLookaside, 0
0x140031467  jnz     loc_140031A19
0x14003146d  cmp     cs:UxCompactMode, 0
0x140031474  jnz     loc_140031B6F
0x14003147a  mov     rcx, cs:qword_1401A01F0
0x140031481  lea     ebx, [r13+1]
0x140031485  shl     rbx, 7
0x140031489  add     rbx, rcx
0x14003148c  movzx   eax, byte ptr [rbx+0B0h]
0x140031493  test    al, al
0x140031495  jz      loc_140031B92
0x14003149b  lea     rcx, [rbx+40h]; Lookaside
0x14003149f  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400314a6  nop     dword ptr [rax+rax+00h]
0x1400314ab  mov     rbx, rax
0x1400314ae  test    rax, rax
0x1400314b1  jz      loc_1400315BE
0x1400314b7  mov     dword ptr [rax+10h], 41436C55h
0x1400314be  lea     rcx, [rax+110h]; void *
0x1400314c5  xor     edi, edi
0x1400314c7  mov     [rax+15h], r12b
0x1400314cb  xorps   xmm0, xmm0
0x1400314ce  mov     [rax+88h], rdi
0x1400314d5  mov     [rax+50h], rdi
0x1400314d9  xor     edx, edx; Val
0x1400314db  mov     [rax+80h], rdi
0x1400314e2  mov     r8d, 50h ; 'P'; Size
0x1400314e8  mov     [rax+90h], rdi
0x1400314ef  mov     [rax+98h], edi
0x1400314f5  movups  xmmword ptr [rax+0A0h], xmm0
0x1400314fc  mov     [rax+0B0h], edi
0x140031502  mov     byte ptr [rax+14h], 1
0x140031506  call    memset
0x14003150b  mov     [rbx+20h], rdi
0x14003150f  xorps   xmm0, xmm0
0x140031512  mov     [rbx+30h], rdi
0x140031516  xor     eax, eax
0x140031518  mov     [rbx+40h], rdi
0x14003151c  lea     rdi, [rbx+0C0h]
0x140031523  mov     r12, [rdi]
0x140031526  mov     esi, [rbx+0D0h]
0x14003152c  movups  xmmword ptr [rdi], xmm0
0x14003152f  movups  xmmword ptr [rdi+10h], xmm0
0x140031533  mov     [rdi+20h], rax
0x140031537  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14003153e  jnz     loc_140031BA0
0x140031544  test    esi, esi
0x140031546  jz      short loc_14003154E
0x140031548  mov     [rdi], r12
0x14003154b  mov     [rdi+10h], esi
0x14003154e  mov     dword ptr [rdi+18h], 0FFFFFFFh
0x140031555  mov     dword ptr [rdi+1Ch], 0FFFFFFFh
0x14003155c  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140031563  jnz     loc_140031A63
0x140031569  mov     esi, [rbx+0F8h]
0x14003156f  lea     rdi, [rbx+0E8h]
0x140031576  mov     r12, [rdi]
0x140031579  xorps   xmm0, xmm0
0x14003157c  movups  xmmword ptr [rdi], xmm0
0x14003157f  xor     eax, eax
0x140031581  movups  xmmword ptr [rdi+10h], xmm0
0x140031585  mov     [rdi+20h], rax
0x140031589  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x140031590  jnz     loc_140031BC7
0x140031596  test    esi, esi
0x140031598  jz      short loc_1400315A0
0x14003159a  mov     [rdi], r12
0x14003159d  mov     [rdi+10h], esi
0x1400315a0  mov     dword ptr [rdi+18h], 0FFFFFFFh
0x1400315a7  mov     dword ptr [rdi+1Ch], 0FFFFFFFh
0x1400315ae  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400315b5  jnz     loc_140031A7E
0x1400315bb  mov     [rbx], r13d
0x1400315be  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400315c5  jnz     loc_140031BEE
0x1400315cb  test    rbx, rbx
0x1400315ce  jz      loc_140031D2E
0x1400315d4  lea     r12, [r14+30h]
0x1400315d8  mov     eax, 1
0x1400315dd  lock xadd [r12], eax
0x1400315e3  inc     eax
0x1400315e5  cmp     cs:UxDebugCheckRefcount, 0
0x1400315ec  jnz     loc_140031935
0x1400315f2  mov     eax, dword ptr [rsp+130h+var_B8]
0x1400315f6  xor     esi, esi
0x1400315f8  mov     [rbx+98h], eax
0x1400315fe  mov     edi, 0C000009Ah
0x140031603  mov     [rbx+50h], r15
0x140031607  mov     [rbx+80h], r14
0x14003160e  mov     [rbp+30h+var_A0], rsi
0x140031612  cmp     [r14+0C8Eh], sil
0x140031619  jnz     loc_14003198A
0x14003161f  cmp     dword ptr [r14+0A74h], 1
0x140031627  jz      loc_140174D3D
0x14003162d  cmp     byte ptr [r14+0C8Eh], 0
0x140031635  mov     rsi, [r15+208h]
0x14003163c  jnz     loc_1400316D5
0x140031642  mov     eax, [rsi+2Ch]
0x140031645  mov     r8d, [r15+204h]
0x14003164c  mov     r10d, [r15+200h]
0x140031653  add     r8, rax
0x140031656  add     r8, [rsi+20h]
0x14003165a  mov     r9, [rbx+68h]
0x14003165e  mov     edx, r8d
0x140031661  mov     eax, edx
0x140031663  and     r8, 0FFFFFFFFFFFFF000h
0x14003166a  and     eax, 0FFFh
0x14003166f  lea     rcx, [r10+0FFFh]
0x140031676  add     rcx, rax
0x140031679  and     edx, 0FFFh
0x14003167f  mov     [r9+20h], r8
0x140031683  xor     eax, eax
0x140031685  mov     qword ptr [r9], 0
0x14003168c  mov     [r9+0Ah], ax
0x140031691  mov     [r9+2Ch], edx
0x140031695  mov     [r9+28h], r10d
0x140031699  shr     rcx, 0Ch
0x14003169d  add     cx, 6
0x1400316a1  shl     cx, 3
0x1400316a5  mov     [r9+8], cx
0x1400316aa  mov     rcx, rsi; SourceMdl
0x1400316ad  mov     r8d, [r15+204h]
0x1400316b4  mov     eax, [rsi+2Ch]
0x1400316b7  mov     r9d, [r15+200h]; Length
0x1400316be  add     r8, rax
0x1400316c1  add     r8, [rsi+20h]; VirtualAddress
0x1400316c5  mov     rdx, [rbx+68h]; TargetMdl
0x1400316c9  call    cs:__imp_IoBuildPartialMdl
0x1400316d0  nop     dword ptr [rax+rax+00h]
0x1400316d5  mov     rcx, [r14+18h]
0x1400316d9  lea     rax, [rbp+30h+var_88]
0x1400316dd  movups  xmm0, xmmword ptr [r14+58h]
0x1400316e2  mov     r9d, [rbp+30h+var_98]; int
0x1400316e6  lea     r8, [rbp+30h+var_60]; int
0x1400316ea  mov     [rsp+130h+var_D0], rax; __int64
0x1400316ef  mov     dl, 1; int
0x1400316f1  lea     rax, [rbp+30h+var_A8]
0x1400316f5  movaps  xmmword ptr [rbp+30h+var_70], xmm0
0x1400316f9  mov     [rsp+130h+var_D8], rax; __int64
0x1400316fe  mov     rax, [rbp+30h+var_A0]
0x140031702  mov     [rsp+130h+var_E0], 0; __int64
0x14003170b  mov     [rsp+130h+var_E8], rax; __int64
0x140031710  mov     rax, [rbx+60h]
0x140031714  mov     [rsp+130h+var_F8], rax; size_t
0x140031719  lea     rax, [rbp+30h+var_70]
0x14003171d  mov     [rsp+130h+var_100], 0; char
0x140031722  mov     [rsp+130h+var_108], rax; __int64
0x140031727  movzx   eax, byte ptr [rcx+3A8h]
0x14003172e  mov     ecx, [rsp+130h+var_C0]; int
0x140031732  mov     [rsp+130h+var_110], al; char
0x140031736  call    UlGenerateVariableHeaders
0x14003173b  mov     edi, eax
0x14003173d  test    eax, eax
0x14003173f  jns     short loc_140031780
0x140031741  lea     r12, [r14+30h]
0x140031745  mov     eax, 0FFFFFFFFh
0x14003174a  lock xadd [r12], eax
0x140031750  dec     eax
0x140031752  cmp     cs:UxDebugCheckRefcount, 0
0x140031759  jnz     loc_140031C2F
0x14003175f  test    eax, eax
0x140031761  jz      loc_140031D95
  ... truncated ...
```
