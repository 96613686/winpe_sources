# QuicSendFlush

- ea: `0x140016210`
- end: `0x140016e1d`
- name: `QuicSendFlush`
- size: `3085`
- prototype: ``
- caller_count: `3`
- callee_count: `37`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140014d80`
- `0x1400211bc`
- `0x14002b5c4`

## callees

- `0x14000d638`
- `0x14000f130`
- `0x14000f370`
- `0x14000f400`
- `0x140010820`
- `0x140016210`
- `0x140016e30`
- `0x140017580`
- `0x140018050`
- `0x140019040`
- `0x14001b418`
- `0x14001bcc8`
- `0x14001dfa4`
- `0x140021158`
- `0x1400217f0`
- `0x1400228b8`
- `0x1400262b4`
- `0x140029720`
- `0x14002ba00`
- `0x14002bac4`
- `0x14002ef50`
- `0x140030044`
- `0x1400300a8`
- `0x1400300b8`
- `0x1400300d4`
- `0x140030824`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ce00`
- `0x14003e884`
- `0x14003ec10`
- `0x14003fd84`
- `0x1400426e8`
- `0x140045620`
- `0x14004572c`
- `0x140049050`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001642f`
- `ntoskrnl!_snprintf_s` at `0x140016596`
- `ntoskrnl!_snprintf_s` at `0x140016c12`
- `ntoskrnl!_snprintf_s` at `0x140016cf9`
- `ntoskrnl!_snprintf_s` at `0x140016daa`
- `ntoskrnl!_snprintf_s` at `0x14001642f`
- `ntoskrnl!_snprintf_s` at `0x140016596`
- `ntoskrnl!_snprintf_s` at `0x140016c12`
- `ntoskrnl!_snprintf_s` at `0x140016cf9`
- `ntoskrnl!_snprintf_s` at `0x140016daa`
- `HAL!KeQueryPerformanceCounter` at `0x140016493`
- `HAL!KeQueryPerformanceCounter` at `0x140016493`

## string_xrefs

- `0x140016d8c`: `Flush complete flags=0x%x`

## pseudocode

```c
bool __fastcall QuicSendFlush(unsigned __int8 *a1)
{
  unsigned __int8 *v1; // r13
  unsigned __int8 *v2; // r15
  __int64 v3; // r14
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 EarliestExpirationTime; // rax
  __int64 v7; // rcx
  int v8; // r12d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rbx
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rdx
  unsigned int v23; // eax
  unsigned __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // r8
  char v28; // di
  __int64 v29; // rcx
  unsigned __int8 *v30; // r14
  unsigned int v31; // edi
  int v32; // ebx
  int v33; // ebx
  __int64 v34; // rsi
  bool v35; // r15
  int v36; // r11d
  __int64 v37; // rax
  int v38; // eax
  int v39; // edi
  _QWORD *v40; // r10
  __int64 v41; // rax
  __int64 v42; // r9
  int NextEncryptLevel; // eax
  int v44; // r9d
  char v45; // bl
  __int64 v46; // rax
  unsigned __int8 *v47; // rbx
  __int64 v48; // rdi
  char CanSendNow; // al
  int v50; // r14d
  unsigned __int8 *i; // rdx
  _QWORD *v52; // rax
  unsigned __int8 *v53; // rcx
  unsigned __int8 **v54; // rax
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // rdx
  bool v58; // bl
  char v59; // al
  __int16 v60; // r8
  __int64 v61; // rcx
  _QWORD *v62; // rax
  bool v63; // cc
  __int64 v64; // rdi
  char v65; // al
  unsigned __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rbx
  unsigned __int8 j; // di
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rdx
  _QWORD v74[100]; // [rsp+40h] [rbp-C0h] BYREF
  char DstBuf[128]; // [rsp+360h] [rbp+260h] BYREF

  v1 = a1 - 3416;
  v2 = a1;
  v3 = (__int64)(a1 - 3096);
  if ( !(unsigned __int8)CxPlatIsRouteReady(a1 - 3416, v3) )
    return 1;
  v4 = *((_QWORD *)v1 + 171);
  if ( v4 != -1 )
  {
    v5 = *((_QWORD *)v1 + 165);
    *((_QWORD *)v1 + 165) = -1;
    if ( v5 == v4 )
    {
      EarliestExpirationTime = QuicGetEarliestExpirationTime(v1);
      if ( EarliestExpirationTime != v4 )
      {
        v7 = *((_QWORD *)v1 + 8) + 88LL;
        *((_QWORD *)v1 + 171) = EarliestExpirationTime;
        QuicTimerWheelUpdateConnection(v7, v1);
      }
    }
  }
  v8 = 0;
  if ( (v1[278] & 3) != 0 )
  {
    v9 = QuicTimePlat();
    v10 = QuicTimePlatToUs64(v9);
    v12 = v1[278];
    if ( (v12 & 2) != 0 )
    {
      v11 = v10 - *((_QWORD *)v1 + 490);
      *((_QWORD *)v1 + 489) += v11;
      *((_QWORD *)v1 + 490) = 0;
    }
    if ( (v12 & 1) != 0 )
    {
      *((_QWORD *)v1 + 487) += v10 - *((_QWORD *)v1 + 488);
      *((_QWORD *)v1 + 488) = 0;
    }
    LOBYTE(v12) = v12 & 0xFC;
    v1[278] = v12;
    if ( (byte_14005C48A & 0x10) != 0 )
      McTemplateU0pu_EtwWriteTransfer(v11, QuicConnOutFlowBlocked, v1, v12);
  }
  if ( !*(_QWORD *)(v3 + 144) )
    return 1;
  v13 = QuicTimePlat();
  v14 = QuicTimePlatToUs64(v13);
  QuicMtuDiscoveryCheckSearchCompleteTimeout(v1, v14);
  if ( (*(_BYTE *)(v3 + 1) & 0x20) == 0 )
    *((_DWORD *)v2 + 18) &= ~0x80000000;
  if ( !*((_DWORD *)v2 + 18) && *((unsigned __int8 **)v2 + 10) == v2 + 80 )
    return 1;
  v15 = *((_DWORD *)v1 + 52);
  if ( v15 && (*v2 & 4) != 0 && v14 - *((_QWORD *)v2 + 2) >= (unsigned __int64)(unsigned int)(1000 * v15) )
    QuicConnRetireCurrentDestCid(v1, v3);
  v16 = *((_DWORD *)v2 + 18);
  if ( (v16 & 0x400) != 0 )
  {
    *((_DWORD *)v2 + 18) = v16 & 0xFFFFFBFF;
    QuicSendPathChallenges(v2);
  }
  memset(v74, 0, sizeof(v74));
  LOBYTE(v74[46]) &= 0x7Cu;
  v74[51] = &v74[52];
  v17 = *((_QWORD *)v1 + 160);
  v74[0] = v1;
  v74[1] = v3;
  BYTE2(v74[46]) = 16;
  HIDWORD(v74[47]) = 0;
  if ( !v17 )
  {
    if ( (byte_14005C48B & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "No src CID to send with");
      McTemplateU0ps_EtwWriteTransfer(v18, QuicConnLogWarning, v1, DstBuf);
    }
    return 1;
  }
  v74[2] = v17 - 24;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v21 = ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
      + (1000000LL * PerformanceCounter.LowPart
       + ((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
      / CxPlatPerfFreq.QuadPart;
  if ( (*v2 & 4) != 0 )
    v22 = v21 - *((_QWORD *)v1 + 429);
  else
    v22 = 0;
  v23 = (*((__int64 (__fastcall **)(unsigned __int8 *, unsigned __int64))v1 + 275))(v1 + 2168, v22);
  v26 = *(unsigned int *)(v3 + 208);
  v27 = v74[1];
  if ( v23 > (unsigned int)v26 )
    v23 = *(_DWORD *)(v3 + 208);
  *((_QWORD *)v1 + 429) = v21;
  *v2 |= 4u;
  LODWORD(v74[49]) = v23;
  v28 = *(_BYTE *)(v27 + 2);
  if ( (v28 & 0x18) == 0x10 )
    goto LABEL_40;
  if ( (v28 & 0x18) == 0 )
  {
    if ( *(_QWORD *)(v27 + 8) )
    {
      if ( !(unsigned __int8)CxPlatTimeAtOrBefore64(v14) )
      {
        *(_BYTE *)(v27 + 2) = v28 & 0xE7 | 8;
        if ( byte_14005C48B < 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "ECN unknown.");
          McTemplateU0ps_EtwWriteTransfer(v29, QuicConnLogInfo, v1, DstBuf);
        }
      }
    }
    else
    {
      v26 = *((_QWORD *)v1 + 63) + 250LL * *((_QWORD *)v1 + 213);
      v24 = v14 + 2 * (*((_QWORD *)v1 + 59) + 4 * v26) + *((_QWORD *)v1 + 59) + 4 * v26;
      *(_QWORD *)(v27 + 8) = v24;
    }
LABEL_40:
    LOBYTE(v74[46]) |= 0x40u;
  }
  if ( (byte_14005C48A & 8) != 0 )
    McTemplateU0pq_EtwWriteTransfer(v26, QuicConnFlushSend, v1, LODWORD(v74[49]));
  v30 = 0;
  while ( 2 )
  {
    v31 = *((_DWORD *)v1 + 132);
    if ( v31 < 0x4C )
    {
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Cannot send any more because of amplification protection");
        McTemplateU0ps_EtwWriteTransfer(v70, QuicConnLogVerbose, v1, DstBuf);
      }
LABEL_177:
      v50 = 0;
      v34 = v74[0];
      goto LABEL_168;
    }
    v24 = *((_DWORD *)v2 + 18) & 0x100F;
    if ( *((int *)v1 + 703) >= 3 )
      v24 = *((unsigned int *)v2 + 18);
    v32 = v24 & 0xFFFFBFFF;
    if ( v31 == -1 )
      v32 = v24;
    if ( !LODWORD(v74[49]) && !(unsigned __int8)QuicCongestionControlGetExemptions(v74[0] + 2168LL) )
    {
      v32 &= 0xDu;
      if ( !v32 )
      {
        if ( (*((unsigned __int8 (**)(void))v1 + 272))() )
        {
          QuicConnAddOutFlowBlockedReason(v1, 2);
          QuicConnTimerSet(v1, 0, 1000);
          v34 = v74[0];
          v50 = 2;
          goto LABEL_168;
        }
        goto LABEL_177;
      }
    }
    if ( (v32 & 0x7FFFFBFF) != 0 )
    {
      v33 = v32 & 0x7FFFFFFF;
      v34 = v74[0];
      v35 = (*v2 & 8) != 0;
      v36 = *(_DWORD *)(v74[0] + 2812LL);
      if ( (v33 & 0xC) != 0 )
      {
        if ( (*(_BYTE *)(v74[0] + 250LL) & 2) != 0 || v36 < 2 || SLOBYTE(v74[46]) < 0 )
          goto LABEL_63;
        v37 = 2936;
        if ( v36 != 3 )
          v37 = 2920;
        if ( !*(_QWORD *)(v37 + v74[0]) )
        {
LABEL_63:
          v39 = 0;
          if ( v36 != 1 )
            v39 = *(_DWORD *)(v74[0] + 2812LL);
        }
        else
        {
          v38 = 2;
          if ( v36 != 3 )
            v38 = 0;
          v39 = v38;
        }
      }
      else
      {
        v24 = 0;
        v39 = 0;
        if ( v36 >= 0 )
        {
          v40 = (_QWORD *)(v74[0] + 2920LL);
          do
          {
            if ( v39 != 1 && *v40 )
            {
              if ( v39 )
              {
                if ( v39 != 2 )
                  goto LABEL_86;
                v41 = 1;
                v42 = 1;
              }
              else
              {
                v42 = (unsigned int)v24;
                v41 = v24;
              }
              if ( (v33 & 1) != 0 && *(_WORD *)(*(_QWORD *)(v34 + 8 * v41 + 2760) + 392LL) )
                goto LABEL_87;
              if ( (v33 & 2) != 0 && (unsigned __int8)QuicCryptoHasPendingCryptoFrame(v34 + 2784, v24, v27, v42) )
              {
                NextEncryptLevel = QuicCryptoGetNextEncryptLevel();
                if ( v44 == NextEncryptLevel )
                  goto LABEL_87;
                v24 = 0;
              }
            }
            ++v39;
            ++v40;
          }
          while ( v39 <= v36 );
        }
        if ( (v33 & 0x1000) != 0 )
        {
          v39 = v36;
          if ( v36 == 1 )
            v39 = v24;
        }
        else
        {
          if ( !*(_QWORD *)(v34 + 2944) )
          {
            if ( (byte_14005C48B & 0x40) != 0 )
            {
              _snprintf_s(
                DstBuf,
                0x80u,
                0xFFFFFFFFFFFFFFFFuLL,
                "Failed to get packet type for control frames, 0x%x",
                v33);
              McTemplateU0ps_EtwWriteTransfer(v67, QuicConnLogWarning, v74[0], DstBuf);
              break;
            }
            goto LABEL_167;
          }
LABEL_86:
          v39 = 3;
        }
      }
LABEL_87:
      if ( (unsigned __int8)QuicPacketBuilderPrepare(v74, (unsigned int)v39, v35, 0) )
      {
        v2 = a1;
        v45 = QuicSendWriteFrames(a1, v74);
        goto LABEL_151;
      }
      break;
    }
    if ( v32 < 0 )
    {
      LOBYTE(v25) = 1;
      if ( (unsigned __int8)QuicPacketBuilderPrepare(v74, 3, 0, v25) )
      {
        v46 = v74[51];
        LOBYTE(v27) = 1;
        *((_DWORD *)v2 + 18) &= ~0x80000000;
        if ( *(_BYTE *)(v46 + 90) >= 0xCu
          || (v24 = v74[4], WORD1(v74[47]) >= *(_DWORD *)v74[4] - (unsigned int)BYTE2(v74[46])) )
        {
          v45 = 0;
          goto LABEL_152;
        }
        *(_BYTE *)(WORD1(v74[47]) + *(_QWORD *)(v74[4] + 8LL)) = 1;
        ++WORD1(v74[47]);
        v24 = v74[51];
        *(_WORD *)(v74[51] + 24LL * (unsigned __int8)(*(_BYTE *)(v74[51] + 90LL))++ + 114) = 1;
        *v2 &= ~8u;
LABEL_153:
        if ( *(_BYTE *)(v74[51] + 90LL) == 12
          || (v24 = WORD1(v74[47]), *(_DWORD *)v74[4] - (unsigned int)WORD1(v74[47]) < 0x40) )
        {
          if ( (_BYTE)v27 )
            goto LABEL_157;
          LOBYTE(v24) = 0;
          goto LABEL_158;
        }
        goto LABEL_159;
      }
      break;
    }
    if ( v30 )
      goto LABEL_116;
    v47 = (unsigned __int8 *)*((_QWORD *)v2 + 10);
    if ( v47 == v2 + 80 )
    {
LABEL_107:
      v34 = v74[0];
      v50 = 0;
      goto LABEL_168;
    }
    while ( 1 )
    {
      v48 = *((_QWORD *)v47 + 2);
      v30 = v47 - 56;
      if ( *(_DWORD *)(v48 + 2812) == 3 )
        break;
      if ( *(_QWORD *)(v48 + 2928) )
      {
        LOBYTE(v24) = 1;
        CanSendNow = QuicStreamCanSendNow(v47 - 56, v24);
        goto LABEL_105;
      }
LABEL_106:
      v47 = *(unsigned __int8 **)v47;
      if ( v47 == v2 + 80 )
        goto LABEL_107;
    }
    v24 = (*((_QWORD *)v30 + 10) >> 2) + 1LL;
    CanSendNow = *(_QWORD *)(v48 + 24 * (*((_QWORD *)v30 + 10) & 3LL) + 2032) >= v24
              && ((v30[96] & 0xAF) != 0 || (unsigned __int8)QuicStreamSendCanWriteDataFrames(v47 - 56) != 0);
LABEL_105:
    if ( !CanSendNow )
      goto LABEL_106;
    if ( (*(v2 - 3165) & 8) != 0 )
    {
      for ( i = *(unsigned __int8 **)v47; i != v2 + 80; i = *(unsigned __int8 **)i )
      {
        if ( *((_WORD *)v30 + 208) > *((_WORD *)i + 180) )
          break;
      }
      if ( *((unsigned __int8 **)i + 1) != v47 )
      {
        v52 = (_QWORD *)*((_QWORD *)v47 + 1);
        v53 = *(unsigned __int8 **)v47;
        *v52 = *(_QWORD *)v47;
        *((_QWORD *)v53 + 1) = v52;
        v54 = (unsigned __int8 **)*((_QWORD *)i + 1);
        *(_QWORD *)v47 = i;
        *((_QWORD *)v47 + 1) = v54;
        *v54 = v47;
        *((_QWORD *)i + 1) = v47;
      }
      v8 = 8;
    }
    else
    {
      v8 = -1;
    }
LABEL_116:
    v55 = *v2;
    LOBYTE(v55) = (v55 & 8) != 0;
    if ( !*(_QWORD *)(v74[0] + 2928LL) || *(_QWORD *)(v74[0] + 2944LL) )
      v56 = 3;
    else
      v56 = 1;
    if ( !(unsigned __int8)QuicPacketBuilderPrepare(v74, v56, v55, 0) )
      break;
    v57 = *(_QWORD *)&v1[8 * SHIDWORD(v74[46]) + 2760];
    v58 = LOBYTE(v74[47]) != (*((_DWORD *)v1 + 909) == -817679509) + 1
       && (*(_BYTE *)(v57 + 394) & 1) == 0
       && *(_DWORD *)(v57 + 208)
       && (unsigned __int8)QuicAckTrackerAckFrameEncode(v57 + 48, v74);
    v59 = QuicStreamSendWrite(v30, v74);
    v60 = *((_WORD *)v30 + 48);
    v45 = v59 | v58;
    if ( v60 || (v61 = *((_QWORD *)v30 + 7)) == 0 )
    {
      if ( v45 )
      {
        if ( !--v8 )
          goto LABEL_150;
      }
      v64 = *((_QWORD *)v30 + 9);
      if ( *(_DWORD *)(v64 + 2812) == 3 )
      {
        v24 = (*((_QWORD *)v30 + 10) >> 2) + 1LL;
        if ( *(_QWORD *)(v64 + 24 * (*((_QWORD *)v30 + 10) & 3LL) + 2032) < v24 )
        {
          v65 = 0;
          goto LABEL_149;
        }
        if ( (v60 & 0xAF) != 0 || (v60 & 0x20) != 0 || *((_QWORD *)v30 + 29) < *((_QWORD *)v30 + 30) )
          goto LABEL_143;
        v66 = *((_QWORD *)v30 + 28);
        if ( v66 == *((_QWORD *)v30 + 20) )
        {
          if ( (v60 & 0x40) != 0 )
          {
LABEL_143:
            v65 = 1;
            goto LABEL_149;
          }
        }
        else if ( v66 < *((_QWORD *)v30 + 23) && *(_QWORD *)(v64 + 3472) < *(_QWORD *)(v64 + 3456) )
        {
          goto LABEL_143;
        }
        v65 = 0;
      }
      else
      {
        if ( !*(_QWORD *)(v64 + 2928) )
          goto LABEL_150;
        LOBYTE(v24) = 1;
        v65 = QuicStreamCanSendNow(v30, v24);
      }
LABEL_149:
      if ( !v65 )
        goto LABEL_150;
      goto LABEL_151;
    }
    v62 = (_QWORD *)*((_QWORD *)v30 + 8);
    *v62 = v61;
    *(_QWORD *)(v61 + 8) = v62;
    v63 = *((_QWORD *)v30 + 2) <= 0LL;
    *((_QWORD *)v30 + 7) = 0;
    if ( v63 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\stream.h", 732, "Stream->RefCount > 0");
    if ( (unsigned __int8)CxPlatRefDecrement(v30 + 16) )
      QuicStreamFree(v30);
LABEL_150:
    v30 = 0;
LABEL_151:
    v27 = 0;
LABEL_152:
    *v2 &= ~8u;
    if ( v45 )
      goto LABEL_153;
LABEL_157:
    LOBYTE(v24) = 1;
LABEL_158:
    if ( (unsigned __int8)QuicPacketBuilderFinalize(v74, v24) )
    {
LABEL_159:
      if ( v74[3] || BYTE1(v74[46]) < 0x28u )
        continue;
    }
    break;
  }
  v34 = v74[0];
LABEL_167:
  v50 = 1;
LABEL_168:
  if ( v74[3] )
  {
    LOBYTE(v24) = 1;
    QuicPacketBuilderFinalize(v74, v24);
    v34 = v74[0];
  }
  if ( (v74[46] & 1) != 0 && (v74[46] & 2) != 0 )
  {
    QuicLossDetectionUpdateTimer(v34 + 2632, 0);
    v34 = v74[0];
  }
  v68 = v74[51];
  for ( j = 0; j < *(_BYTE *)(v68 + 90); ++j )
  {
    switch ( *(_WORD *)(v68 + 24LL * j + 114) )
    {
      case 4:
      case 5:
      case 8:
      case 0x11:
      case 0x15:
      case 0x21:
        QuicStreamSentMetadataDecrement(*(_QWORD *)(v68 + 24LL * j + 96));
        break;
      case 0x30:
      case 0x31:
        if ( *(_QWORD *)(v68 + 24 * (j + 4LL)) )
          QuicDatagramIndicateSendStateChange(v34, v68 + 24 * (j + 4LL), 3);
        break;
      default:
        continue;
    }
  }
  memset(&v74[22], 0, 0x80u);
  if ( (byte_14005C48C & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Flush complete flags=0x%x", *((_DWORD *)a1 + 18));
    McTemplateU0ps_EtwWriteTransfer(v71, QuicConnLogVerbose, v1, DstBuf);
  }
  if ( v50 == 1 )
  {
    QuicConnAddOutFlowBlockedReason(v1, 1);
    QuicSendQueueFlush(a1, 12);
    v72 = BYTE1(v74[46]);
    if ( (unsigned int)BYTE1(v74[46]) + 1 > v1[281] )
    {
      LOBYTE(v72) = BYTE1(v74[46]) + 1;
      QuicConnUpdatePeerPacketTolerance(v1, v72);
    }
  }
  QuicDatagramCancelBlocked(v1);
  return v50 != 1;
}

```

## disassembly

```asm
0x140016210  mov     [rsp-8+arg_10], rbx
0x140016215  mov     [rsp-8+arg_18], rdi
0x14001621a  push    rbp
0x14001621b  push    r12
0x14001621d  push    r13
0x14001621f  push    r14
0x140016221  push    r15
0x140016223  lea     rbp, [rsp-2F0h]
0x14001622b  sub     rsp, 3F0h
0x140016232  mov     rax, cs:__security_cookie
0x140016239  xor     rax, rsp
0x14001623c  mov     [rbp+310h+var_30], rax
0x140016243  lea     r13, [rcx-0D58h]
0x14001624a  mov     [rsp+410h+var_3D8], rcx
0x14001624f  mov     r15, rcx
0x140016252  lea     r14, [r13+140h]
0x140016259  mov     rdx, r14
0x14001625c  mov     rcx, r13
0x14001625f  call    CxPlatIsRouteReady
0x140016264  test    al, al
0x140016266  jz      loc_140016451
0x14001626c  mov     rdi, [r13+558h]
0x140016273  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140016277  jz      short loc_1400162B4
0x140016279  mov     rax, [r13+528h]
0x140016280  mov     qword ptr [r13+528h], 0FFFFFFFFFFFFFFFFh
0x14001628b  cmp     rax, rdi
0x14001628e  jnz     short loc_1400162B4
0x140016290  mov     rcx, r13
0x140016293  call    QuicGetEarliestExpirationTime
0x140016298  cmp     rax, rdi
0x14001629b  jz      short loc_1400162B4
0x14001629d  mov     rcx, [r13+40h]
0x1400162a1  mov     rdx, r13
0x1400162a4  add     rcx, 58h ; 'X'
0x1400162a8  mov     [r13+558h], rax
0x1400162af  call    QuicTimerWheelUpdateConnection
0x1400162b4  xor     r12d, r12d
0x1400162b7  test    byte ptr [r13+116h], 3
0x1400162bf  jz      short loc_140016332
0x1400162c1  call    QuicTimePlat
0x1400162c6  mov     rcx, rax
0x1400162c9  call    QuicTimePlatToUs64
0x1400162ce  movzx   r9d, byte ptr [r13+116h]
0x1400162d6  test    r9b, 2
0x1400162da  jz      short loc_1400162F4
0x1400162dc  mov     rcx, rax
0x1400162df  sub     rcx, [r13+0F50h]
0x1400162e6  add     [r13+0F48h], rcx
0x1400162ed  mov     [r13+0F50h], r12
0x1400162f4  test    r9b, 1
0x1400162f8  jz      short loc_14001630F
0x1400162fa  sub     rax, [r13+0F40h]
0x140016301  add     [r13+0F38h], rax
0x140016308  mov     [r13+0F40h], r12
0x14001630f  and     r9b, 0FCh
0x140016313  mov     [r13+116h], r9b
0x14001631a  test    cs:byte_14005C48A, 10h
0x140016321  jz      short loc_140016332
0x140016323  mov     r8, r13
0x140016326  lea     rdx, QuicConnOutFlowBlocked
0x14001632d  call    McTemplateU0pu_EtwWriteTransfer
0x140016332  cmp     [r14+90h], r12
0x140016339  jz      loc_140016451
0x14001633f  call    QuicTimePlat
0x140016344  mov     rcx, rax
0x140016347  call    QuicTimePlatToUs64
0x14001634c  mov     rdx, rax
0x14001634f  mov     rcx, r13
0x140016352  mov     rbx, rax
0x140016355  call    QuicMtuDiscoveryCheckSearchCompleteTimeout
0x14001635a  test    byte ptr [r14+1], 20h
0x14001635f  jnz     short loc_140016369
0x140016361  and     dword ptr [r15+48h], 7FFFFFFFh
0x140016369  cmp     [r15+48h], r12d
0x14001636d  jnz     short loc_14001637C
0x14001636f  lea     rax, [r15+50h]
0x140016373  cmp     [rax], rax
0x140016376  jz      loc_140016451
0x14001637c  mov     ecx, [r13+0D0h]
0x140016383  test    ecx, ecx
0x140016385  jz      short loc_1400163AA
0x140016387  test    byte ptr [r15], 4
0x14001638b  jz      short loc_1400163AA
0x14001638d  imul    ecx, 3E8h
0x140016393  mov     rdx, rbx
0x140016396  sub     rdx, [r15+10h]
0x14001639a  cmp     rdx, rcx
0x14001639d  jb      short loc_1400163AA
0x14001639f  mov     rdx, r14
0x1400163a2  mov     rcx, r13
0x1400163a5  call    QuicConnRetireCurrentDestCid
0x1400163aa  mov     eax, [r15+48h]
0x1400163ae  bt      eax, 0Ah
0x1400163b2  jnb     short loc_1400163C4
0x1400163b4  btr     eax, 0Ah
0x1400163b8  mov     rcx, r15
0x1400163bb  mov     [r15+48h], eax
0x1400163bf  call    QuicSendPathChallenges
0x1400163c4  xor     edx, edx; Val
0x1400163c6  lea     rcx, [rsp+410h+var_3D0]; void *
0x1400163cb  mov     r8d, 320h; Size
0x1400163d1  call    memset
0x1400163d6  and     [rbp+310h+var_260], 7Ch
0x1400163dd  lea     rax, [rbp+310h+var_230]
0x1400163e4  mov     [rbp+310h+var_238], rax
0x1400163eb  mov     rax, [r13+500h]
0x1400163f2  mov     [rsp+410h+var_3D0], r13
0x1400163f7  mov     [rsp+410h+var_3C8], r14
0x1400163fc  mov     [rbp+310h+var_25E], 10h
0x140016403  mov     [rbp+310h+var_254], r12d
0x14001640a  test    rax, rax
0x14001640d  jnz     short loc_140016480
0x14001640f  test    cs:byte_14005C48B, 40h
0x140016416  jz      short loc_140016451
0x140016418  lea     r9, aNoSrcCidToSend; "No src CID to send with"
0x14001641f  mov     edx, 80h; SizeInBytes
0x140016424  lea     r8, [rax-1]; MaxCount
0x140016428  lea     rcx, [rbp+310h+DstBuf]; DstBuf
0x14001642f  call    cs:__imp__snprintf_s
0x140016436  nop     dword ptr [rax+rax+00h]
0x14001643b  lea     r9, [rbp+310h+DstBuf]
0x140016442  mov     r8, r13
0x140016445  lea     rdx, QuicConnLogWarning
0x14001644c  call    McTemplateU0ps_EtwWriteTransfer
0x140016451  mov     al, 1
0x140016453  mov     rcx, [rbp+310h+var_30]
0x14001645a  xor     rcx, rsp; StackCookie
0x14001645d  call    __security_check_cookie
0x140016462  lea     r11, [rsp+410h+var_20]
0x14001646a  mov     rbx, [r11+40h]
0x14001646e  mov     rdi, [r11+48h]
0x140016472  mov     rsp, r11
0x140016475  pop     r15
0x140016477  pop     r14
0x140016479  pop     r13
0x14001647b  pop     r12
0x14001647d  pop     rbp
0x14001647e  retn
0x140016480  add     rax, 0FFFFFFFFFFFFFFE8h
0x140016484  mov     [rsp+410h+arg_8], rsi
0x14001648c  xor     ecx, ecx; PerformanceFrequency
0x14001648e  mov     [rsp+410h+var_3C0], rax
0x140016493  call    cs:__imp_KeQueryPerformanceCounter
0x14001649a  nop     dword ptr [rax+rax+00h]
0x14001649f  mov     rdi, qword ptr cs:CxPlatPerfFreq
0x1400164a6  xor     edx, edx
0x1400164a8  mov     rcx, rax
0x1400164ab  shr     rax, 20h
0x1400164af  imul    r8, rax, 0F4240h
0x1400164b6  mov     rax, r8
0x1400164b9  div     rdi
0x1400164bc  mov     rax, rdx
0x1400164bf  mov     edx, ecx
0x1400164c1  imul    rcx, rdx, 0F4240h
0x1400164c8  shl     rax, 20h
0x1400164cc  xor     edx, edx
0x1400164ce  add     rax, rcx
0x1400164d1  div     rdi
0x1400164d4  xor     edx, edx
0x1400164d6  mov     rsi, rax
0x1400164d9  mov     rax, r8
0x1400164dc  movzx   r8d, byte ptr [r15]
0x1400164e0  div     rdi
0x1400164e3  shr     r8b, 2
0x1400164e7  shl     rax, 20h
0x1400164eb  add     rsi, rax
0x1400164ee  and     r8b, 1
0x1400164f2  jz      short loc_140016500
0x1400164f4  mov     rdx, rsi
0x1400164f7  sub     rdx, [r13+0D68h]
0x1400164fe  jmp     short loc_140016503
0x140016500  mov     rdx, r12
0x140016503  lea     rcx, [r13+878h]
0x14001650a  mov     rax, [rcx+20h]
0x14001650e  call    _guard_dispatch_icall
0x140016513  mov     ecx, [r14+0D0h]
0x14001651a  cmp     eax, ecx
0x14001651c  mov     r8, [rsp+410h+var_3C8]
0x140016521  cmova   eax, ecx
0x140016524  mov     [r13+0D68h], rsi
0x14001652b  or      byte ptr [r15], 4
0x14001652f  mov     [rbp+310h+var_248], eax
0x140016535  movzx   edi, byte ptr [r8+2]
0x14001653a  movzx   eax, dil
0x14001653e  and     al, 18h
0x140016540  cmp     al, 10h
0x140016542  jz      loc_1400165E2
0x140016548  test    al, al
0x14001654a  jnz     loc_1400165E9
0x140016550  mov     rdx, [r8+8]
0x140016554  test    rdx, rdx
0x140016557  jz      short loc_1400165BA
0x140016559  mov     rcx, rbx
0x14001655c  call    CxPlatTimeAtOrBefore64
0x140016561  test    al, al
0x140016563  jnz     short loc_1400165E2
0x140016565  and     dil, 0EFh
0x140016569  or      dil, 8
0x14001656d  mov     [r8+2], dil
0x140016571  movzx   eax, cs:byte_14005C48B
0x140016578  test    al, al
0x14001657a  jns     short loc_1400165E2
0x14001657c  lea     r9, aEcnUnknown; "ECN unknown."
0x140016583  mov     edx, 80h; SizeInBytes
0x140016588  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001658f  lea     rcx, [rbp+310h+DstBuf]; DstBuf
0x140016596  call    cs:__imp__snprintf_s
0x14001659d  nop     dword ptr [rax+rax+00h]
0x1400165a2  lea     r9, [rbp+310h+DstBuf]
0x1400165a9  mov     r8, r13
0x1400165ac  lea     rdx, QuicConnLogInfo
0x1400165b3  call    McTemplateU0ps_EtwWriteTransfer
0x1400165b8  jmp     short loc_1400165E2
0x1400165ba  imul    rcx, [r13+6A8h], 0FAh
0x1400165c5  mov     rax, [r13+1D8h]
0x1400165cc  add     rcx, [r13+1F8h]
0x1400165d3  lea     rdx, [rax+rcx*4]
0x1400165d7  lea     rax, [rbx+rdx*2]
0x1400165db  add     rdx, rax
0x1400165de  mov     [r8+8], rdx
0x1400165e2  or      [rbp+310h+var_260], 40h
0x1400165e9  test    cs:byte_14005C48A, 8
0x1400165f0  jz      short loc_140016608
0x1400165f2  mov     r9d, [rbp+310h+var_248]
0x1400165f9  lea     rdx, QuicConnFlushSend
0x140016600  mov     r8, r13
0x140016603  call    McTemplateU0pq_EtwWriteTransfer
0x140016608  xor     esi, esi
0x14001660a  mov     [rsp+410h+var_3DC], 1
0x140016612  mov     r14d, esi
0x140016615  nop     word ptr [rax+rax+00000000h]
0x140016620  mov     edi, [r13+210h]
0x140016627  cmp     edi, 4Ch ; 'L'
0x14001662a  jb      loc_140016CD6
0x140016630  mov     ecx, [r15+48h]
0x140016634  mov     edx, ecx
0x140016636  and     edx, 100Fh
0x14001663c  cmp     dword ptr [r13+0AFCh], 3
0x140016644  cmovge  edx, ecx
0x140016647  mov     ebx, edx
0x140016649  btr     ebx, 0Eh
0x14001664d  cmp     edi, 0FFFFFFFFh
0x140016650  cmovz   ebx, edx
0x140016653  cmp     [rbp+310h+var_248], 0
0x14001665a  ja      short loc_14001667A
0x14001665c  mov     rcx, [rsp+410h+var_3D0]
0x140016661  add     rcx, 878h
0x140016668  call    QuicCongestionControlGetExemptions
0x14001666d  test    al, al
0x14001666f  jnz     short loc_14001667A
0x140016671  and     ebx, 0Dh
0x140016674  jz      loc_140016BA9
0x14001667a  mov     [rsp+410h+var_3E0], 0
0x14001667f  test    ebx, 7FFFFBFFh
0x140016685  jz      loc_1400167E8
0x14001668b  movzx   r15d, byte ptr [r15]
0x14001668f  btr     ebx, 1Fh
0x140016693  mov     rsi, [rsp+410h+var_3D0]
0x140016698  shr     r15b, 3
0x14001669c  and     r15b, 1
0x1400166a0  mov     r11d, [rsi+0AFCh]
0x1400166a7  test    bl, 0Ch
0x1400166aa  jz      short loc_14001670E
0x1400166ac  test    byte ptr [rsi+0FAh], 2
0x1400166b3  jnz     short loc_1400166FD
0x1400166b5  cmp     r11d, 2
0x1400166b9  jl      short loc_1400166FD
0x1400166bb  test    [rbp+310h+var_260], 80h
0x1400166c2  jnz     short loc_1400166FD
0x1400166c4  cmp     r11d, 3
0x1400166c8  mov     eax, 0B78h
0x1400166cd  mov     ecx, 0B68h
0x1400166d2  cmovnz  eax, ecx
0x1400166d5  cmp     qword ptr [rax+rsi], 0
0x1400166da  jz      short loc_1400166FD
0x1400166dc  cmp     r11d, 3
0x1400166e0  mov     ecx, 0
0x1400166e5  mov     eax, 2
0x1400166ea  mov     edi, ecx
0x1400166ec  cmovnz  eax, ecx
0x1400166ef  cmp     eax, 1
0x1400166f2  mov     r11d, eax
0x1400166f5  cmovnz  edi, eax
0x1400166f8  jmp     loc_1400167B3
0x1400166fd  xor     ecx, ecx
0x1400166ff  cmp     r11d, 1
0x140016703  mov     edi, ecx
0x140016705  cmovnz  edi, r11d
0x140016709  jmp     loc_1400167B3
0x14001670e  xor     edx, edx
0x140016710  mov     edi, edx
0x140016712  test    r11d, r11d
0x140016715  js      short loc_14001678E
0x140016717  lea     r10, [rsi+0B68h]
0x14001671e  xchg    ax, ax
0x140016720  cmp     edi, 1
0x140016723  jz      short loc_140016783
0x140016725  cmp     qword ptr [r10], 0
0x140016729  jz      short loc_140016783
  ... truncated ...
```
