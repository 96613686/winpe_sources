# QuicSendWriteFrames

- ea: `0x140019040`
- end: `0x140019bfd`
- name: `QuicSendWriteFrames`
- size: `3005`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: ``

## callers

- `0x140016210`

## callees

- `0x14000d7a0`
- `0x1400123b0`
- `0x140019040`
- `0x140019c10`
- `0x140019e00`
- `0x140019e48`
- `0x14001b768`
- `0x14001bbc8`
- `0x14001bd68`
- `0x140022d10`
- `0x140022f04`
- `0x140028658`
- `0x14002ab40`
- `0x14002f700`
- `0x14002fac8`
- `0x14002fb78`
- `0x1400300b8`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x140045ccc`
- `0x140046a14`
- `0x140046b30`
- `0x140046cbc`
- `0x1400489b0`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14001911f`
- `HAL!KeQueryPerformanceCounter` at `0x14001911f`

## pseudocode

```c
bool __fastcall QuicSendWriteFrames(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // r13
  __int64 v5; // rdx
  unsigned __int16 v7; // r12
  __int64 v8; // rsi
  bool v9; // r15
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // r10
  __int64 v13; // r9
  __int16 v14; // ax
  unsigned __int64 v15; // r10
  __int64 v16; // rcx
  __int16 v17; // ax
  unsigned int v18; // r15d
  unsigned __int16 v19; // r8
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 v23; // r9
  __int64 v24; // rbx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // ecx
  __int64 v29; // rbx
  __int64 v30; // rax
  int v31; // eax
  _QWORD *v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rcx
  BOOL v36; // ebx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // r9
  unsigned __int8 v41; // si
  bool v42; // zf
  __int64 v43; // r15
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // r9
  __int64 v53; // rdx
  unsigned __int8 IsServer; // al
  __int64 v55; // r9
  __int64 v56; // rdx
  unsigned __int8 v57; // al
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 *v63; // r15
  char i; // dl
  size_t v65; // rdx
  unsigned __int64 v66; // rcx
  unsigned __int64 v67; // rax
  size_t v68; // rbx
  __int64 v69; // rdx
  char v70; // dl
  __int64 *j; // rbx
  __int64 v72; // r9
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // r9
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int16 v79; // dx
  unsigned __int16 *v80; // rcx
  unsigned __int16 v81; // ax
  unsigned __int16 v82; // cx
  char v83; // [rsp+30h] [rbp-79h]
  bool v84; // [rsp+31h] [rbp-78h]
  unsigned __int8 v85; // [rsp+32h] [rbp-77h]
  unsigned __int16 v86; // [rsp+34h] [rbp-75h]
  __int64 v87; // [rsp+38h] [rbp-71h] BYREF
  __int64 v88; // [rsp+40h] [rbp-69h]
  __int64 v89; // [rsp+48h] [rbp-61h]
  __int64 v90; // [rsp+50h] [rbp-59h]
  unsigned __int64 v91; // [rsp+58h] [rbp-51h] BYREF
  __int64 v92; // [rsp+60h] [rbp-49h]
  __int64 v93[3]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v94; // [rsp+80h] [rbp-29h] BYREF
  __int64 v95; // [rsp+88h] [rbp-21h]
  __int64 v96; // [rsp+90h] [rbp-19h]
  _BYTE v97[33]; // [rsp+98h] [rbp-11h] BYREF
  int v98; // [rsp+B9h] [rbp+10h]
  __int16 v99; // [rsp+BDh] [rbp+14h]
  char v100; // [rsp+BFh] [rbp+16h]

  v4 = a1 - 3416;
  v5 = *((unsigned __int8 *)a2 + 370);
  v7 = *(_WORD *)a2[4] - v5;
  v85 = *(_BYTE *)(a2[51] + 90LL);
  v8 = *(_QWORD *)(a1 - 3416 + 8LL * *((int *)a2 + 93) + 2760);
  if ( *((_DWORD *)a2 + 98) || (v83 = 0, (unsigned __int8)QuicCongestionControlGetExemptions(*a2 + 2168LL)) )
    v83 = 1;
  v9 = (((*(_BYTE *)(a2[51] + 88LL) & 3) - 1) & 0xFD) == 0;
  v84 = v9;
  if ( *((_BYTE *)a2 + 376) != (*(_DWORD *)(v4 + 3636) == -817679509) + 1
    && (*(_BYTE *)(v8 + 394) & 1) == 0
    && *(_DWORD *)(v8 + 208) )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v11 = *a2;
    v12 = ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
        + (1000000LL * PerformanceCounter.LowPart
         + ((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
        / CxPlatPerfFreq.QuadPart;
    v42 = (*(_BYTE *)(*a2 + 252LL) & 8) == 0;
    v87 = (v12 - *(_QWORD *)(v8 + 384)) >> *(_BYTE *)(*a2 + 279LL);
    if ( !v42 && *((_DWORD *)a2 + 93) == 2 )
    {
      v13 = a2[4];
      v14 = *((unsigned __int8 *)a2 + 370);
      v91 = v12 - *(_QWORD *)(v11 + 3640);
      if ( !(unsigned __int8)QuicTimestampFrameEncode(
                               &v91,
                               (char *)a2 + 378,
                               (unsigned __int16)(*(_WORD *)v13 - v14),
                               *(_QWORD *)(v13 + 8)) )
        return *(_BYTE *)(a2[51] + 90LL) > v85;
    }
    v15 = v8 + 352;
    if ( (*(_BYTE *)(v8 + 394) & 2) == 0 )
      v15 = 0;
    v16 = a2[4];
    v17 = *((unsigned __int8 *)a2 + 370);
    v18 = *(_DWORD *)(v8 + 208) - 1;
    v91 = v15;
    v19 = *(_WORD *)v16 - v17;
    v93[0] = *(_QWORD *)(v16 + 8);
    v86 = v19;
    v96 = v18;
    v20 = (_QWORD *)(*(_QWORD *)(v8 + 200) + 16LL * v18);
    v21 = v20[1];
    v22 = v21 + *v20 - 1LL;
    v95 = v87;
    v92 = v21;
    *(_QWORD *)v97 = v21 - 1;
    v94 = v22;
    if ( !(unsigned __int8)QuicAckHeaderEncode((unsigned int)&v94, v15, (int)a2 + 378, v19, v93[0]) )
      return *(_BYTE *)(a2[51] + 90LL) > v85;
    v23 = v93[0];
    if ( v18 )
    {
      while ( 1 )
      {
        v24 = v22 - v92;
        v25 = (_QWORD *)(*(_QWORD *)(v8 + 200) + 16LL * --v18);
        v26 = v25[1];
        v27 = *v25 - 1LL;
        v92 = v26;
        v87 = v26 + v27;
        v93[0] = v24 - (v26 + v27) - 1;
        v93[1] = v26 - 1;
        if ( !(unsigned __int8)QuicAckBlockEncode(v93, (char *)a2 + 378, v86, v23) )
          break;
        v22 = v87;
        if ( !v18 )
          goto LABEL_16;
      }
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\frame.c", 240, "0");
      return *(_BYTE *)(a2[51] + 90LL) > v85;
    }
LABEL_16:
    if ( v91 && !(unsigned __int8)QuicAckEcnEncode(v91, (char *)a2 + 378, v86, v23) )
      return *(_BYTE *)(a2[51] + 90LL) > v85;
    if ( *(_WORD *)(v8 + 392) )
    {
      v28 = 0;
      *(_WORD *)(v8 + 392) = 0;
      v29 = *a2;
      v30 = *a2 + 2760LL;
      while ( !*(_QWORD *)v30 || !*(_WORD *)(*(_QWORD *)v30 + 392LL) )
      {
        ++v28;
        v30 += 8;
        if ( v28 >= 3 )
        {
          v31 = *(_DWORD *)(v29 + 3488);
          if ( (v31 & 1) != 0 )
          {
            *(_DWORD *)(v29 + 3488) = v31 & 0xFFFFFFFE;
          }
          else if ( (*(_BYTE *)(v29 + 3416) & 2) != 0 )
          {
            QuicConnTimerCancel(*a2, 1);
            *(_BYTE *)(v29 + 3416) &= ~2u;
          }
          break;
        }
      }
    }
    *(_BYTE *)(v8 + 394) |= 1u;
    v9 = v84;
    v32 = (_QWORD *)(*(_QWORD *)(v8 + 200) + 16LL * (unsigned int)(*(_DWORD *)(v8 + 208) - 1));
    v33 = v32[1] - 1LL + *v32;
    *(_QWORD *)(a2[51] + 24 * (*(unsigned __int8 *)(a2[51] + 90LL) + 4LL)) = v33;
    *(_QWORD *)(v8 + 376) = v33;
    v5 = a2[51];
    *(_WORD *)(v5 + 24LL * *(unsigned __int8 *)(v5 + 90) + 114) = 2;
    ++*(_BYTE *)(a2[51] + 90LL);
  }
  if ( v83
    && (*(_DWORD *)(a1 + 72) & 2) != 0
    && (unsigned __int8)QuicCryptoWriteFrames(v4 + 2784, a2)
    && *(_BYTE *)(a2[51] + 90LL) == 12 )
  {
    return 1;
  }
  v34 = *(_DWORD *)(a1 + 72);
  if ( (v34 & 0xC) != 0 )
  {
    v35 = *(_QWORD *)(v4 + 1600);
    v36 = 0;
    if ( (*(_BYTE *)(v4 + 248) & 0x20) == 0 )
      v36 = (*(_DWORD *)(a1 + 72) & 8) != 0;
    v37 = *(_QWORD *)(v4 + 1592);
    if ( v36 && !v9 )
    {
      v37 = 11;
      v35 = 0;
      LOBYTE(v36) = 0;
    }
    LOBYTE(v94) = v36;
    *(_DWORD *)((char *)&v94 + 1) = 0;
    *(_WORD *)((char *)&v94 + 5) = 0;
    HIBYTE(v94) = 0;
    v95 = v37;
    v96 = 0;
    if ( v35 )
    {
      v38 = -1;
      do
        ++v38;
      while ( *(_BYTE *)(v35 + v38) );
      *(_QWORD *)v97 = v38;
    }
    else
    {
      *(_QWORD *)v97 = 0;
    }
    v39 = a2[4];
    *(_QWORD *)&v97[8] = v35;
    if ( !(unsigned __int8)QuicConnCloseFrameEncode(&v94, (char *)a2 + 378, v7, *(_QWORD *)(v39 + 8)) )
      return 0;
    *((_BYTE *)a2 + 368) |= 0x80u;
    if ( *(_DWORD *)a2[5] == *(_DWORD *)(v4 + 2812) )
      *(_DWORD *)(a1 + 72) &= 0xFFFFFFF3;
    QuicPacketBuilderAddFrame(a2, (unsigned int)(v36 + 28), 0);
    return 1;
  }
  if ( v83 )
  {
    if ( (v34 & 0x800) != 0 )
    {
      v41 = 0;
      v42 = *(_BYTE *)(v4 + 275) == 0;
      if ( *(_BYTE *)(v4 + 275) )
      {
        do
        {
          v43 = v4 + 240LL * v41;
          if ( (*(_BYTE *)(v43 + 322) & 2) != 0 )
          {
            v44 = a2[4];
            v45 = *(_QWORD *)(v43 + 532);
            v87 = v45;
            if ( !(unsigned __int8)QuicPathChallengeFrameEncode(
                                     27,
                                     (unsigned int)&v87,
                                     (int)a2 + 378,
                                     v7,
                                     *(_QWORD *)(v44 + 8)) )
              break;
            *(_BYTE *)(v43 + 322) &= ~2u;
            LOBYTE(a3) = 1;
            LOBYTE(v5) = 27;
            *(_QWORD *)(a2[51] + 24 * (*(unsigned __int8 *)(a2[51] + 90LL) + 4LL)) = v45;
            if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v5, a3) )
              break;
          }
          ++v41;
        }
        while ( v41 < *(_BYTE *)(v4 + 275) );
        v42 = v41 == *(_BYTE *)(v4 + 275);
      }
      if ( v42 )
        *(_DWORD *)(a1 + 72) &= ~0x800u;
      if ( *(_BYTE *)(a2[51] + 90LL) == 12 )
        return 1;
    }
    if ( v84 )
    {
      if ( (*(_BYTE *)(a2[51] + 88LL) & 3) == 3 && (*(_DWORD *)(a1 + 72) & 0x2000) != 0 )
      {
        v46 = *((unsigned __int16 *)a2 + 189);
        if ( (unsigned __int16)v46 < v7 )
        {
          LOBYTE(a3) = 1;
          LOBYTE(v5) = 30;
          *(_BYTE *)(v46 + *(_QWORD *)(a2[4] + 8LL)) = 30;
          ++*((_WORD *)a2 + 189);
          *(_DWORD *)(a1 + 72) &= ~0x2000u;
          *((_WORD *)a2 + 192) = *(_WORD *)a2[4];
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v5, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x10) != 0 )
      {
        v47 = a2[4];
        v87 = *(_QWORD *)(a1 + 56);
        if ( (unsigned __int8)QuicDataBlockedFrameEncode(&v87, (char *)a2 + 378, v7, *(_QWORD *)(v47 + 8)) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x10u;
          LOBYTE(a3) = 1;
          LOBYTE(v48) = 20;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v48, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x20) != 0 )
      {
        v49 = a2[4];
        v87 = *(_QWORD *)(a1 + 32);
        if ( (unsigned __int8)QuicMaxDataFrameEncode(&v87, (char *)a2 + 378, v7, *(_QWORD *)(v49 + 8)) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x20u;
          LOBYTE(a3) = 1;
          LOBYTE(v50) = 16;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v50, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x40) != 0 )
      {
        v87 = 1;
        v51 = (unsigned __int8)QuicConnIsServer(v4) ? *(_QWORD *)(v4 + 2032) : *(_QWORD *)(v4 + 2056);
        v52 = a2[4];
        v88 = v51;
        if ( (unsigned __int8)QuicMaxStreamsFrameEncode(&v87, (char *)a2 + 378, v7, *(_QWORD *)(v52 + 8)) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x40u;
          LOBYTE(a3) = 1;
          LOBYTE(v53) = 18;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v53, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
      {
        v87 = 1;
        IsServer = QuicConnIsServer(v4);
        v55 = *(_QWORD *)(a2[4] + 8LL);
        v88 = *(_QWORD *)(v4 + 24LL * IsServer + 2032);
        if ( (unsigned __int8)QuicStreamsBlockedFrameEncode(&v87, (char *)a2 + 378, v7, v55) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x10000u;
          LOBYTE(a3) = 1;
          LOBYTE(v56) = 22;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v56, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
      {
        v87 = 0;
        v57 = QuicConnIsServer(v4);
        v58 = *(_QWORD *)(a2[4] + 8LL);
        v88 = *(_QWORD *)(v4 + 24 * (v57 | 2LL) + 2032);
        if ( (unsigned __int8)QuicStreamsBlockedFrameEncode(&v87, (char *)a2 + 378, v7, v58) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x20000u;
          LOBYTE(a3) = 1;
          LOBYTE(v59) = 23;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v59, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x80u) != 0 )
      {
        v87 = 0;
        v60 = (unsigned __int8)QuicConnIsServer(v4) ? *(_QWORD *)(v4 + 2080) : *(_QWORD *)(v4 + 2104);
        v61 = a2[4];
        v88 = v60;
        if ( (unsigned __int8)QuicMaxStreamsFrameEncode(&v87, (char *)a2 + 378, v7, *(_QWORD *)(v61 + 8)) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x80u;
          LOBYTE(a3) = 1;
          LOBYTE(v62) = 19;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v62, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
      {
        v63 = *(__int64 **)(v4 + 1280);
        for ( i = 0; v63; v63 = (__int64 *)*v63 )
        {
          if ( (v63[2] & 2) != 0 )
          {
            if ( i )
              return 1;
            v65 = *((unsigned __int8 *)v63 + 17);
            v98 = 0;
            v99 = 0;
            v100 = 0;
            v66 = *(unsigned __int8 *)(v4 + 274);
            *(_DWORD *)((char *)&v94 + 1) = 0;
            *(_WORD *)((char *)&v94 + 5) = 0;
            HIBYTE(v94) = 0;
            v67 = v63[3];
            LOBYTE(v94) = v65;
            v95 = v67;
            v96 = 0;
            memset(v97, 0, sizeof(v97));
            if ( v67 >= v66 )
              v96 = v67 - v66 + 1;
            v68 = v65;
            memmove(v97, v63 + 4, v65);
            QuicLibraryGenerateStatelessResetToken(*(_QWORD *)(v4 + 72), v63 + 4, &v97[v68]);
            if ( !(unsigned __int8)QuicNewConnectionIDFrameEncode(&v94, (char *)a2 + 378, v7, *(_QWORD *)(a2[4] + 8LL)) )
              goto LABEL_100;
            *((_BYTE *)v63 + 16) &= ~2u;
            LOBYTE(a3) = 1;
            v69 = a2[51];
            *(_QWORD *)(v69 + 24 * (*(unsigned __int8 *)(v69 + 90) + 4LL)) = v63[3];
            LOBYTE(v69) = 24;
            i = QuicPacketBuilderAddFrame(a2, v69, a3);
          }
        }
        *(_DWORD *)(a1 + 72) &= ~0x100u;
        if ( i )
          return 1;
      }
LABEL_100:
      if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
      {
        v70 = 0;
        for ( j = *(__int64 **)(v4 + 1288); j != (__int64 *)(v4 + 1288); j = (__int64 *)*j )
        {
          if ( (j[4] & 2) != 0 )
          {
            if ( v70 )
              return 1;
            v72 = a2[4];
            v87 = j[5];
            if ( !(unsigned __int8)QuicRetireConnectionIDFrameEncode(&v87, (char *)a2 + 378, v7, *(_QWORD *)(v72 + 8)) )
              goto LABEL_108;
            *((_BYTE *)j + 32) &= ~2u;
            LOBYTE(a3) = 1;
            v73 = a2[51];
            *(_QWORD *)(v73 + 24 * (*(unsigned __int8 *)(v73 + 90) + 4LL)) = j[5];
            LOBYTE(v73) = 25;
            v70 = QuicPacketBuilderAddFrame(a2, v73, a3);
          }
        }
        *(_DWORD *)(a1 + 72) &= ~0x200u;
        if ( v70 )
          return 1;
      }
LABEL_108:
      if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
      {
        v87 = *(_QWORD *)(v4 + 288);
        v88 = *(unsigned __int8 *)(v4 + 281);
        v74 = 1000 * QuicConnGetAckDelay(v4);
        v75 = *(unsigned __int8 *)(v4 + 283);
        v76 = *(_QWORD *)(a2[4] + 8LL);
        v89 = v74;
        v90 = v75;
        if ( (unsigned __int8)QuicAckFrequencyFrameEncode(&v87, (char *)a2 + 378, v7, v76) )
        {
          *(_DWORD *)(a1 + 72) &= ~0x8000u;
          LOBYTE(a3) = 1;
          v77 = a2[51];
          *(_QWORD *)(v77 + 24 * (*(unsigned __int8 *)(v77 + 90) + 4LL)) = v87;
          LOBYTE(v77) = -81;
          if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, v77, a3) )
            return 1;
        }
      }
      if ( (*(_DWORD *)(a1 + 72) & 0x4000) != 0 )
      {
        QuicDatagramWriteFrame(v4 + 3552, a2);
        if ( *(_BYTE *)(a2[51] + 90LL) == 12 )
          return 1;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000) != 0 )
    {
      v78 = *((unsigned __int16 *)a2 + 189);
      if ( (unsigned __int16)v78 < v7 )
      {
        *(_BYTE *)(v78 + *(_QWORD *)(a2[4] + 8LL)) = 1;
        ++*((_WORD *)a2 + 189);
        *(_DWORD *)(a1 + 72) &= ~0x1000u;
        v79 = *(_WORD *)(v4 + 3888);
        v80 = (unsigned __int16 *)a2[4];
        if ( v79 )
        {
          v81 = v79 + *((_WORD *)a2 + 189) + *((unsigned __int8 *)a2 + 370);
          *((_WORD *)a2 + 192) = v81;
          v82 = *v80;
          if ( v81 > v82 )
            *((_WORD *)a2 + 192) = v82;
        }
        else
        {
          *((_WORD *)a2 + 192) = *v80;
        }
        LOBYTE(a3) = 1;
        if ( (unsigned __int8)QuicPacketBuilderAddFrame(a2, 1, a3) )
          return 1;
      }
    }
  }
  return *(_BYTE *)(a2[51] + 90LL) > v85;
}

```

## disassembly

```asm
0x140019040  mov     [rsp-8+arg_10], rbx
0x140019045  push    rbp
0x140019046  push    rsi
0x140019047  push    rdi
0x140019048  push    r12
0x14001904a  push    r13
0x14001904c  push    r14
0x14001904e  push    r15
0x140019050  lea     rbp, [rsp-27h]
0x140019055  sub     rsp, 0D0h
0x14001905c  mov     rax, cs:__security_cookie
0x140019063  xor     rax, rsp
0x140019066  mov     [rbp+57h+var_40], rax
0x14001906a  mov     rdi, rdx
0x14001906d  lea     r13, [rcx-0D58h]
0x140019074  movzx   edx, byte ptr [rdx+172h]
0x14001907b  mov     r14, rcx
0x14001907e  mov     rax, [rdi+20h]
0x140019082  movzx   r12d, word ptr [rax]
0x140019086  mov     rax, [rdi+198h]
0x14001908d  sub     r12w, dx
0x140019091  cmp     dword ptr [rdi+188h], 0
0x140019098  movzx   eax, byte ptr [rax+5Ah]
0x14001909c  mov     [rbp+57h+var_CE], al
0x14001909f  movsxd  rax, dword ptr [rdi+174h]
0x1400190a6  mov     rsi, [r13+rax*8+0AC8h]
0x1400190ae  ja      short loc_1400190C7
0x1400190b0  mov     rcx, [rdi]
0x1400190b3  add     rcx, 878h
0x1400190ba  call    QuicCongestionControlGetExemptions
0x1400190bf  mov     [rbp+57h+var_D0], 0
0x1400190c3  test    al, al
0x1400190c5  jz      short loc_1400190CB
0x1400190c7  mov     [rbp+57h+var_D0], 1
0x1400190cb  mov     rax, [rdi+198h]
0x1400190d2  movzx   ecx, byte ptr [rax+58h]
0x1400190d6  and     cl, 3
0x1400190d9  dec     cl
0x1400190db  test    cl, 0FDh
0x1400190de  setz    r15b
0x1400190e2  cmp     dword ptr [r13+0E34h], 0CF43336Bh
0x1400190ed  mov     [rbp+57h+var_CF], r15b
0x1400190f1  setz    al
0x1400190f4  xor     ebx, ebx
0x1400190f6  inc     al
0x1400190f8  cmp     [rdi+178h], al
0x1400190fe  jz      loc_1400193F9
0x140019104  test    byte ptr [rsi+18Ah], 1
0x14001910b  jnz     loc_1400193F9
0x140019111  cmp     [rsi+0D0h], ebx
0x140019117  jz      loc_1400193F9
0x14001911d  xor     ecx, ecx; PerformanceFrequency
0x14001911f  call    cs:__imp_KeQueryPerformanceCounter
0x140019126  nop     dword ptr [rax+rax+00h]
0x14001912b  mov     r8, qword ptr cs:CxPlatPerfFreq
0x140019132  xor     edx, edx
0x140019134  mov     rcx, rax
0x140019137  shr     rax, 20h
0x14001913b  imul    r9, rax, 0F4240h
0x140019142  mov     rax, r9
0x140019145  div     r8
0x140019148  mov     rax, rdx
0x14001914b  mov     edx, ecx
0x14001914d  shl     rax, 20h
0x140019151  imul    rcx, rdx, 0F4240h
0x140019158  xor     edx, edx
0x14001915a  add     rax, rcx
0x14001915d  div     r8
0x140019160  xor     edx, edx
0x140019162  mov     r10, rax
0x140019165  mov     rax, r9
0x140019168  div     r8
0x14001916b  mov     rdx, [rdi]
0x14001916e  shl     rax, 20h
0x140019172  add     r10, rax
0x140019175  mov     rax, r10
0x140019178  sub     rax, [rsi+180h]
0x14001917f  movzx   ecx, byte ptr [rdx+117h]
0x140019186  shr     rax, cl
0x140019189  test    byte ptr [rdx+0FCh], 8
0x140019190  mov     [rbp+57h+var_C8], rax
0x140019194  jz      short loc_1400191D9
0x140019196  cmp     dword ptr [rdi+174h], 2
0x14001919d  jnz     short loc_1400191D9
0x14001919f  mov     r9, [rdi+20h]
0x1400191a3  lea     rcx, [rbp+57h+var_A8]
0x1400191a7  sub     r10, [rdx+0E38h]
0x1400191ae  lea     rdx, [rdi+17Ah]
0x1400191b5  movzx   eax, byte ptr [rdi+172h]
0x1400191bc  mov     [rbp+57h+var_A8], r10
0x1400191c0  movzx   r8d, word ptr [r9]
0x1400191c4  mov     r9, [r9+8]
0x1400191c8  sub     r8w, ax
0x1400191cc  call    QuicTimestampFrameEncode
0x1400191d1  test    al, al
0x1400191d3  jz      loc_140019BC4
0x1400191d9  test    byte ptr [rsi+18Ah], 2
0x1400191e0  lea     r10, [rsi+160h]
0x1400191e7  jnz     short loc_1400191EC
0x1400191e9  mov     r10, rbx
0x1400191ec  mov     rcx, [rdi+20h]
0x1400191f0  movzx   eax, byte ptr [rdi+172h]
0x1400191f7  mov     r15d, [rsi+0D0h]
0x1400191fe  dec     r15d
0x140019201  mov     [rbp+57h+var_A8], r10
0x140019205  mov     r9, [rcx+8]
0x140019209  movzx   r8d, word ptr [rcx]
0x14001920d  sub     r8w, ax
0x140019211  mov     ecx, r15d
0x140019214  mov     [rbp+57h+var_98], r9
0x140019218  mov     [rsp+100h+var_E0], r9
0x14001921d  movzx   r9d, r8w
0x140019221  mov     [rbp+57h+var_CC], r8w
0x140019226  lea     r8, [rdi+17Ah]
0x14001922d  mov     [rbp+57h+var_70], rcx
0x140019231  lea     rcx, [rbp+57h+var_80]
0x140019235  mov     eax, r15d
0x140019238  shl     rax, 4
0x14001923c  add     rax, [rsi+0C8h]
0x140019243  mov     rdx, [rax+8]
0x140019247  mov     rbx, [rax]
0x14001924a  mov     rax, [rbp+57h+var_C8]
0x14001924e  dec     rbx
0x140019251  add     rbx, rdx
0x140019254  mov     [rbp+57h+var_78], rax
0x140019258  lea     rax, [rdx-1]
0x14001925c  mov     [rbp+57h+var_A0], rdx
0x140019260  mov     rdx, r10
0x140019263  mov     qword ptr [rbp+57h+var_68], rax
0x140019267  mov     [rbp+57h+var_80], rbx
0x14001926b  call    QuicAckHeaderEncode
0x140019270  test    al, al
0x140019272  jz      loc_140019BC4
0x140019278  mov     r9, [rbp+57h+var_98]
0x14001927c  test    r15d, r15d
0x14001927f  jz      short loc_1400192E0
0x140019281  sub     rbx, [rbp+57h+var_A0]
0x140019285  lea     eax, [r15-1]
0x140019289  movzx   r8d, [rbp+57h+var_CC]
0x14001928e  lea     rdx, [rdi+17Ah]
0x140019295  mov     r15d, eax
0x140019298  shl     rax, 4
0x14001929c  add     rax, [rsi+0C8h]
0x1400192a3  mov     rcx, [rax+8]
0x1400192a7  mov     rax, [rax]
0x1400192aa  dec     rax
0x1400192ad  mov     [rbp+57h+var_A0], rcx
0x1400192b1  add     rax, rcx
0x1400192b4  sub     rbx, rax
0x1400192b7  mov     [rbp+57h+var_C8], rax
0x1400192bb  lea     rax, [rcx-1]
0x1400192bf  dec     rbx
0x1400192c2  lea     rcx, [rbp+57h+var_98]
0x1400192c6  mov     [rbp+57h+var_98], rbx
0x1400192ca  mov     [rbp+57h+var_90], rax
0x1400192ce  call    QuicAckBlockEncode
0x1400192d3  test    al, al
0x1400192d5  jz      short loc_140019355
0x1400192d7  mov     rbx, [rbp+57h+var_C8]
0x1400192db  test    r15d, r15d
0x1400192de  jnz     short loc_140019281
0x1400192e0  mov     rcx, [rbp+57h+var_A8]
0x1400192e4  test    rcx, rcx
0x1400192e7  jz      short loc_140019302
0x1400192e9  movzx   r8d, [rbp+57h+var_CC]
0x1400192ee  lea     rdx, [rdi+17Ah]
0x1400192f5  call    QuicAckEcnEncode
0x1400192fa  test    al, al
0x1400192fc  jz      loc_140019BC4
0x140019302  cmp     word ptr [rsi+188h], 0
0x14001930a  jz      loc_14001938F
0x140019310  xor     ecx, ecx
0x140019312  mov     [rsi+188h], cx
0x140019319  mov     rbx, [rdi]
0x14001931c  lea     rax, [rbx+0AC8h]
0x140019323  mov     rdx, [rax]
0x140019326  test    rdx, rdx
0x140019329  jz      short loc_140019335
0x14001932b  cmp     word ptr [rdx+188h], 0
0x140019333  jnz     short loc_14001938F
0x140019335  inc     ecx
0x140019337  add     rax, 8
0x14001933b  cmp     ecx, 3
0x14001933e  jb      short loc_140019323
0x140019340  mov     eax, [rbx+0DA0h]
0x140019346  test    al, 1
0x140019348  jz      short loc_140019372
0x14001934a  and     eax, 0FFFFFFFEh
0x14001934d  mov     [rbx+0DA0h], eax
0x140019353  jmp     short loc_14001938F
0x140019355  lea     r8, a0; "0"
0x14001935c  mov     edx, 0F0h
0x140019361  lea     rcx, aCW1SMsquicSrcC_9; "C:\\__w\\1\\s\\msquic\\src\\core\\frame"...
0x140019368  call    CxPlatLogAssert
0x14001936d  jmp     loc_140019BC4
0x140019372  test    byte ptr [rbx+0D58h], 2
0x140019379  jz      short loc_14001938F
0x14001937b  mov     edx, 1
0x140019380  mov     rcx, rbx
0x140019383  call    QuicConnTimerCancel
0x140019388  and     byte ptr [rbx+0D58h], 0FDh
0x14001938f  or      byte ptr [rsi+18Ah], 1
0x140019396  mov     eax, [rsi+0D0h]
0x14001939c  movzx   r15d, [rbp+57h+var_CF]
0x1400193a1  dec     eax
0x1400193a3  shl     rax, 4
0x1400193a7  add     rax, [rsi+0C8h]
0x1400193ae  mov     rcx, [rax+8]
0x1400193b2  mov     rdx, [rax]
0x1400193b5  dec     rcx
0x1400193b8  add     rdx, rcx
0x1400193bb  mov     rcx, [rdi+198h]
0x1400193c2  movzx   eax, byte ptr [rcx+5Ah]
0x1400193c6  add     rax, 4
0x1400193ca  lea     rax, [rax+rax*2]
0x1400193ce  mov     [rcx+rax*8], rdx
0x1400193d2  mov     [rsi+178h], rdx
0x1400193d9  mov     rdx, [rdi+198h]
0x1400193e0  movzx   eax, byte ptr [rdx+5Ah]
0x1400193e4  lea     rcx, [rax+rax*2]
0x1400193e8  mov     word ptr [rdx+rcx*8+72h], 2
0x1400193ef  mov     rax, [rdi+198h]
0x1400193f6  inc     byte ptr [rax+5Ah]
0x1400193f9  movzx   ebx, [rbp+57h+var_D0]
0x1400193fd  test    bl, bl
0x1400193ff  jz      short loc_14001942D
0x140019401  mov     eax, [r14+48h]
0x140019405  test    al, 2
0x140019407  jz      short loc_14001942D
0x140019409  lea     rcx, [r13+0AE0h]
0x140019410  mov     rdx, rdi
0x140019413  call    QuicCryptoWriteFrames
0x140019418  test    al, al
0x14001941a  jz      short loc_14001942D
0x14001941c  mov     rax, [rdi+198h]
0x140019423  cmp     byte ptr [rax+5Ah], 0Ch
0x140019427  jz      loc_1400194F9
0x14001942d  mov     eax, [r14+48h]
0x140019431  test    al, 0Ch
0x140019433  jz      loc_140019507
0x140019439  mov     rcx, [r13+640h]
0x140019440  xor     r8d, r8d
0x140019443  shr     eax, 3
0x140019446  mov     ebx, r8d
0x140019449  and     al, 1
0x14001944b  test    byte ptr [r13+0F8h], 20h
0x140019453  movzx   eax, al
0x140019456  cmovz   ebx, eax
0x140019459  mov     rax, [r13+638h]
0x140019460  test    bl, bl
0x140019462  jz      short loc_140019472
0x140019464  test    r15b, r15b
0x140019467  jnz     short loc_140019472
0x140019469  lea     eax, [r8+0Bh]
0x14001946d  mov     ecx, r8d
0x140019470  xor     bl, bl
0x140019472  xor     edx, edx
0x140019474  mov     byte ptr [rbp+57h+var_80], bl
0x140019477  mov     dword ptr [rbp+57h+var_80+1], edx
0x14001947a  mov     word ptr [rbp+57h+var_80+5], dx
0x14001947e  mov     byte ptr [rbp+57h+var_80+7], dl
0x140019481  mov     [rbp+57h+var_78], rax
0x140019485  mov     [rbp+57h+var_70], r8
0x140019489  test    rcx, rcx
0x14001948c  jnz     short loc_140019494
0x14001948e  mov     qword ptr [rbp+57h+var_68], r8
0x140019492  jmp     short loc_1400194AC
0x140019494  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001949b  nop     dword ptr [rax+rax+00h]
0x1400194a0  inc     rax
0x1400194a3  cmp     [rcx+rax], dl
0x1400194a6  jnz     short loc_1400194A0
0x1400194a8  mov     qword ptr [rbp+57h+var_68], rax
0x1400194ac  mov     r9, [rdi+20h]
0x1400194b0  lea     rdx, [rdi+17Ah]
0x1400194b7  mov     qword ptr [rbp+57h+var_68+8], rcx
0x1400194bb  movzx   r8d, r12w
0x1400194bf  lea     rcx, [rbp+57h+var_80]
0x1400194c3  mov     r9, [r9+8]
0x1400194c7  call    QuicConnCloseFrameEncode
0x1400194cc  test    al, al
0x1400194ce  jz      short loc_140019500
0x1400194d0  or      byte ptr [rdi+170h], 80h
0x1400194d7  mov     rcx, [rdi+28h]
0x1400194db  mov     eax, [r13+0AFCh]
0x1400194e2  cmp     [rcx], eax
0x1400194e4  jnz     short loc_1400194EB
0x1400194e6  and     dword ptr [r14+48h], 0FFFFFFF3h
0x1400194eb  lea     edx, [rbx+1Ch]
0x1400194ee  xor     r8d, r8d
0x1400194f1  mov     rcx, rdi
0x1400194f4  call    QuicPacketBuilderAddFrame
0x1400194f9  mov     al, 1
0x1400194fb  jmp     loc_140019BD5
0x140019500  xor     al, al
0x140019502  jmp     loc_140019BD5
0x140019507  test    bl, bl
0x140019509  jz      loc_140019BC4
0x14001950f  bt      eax, 0Bh
0x140019513  jnb     loc_1400195DF
  ... truncated ...
```
