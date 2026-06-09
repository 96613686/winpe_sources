# QuicLossDetectionProcessAckBlocks

- ea: `0x140013b30`
- end: `0x1400145b0`
- name: `QuicLossDetectionProcessAckBlocks`
- size: `2688`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400108c0`

## callees

- `0x14000d638`
- `0x14000f130`
- `0x140013550`
- `0x140013a40`
- `0x140013b30`
- `0x140018ee0`
- `0x14001e790`
- `0x14003020c`
- `0x1400302e0`
- `0x140030300`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003ec10`
- `0x14003fd84`
- `0x14004275c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140013d0a`
- `ntoskrnl!_snprintf_s` at `0x140013fac`
- `ntoskrnl!_snprintf_s` at `0x1400141fe`
- `ntoskrnl!_snprintf_s` at `0x1400142e7`
- `ntoskrnl!_snprintf_s` at `0x140013d0a`
- `ntoskrnl!_snprintf_s` at `0x140013fac`
- `ntoskrnl!_snprintf_s` at `0x1400141fe`
- `ntoskrnl!_snprintf_s` at `0x1400142e7`
- `HAL!KeQueryPerformanceCounter` at `0x140013b98`
- `HAL!KeQueryPerformanceCounter` at `0x140013b98`

## string_xrefs

- `0x1400142d8`: `Updated Rtt=%u.%03u ms, Var=%u.%03u 1Way=%u.%03u ms`
- `0x140013cef`: `[%c][TX][%llu] Spurious loss detected`

## pseudocode

```c
__int64 __fastcall QuicLossDetectionProcessAckBlocks(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int64 a5,
        __int64 a6,
        _BYTE *a7,
        _QWORD *a8)
{
  int v9; // edi
  _QWORD *v10; // rsi
  LARGE_INTEGER PerformanceCounter; // rax
  _QWORD *v12; // r13
  int v13; // r8d
  _QWORD *v14; // r9
  _QWORD *v15; // r12
  unsigned int v16; // ecx
  _QWORD *v17; // rbx
  __int64 result; // rax
  _QWORD *v19; // rdx
  _QWORD *v20; // rcx
  _QWORD *v21; // r14
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  unsigned __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rax
  _QWORD *v30; // r8
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rax
  _QWORD *v33; // r14
  bool v34; // r12
  _QWORD *v35; // r13
  _QWORD *v36; // rbx
  __int64 v37; // rcx
  int v38; // eax
  unsigned __int64 v39; // rdi
  int v40; // r9d
  __int64 v41; // rcx
  char v42; // al
  char v43; // al
  unsigned __int64 v44; // rax
  __int64 v45; // rdi
  unsigned __int64 v46; // r8
  char v47; // r11
  unsigned __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rbx
  __int64 v51; // r9
  char v52; // al
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rdx
  unsigned __int64 v55; // rcx
  __int64 v56; // rdx
  unsigned __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // r9
  unsigned __int64 v61; // rax
  signed __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rcx
  int v65; // edx
  int v66; // r9d
  __int64 v67; // rcx
  unsigned __int64 v68; // rdi
  unsigned __int64 v69; // rbx
  __int64 v70; // rdx
  __int64 v71; // rcx
  int v72; // ecx
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  _QWORD *v76; // rcx
  __int64 v77; // [rsp+20h] [rbp-E0h]
  bool v78; // [rsp+50h] [rbp-B0h]
  bool v79; // [rsp+51h] [rbp-AFh]
  char v80; // [rsp+52h] [rbp-AEh]
  int v83; // [rsp+60h] [rbp-A0h]
  _QWORD *v84; // [rsp+68h] [rbp-98h]
  __int64 v85; // [rsp+68h] [rbp-98h]
  unsigned int v86; // [rsp+70h] [rbp-90h]
  unsigned __int64 v87; // [rsp+70h] [rbp-90h]
  unsigned __int64 v88; // [rsp+78h] [rbp-88h]
  __int64 v89; // [rsp+80h] [rbp-80h]
  __int64 v90; // [rsp+80h] [rbp-80h]
  __int64 v91; // [rsp+88h] [rbp-78h]
  _QWORD *v92; // [rsp+90h] [rbp-70h] BYREF
  __int64 v93; // [rsp+98h] [rbp-68h]
  _QWORD v94[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v95[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v96; // [rsp+B8h] [rbp-48h]
  __int64 v97; // [rsp+C0h] [rbp-40h]
  __int64 v98; // [rsp+C8h] [rbp-38h]
  int v99; // [rsp+D0h] [rbp-30h]
  int v100; // [rsp+D4h] [rbp-2Ch]
  _QWORD *v101; // [rsp+D8h] [rbp-28h]
  __int64 v102; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v103; // [rsp+E8h] [rbp-18h]
  __int64 v104; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v105; // [rsp+F8h] [rbp-8h]
  int v106; // [rsp+100h] [rbp+0h]
  char v107; // [rsp+104h] [rbp+4h]
  __int16 v108; // [rsp+105h] [rbp+5h]
  char v109; // [rsp+107h] [rbp+7h]
  char DstBuf[128]; // [rsp+130h] [rbp+30h] BYREF

  v93 = a3;
  v9 = 0;
  v94[0] = a7;
  v10 = (_QWORD *)(a1 - 2632);
  v92 = 0;
  v84 = &v92;
  v83 = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v12 = (_QWORD *)(a1 + 88);
  v88 = -1;
  v78 = 0;
  v13 = a4;
  v14 = (_QWORD *)(a1 + 104);
  v15 = (_QWORD *)(a1 + 104);
  v91 = ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
      + (1000000LL * PerformanceCounter.LowPart
       + ((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
      / CxPlatPerfFreq.QuadPart;
  *a7 = 0;
  v16 = 0;
  v89 = 0;
  v17 = 0;
  v80 = 0;
  v79 = 0;
  while ( 1 )
  {
    result = a6;
    if ( v16 >= *(_DWORD *)(a6 + 8) )
      break;
    v19 = (_QWORD *)(*(_QWORD *)a6 + 16LL * v16);
    v86 = v16 + 1;
    if ( !v19 )
      break;
    v20 = (_QWORD *)*v15;
    v21 = v19;
    if ( *v15 && *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL) >= *v19 )
    {
      do
      {
        if ( v20[2] >= *v19 )
          break;
        v15 = v20;
        v20 = (_QWORD *)*v20;
      }
      while ( v20 );
      v22 = (_QWORD *)*v15;
      v23 = v15;
      if ( *v15 )
      {
        do
        {
          v24 = v22[2];
          if ( v24 > *v21 + v21[1] - 1LL )
            break;
          if ( byte_14005C48E < 0 )
          {
            if ( a1 == 2632 )
              v25 = 45;
            else
              v25 = PacketLogPrefix[*(_DWORD *)(a1 - 2632) == 4];
            LODWORD(v77) = v25;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%c][TX][%llu] Spurious loss detected", v77, v24);
            McTemplateU0s_EtwWriteTransfer(v26, QuicLogVerbose, DstBuf);
          }
          ++v10[467];
          _InterlockedDecrement64((volatile signed __int64 *)(v10[9] + 2280LL));
          v23 = (_QWORD *)*v23;
          v22 = (_QWORD *)*v23;
        }
        while ( *v23 );
        v14 = (_QWORD *)(a1 + 104);
        if ( v15 != v23 )
        {
          v27 = v84;
          v84 = v23;
          *v27 = *v15;
          *v15 = *v23;
          *v23 = 0;
          if ( v23 == *(_QWORD **)(a1 + 112) )
            *(_QWORD *)(a1 + 112) = v15;
        }
      }
      if ( !*v14 )
      {
        if ( (unsigned __int8)QuicCongestionControlOnSpuriousCongestionEvent(v10 + 271) )
          QuicSendQueueFlush(v10 + 427, 6);
        v14 = (_QWORD *)(a1 + 104);
      }
      v9 = v83;
    }
    v28 = (_QWORD *)*v12;
    if ( *v12 )
    {
      do
      {
        if ( v28[2] >= *v21 )
          break;
        v12 = v28;
        v28 = (_QWORD *)*v28;
      }
      while ( v28 );
      v29 = (_QWORD *)*v12;
      v30 = v12;
      if ( *v12 )
      {
        do
        {
          if ( v29[2] > (unsigned __int64)(*v21 + v21[1] - 1LL) )
            break;
          v17 = v29;
          if ( (v29[11] & 4) != 0 )
          {
            --*(_DWORD *)a1;
            v17 = (_QWORD *)*v30;
            v9 += *(unsigned __int16 *)(*v30 + 40LL);
          }
          v29 = (_QWORD *)*v17;
          v30 = v17;
        }
        while ( *v17 );
        v83 = v9;
        if ( v12 != v30 )
        {
          v31 = v84;
          v84 = v30;
          *v31 = *v12;
          *v12 = *v30;
          *v30 = 0;
          if ( v30 == *(_QWORD **)(a1 + 96) )
            *(_QWORD *)(a1 + 96) = v12;
        }
      }
    }
    v16 = v86;
    v13 = a4;
    if ( v17 )
    {
      v32 = v17[2];
      if ( *(_QWORD *)(a1 + 8) <= v32 )
      {
        *(_QWORD *)(a1 + 8) = v32;
        if ( a4 > *(_DWORD *)(a1 + 16) )
          *(_DWORD *)(a1 + 16) = a4;
        v80 = 1;
        v16 = v86;
        v78 = (v17[11] & 4) != 0;
        v79 = *(_BYTE *)a2 != *((_BYTE *)v17 + 42);
        v89 = v17[4];
      }
    }
  }
  v33 = v92;
  if ( v92 )
  {
    v87 = 0;
    v34 = 0;
    v85 = 0;
    v35 = v92;
    while ( 1 )
    {
      v36 = v35;
      v35 = (_QWORD *)*v35;
      v37 = v36[11] & 3;
      if ( (v36[11] & 3) != 0 )
      {
        v37 = (unsigned int)(v37 - 1);
        v38 = (_DWORD)v37 == 1 ? 1 : 2;
      }
      else
      {
        v38 = 0;
      }
      if ( v38 != v13 )
        break;
      v39 = v91 - v36[4];
      if ( byte_14005C48E < 0 )
      {
        if ( a1 == 2632 )
          v40 = 45;
        else
          v40 = PacketLogPrefix[*(_DWORD *)(a1 - 2632) == 4];
        LODWORD(v77) = v40;
        _snprintf_s(
          v95,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "[%c][TX][%llu] ACKed (%u.%03u ms)",
          v77,
          v36[2],
          v39 / 0x3E8,
          v39 % 0x3E8);
        McTemplateU0s_EtwWriteTransfer(v41, QuicLogVerbose, v95);
      }
      if ( (byte_14005C48B & 8) != 0 )
      {
        v42 = v36[11] & 3;
        if ( v42 == 3 )
          v43 = 5;
        else
          v43 = v42 + 1;
        McTemplateU0pxu_EtwWriteTransfer(v37, (unsigned int)QuicConnPacketACKed, a1 - 2632, v36[2], v43);
      }
      v44 = v88;
      if ( v88 >= v39 )
        v44 = v39;
      v88 = v44;
      if ( v87 < v36[2] )
      {
        v34 = (v36[11] & 0x40) != 0;
        v87 = v36[2];
      }
      v45 = (*((_BYTE *)v36 + 89) & 1) + v85;
      v85 = v45;
      QuicLossDetectionOnPacketAcknowledged(a1, a4, (_DWORD)v36, 0, v91, a5);
      v47 = 0;
      if ( !v35 )
      {
        if ( v78 && !v79 )
        {
          v48 = v88;
          if ( v88 >= a5 )
          {
            v48 = v88 - a5;
            v88 -= a5;
          }
          v46 = v48;
          v49 = v89 - v10[455];
          v50 = a2;
          if ( !v48 )
            v46 = 1;
          v90 = v89 - v10[455];
          v51 = *(_QWORD *)(v93 + 48);
          *(_QWORD *)(a2 + 160) = v46;
          if ( v46 < *(_QWORD *)(a2 + 168) )
          {
            *(_QWORD *)(a2 + 168) = v46;
            v47 = 1;
          }
          if ( v46 > *(_QWORD *)(a2 + 176) )
            *(_QWORD *)(a2 + 176) = v46;
          v52 = *(_BYTE *)(a2 + 1);
          if ( (v52 & 8) != 0 )
          {
            v55 = *(_QWORD *)(a2 + 152);
            v56 = 3LL * *(_QWORD *)(a2 + 184);
            v57 = (v56 + v55 - v46) >> 2;
            v54 = (v46 + v56 - v55) >> 2;
            if ( v55 > v46 )
              v54 = v57;
            v58 = 7 * v55;
            v49 = v90;
            v53 = (v46 + v58) >> 3;
          }
          else
          {
            *(_BYTE *)(a2 + 1) = v52 | 8;
            v53 = v46;
            v54 = v46 >> 1;
          }
          *(_QWORD *)(a2 + 184) = v54;
          *(_QWORD *)(a2 + 152) = v53;
          if ( v49 != -1 )
          {
            v59 = v10[458];
            if ( v59 && !v47 )
            {
              v60 = v51 - v59 - v49;
              v61 = v60 + 7LL * *(_QWORD *)(a2 + 192);
              *(_QWORD *)(a2 + 200) = v60;
              *(_QWORD *)(a2 + 192) = v61 >> 3;
              goto LABEL_85;
            }
            v62 = v46;
            v46 >>= 1;
            v10[458] = v51 - v62 / 2 - v49;
            *(_QWORD *)(a2 + 192) = v46;
            *(_QWORD *)(a2 + 200) = v46;
            if ( (byte_14005C48C & 1) != 0 )
            {
              _snprintf_s(v95, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "New Phase Shift: %lld us", v10[458]);
              McTemplateU0ps_EtwWriteTransfer(v63, QuicConnLogVerbose, a1 - 2632, v95);
              goto LABEL_85;
            }
LABEL_88:
            if ( v80 )
            {
              v65 = *(unsigned __int8 *)(v50 + 2);
              if ( (v65 & 0x18) == 0x18 )
                goto LABEL_101;
              v66 = a4;
              LODWORD(v67) = 0;
              v46 = v10[a4 + 345];
              if ( a8 )
              {
                v68 = *(_QWORD *)(v46 + 24);
                v69 = a8[2];
                v67 = v69 + *a8 - *(_QWORD *)(v46 + 16) - v68;
                if ( v67 >= 0 && v67 >= v85 && (unsigned __int64)v10[430] >= *(_OWORD *)a8 )
                {
                  v70 = a2;
                  *(_QWORD *)(v46 + 24) = v69;
                  *(_QWORD *)(v46 + 16) = *a8;
                  v71 = *(unsigned __int8 *)(a2 + 2);
                  if ( ((unsigned __int8)v71 & 0x18u) <= 8 )
                  {
                    LOBYTE(v71) = v71 & 0xE7 | 0x10;
                    *(_BYTE *)(a2 + 2) = v71;
                    if ( (byte_14005C489 & 0x40) != 0 )
                    {
                      McTemplateU0pq_EtwWriteTransfer(v71, QuicConnEcnCapable, a1 - 2632, 1);
                      v70 = a2;
                    }
                  }
                  if ( (*(_BYTE *)(v70 + 2) & 0x18) == 0x10 && v69 > v68 )
                  {
                    v94[0] = v87;
                    v94[1] = *(_QWORD *)(a1 + 80);
                    QuicCongestionControlOnEcn(v10 + 271, v94);
                  }
                  v50 = a2;
LABEL_101:
                  QuicLossDetectionDetectAndHandleLostPackets(a1, v91, v46);
                  v72 = v83;
LABEL_109:
                  v96 = *(_QWORD *)(a1 + 8);
                  v97 = *(_QWORD *)(a1 + 80);
                  v98 = *(_QWORD *)(a1 + 64);
                  v100 = 0;
                  v73 = *(_QWORD *)(v50 + 152);
                  v99 = v72;
                  v102 = v73;
                  v74 = *(_QWORD *)(v50 + 192);
                  v103 = v88;
                  v104 = v74;
                  v75 = *(_QWORD *)(a1 + 104);
                  *(_QWORD *)v95 = v91;
                  v105 = v91 - a5;
                  v101 = v33;
                  v107 = 0;
                  v108 = 0;
                  v109 = 0;
                  v106 = (unsigned __int8)((4 * (v34 | 2)) | (v75 != 0 ? 2 : 0));
                  if ( (unsigned __int8)QuicCongestionControlOnDataAcknowledged(v10 + 271, v95) )
                    QuicSendQueueFlush(v10 + 427, 6);
LABEL_111:
                  *(_WORD *)(a1 + 120) = 0;
                  while ( v33 )
                  {
                    v76 = v33;
                    v33 = (_QWORD *)*v33;
                    QuicSentPacketPoolReturnPacketMetadata(v76, a1 - 2632);
                  }
                  return QuicLossDetectionUpdateTimer(a1, 0);
                }
                v66 = a4;
                v50 = a2;
              }
              else if ( !v45 )
              {
                goto LABEL_101;
              }
              if ( (byte_14005C489 & 0x40) != 0 )
              {
                LOBYTE(v65) = ((unsigned __int8)v65 >> 3) & 3;
                McTemplateU0pqxxxiu_EtwWriteTransfer(
                  v67,
                  v65,
                  a1 - 2632,
                  v66,
                  *(_QWORD *)(v46 + 16),
                  *(_QWORD *)(v46 + 24),
                  v10[430],
                  v67,
                  v65);
              }
              *(_BYTE *)(v50 + 2) |= 0x18u;
              QuicLossDetectionDetectAndHandleLostPackets(a1, v91, v46);
              v72 = v83;
              goto LABEL_109;
            }
            v72 = v83;
            if ( v83 )
              goto LABEL_109;
            goto LABEL_111;
          }
LABEL_85:
          if ( (byte_14005C48C & 1) == 0 )
            goto LABEL_88;
          _snprintf_s(
            v95,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Updated Rtt=%u.%03u ms, Var=%u.%03u 1Way=%u.%03u ms",
            *(_QWORD *)(a2 + 152) / 0x3E8uLL,
            *(_QWORD *)(a2 + 152) % 0x3E8uLL,
            *(_QWORD *)(a2 + 184) / 0x3E8uLL,
            *(_QWORD *)(a2 + 184) % 0x3E8uLL,
            *(_QWORD *)(a2 + 192) / 0x3E8uLL,
            *(_QWORD *)(a2 + 192) % 0x3E8uLL);
          McTemplateU0ps_EtwWriteTransfer(v64, QuicConnLogVerbose, a1 - 2632, v95);
        }
        v50 = a2;
        goto LABEL_88;
      }
      v13 = a4;
    }
    if ( (byte_14005C48B & 4) != 0 )
      McTemplateU0ps_EtwWriteTransfer(v37, QuicConnError, a1 - 2632, "Incorrect ACK encryption level");
    result = v94[0];
    *(_BYTE *)v94[0] = 1;
  }
  return result;
}

```

## disassembly

```asm
0x140013b30  mov     [rsp-8+arg_10], rbx
0x140013b35  push    rbp
0x140013b36  push    rsi
0x140013b37  push    rdi
0x140013b38  push    r12
0x140013b3a  push    r13
0x140013b3c  push    r14
0x140013b3e  push    r15
0x140013b40  lea     rbp, [rsp-0C0h]
0x140013b48  sub     rsp, 1C0h
0x140013b4f  mov     rax, cs:__security_cookie
0x140013b56  xor     rax, rsp
0x140013b59  mov     [rbp+0F0h+var_40], rax
0x140013b60  mov     rbx, [rbp+0F0h+arg_30]
0x140013b67  lea     rax, [rbp+0F0h+var_160]
0x140013b6b  mov     r15, rcx
0x140013b6e  mov     [rsp+1F0h+var_19C], r9d
0x140013b73  xor     ecx, ecx; PerformanceFrequency
0x140013b75  mov     [rbp+0F0h+var_158], r8
0x140013b79  mov     [rsp+1F0h+var_198], rdx
0x140013b7e  mov     edi, ecx
0x140013b80  mov     [rbp+0F0h+var_150], rbx
0x140013b84  lea     rsi, [r15-0A48h]
0x140013b8b  mov     [rbp+0F0h+var_160], rcx
0x140013b8f  mov     [rsp+1F0h+var_188], rax
0x140013b94  mov     [rsp+1F0h+var_190], ecx
0x140013b98  call    cs:__imp_KeQueryPerformanceCounter
0x140013b9f  nop     dword ptr [rax+rax+00h]
0x140013ba4  mov     r8, qword ptr cs:CxPlatPerfFreq
0x140013bab  lea     r13, [r15+58h]
0x140013baf  mov     rcx, rax
0x140013bb2  mov     [rsp+1F0h+var_178], 0FFFFFFFFFFFFFFFFh
0x140013bbb  shr     rax, 20h
0x140013bbf  xor     edx, edx
0x140013bc1  imul    r9, rax, 0F4240h
0x140013bc8  mov     rax, r9
0x140013bcb  div     r8
0x140013bce  mov     rax, rdx
0x140013bd1  mov     edx, ecx
0x140013bd3  imul    rcx, rdx, 0F4240h
0x140013bda  shl     rax, 20h
0x140013bde  xor     edx, edx
0x140013be0  add     rax, rcx
0x140013be3  xor     cl, cl
0x140013be5  div     r8
0x140013be8  xor     edx, edx
0x140013bea  mov     [rsp+1F0h+var_1A0], cl
0x140013bee  mov     r11, rax
0x140013bf1  mov     rax, r9
0x140013bf4  div     r8
0x140013bf7  mov     r8d, [rsp+1F0h+var_19C]
0x140013bfc  lea     r9, [r15+68h]
0x140013c00  shl     rax, 20h
0x140013c04  mov     r12, r9
0x140013c07  add     r11, rax
0x140013c0a  xor     al, al
0x140013c0c  mov     [rbp+0F0h+var_168], r11
0x140013c10  xor     r11d, r11d
0x140013c13  mov     [rbx], al
0x140013c15  mov     ecx, r11d
0x140013c18  mov     [rbp+0F0h+var_170], r11
0x140013c1c  mov     ebx, r11d
0x140013c1f  mov     [rsp+1F0h+var_19E], al
0x140013c23  mov     [rsp+1F0h+var_19F], al
0x140013c27  lea     r10, PacketLogPrefix; "CSTR"
0x140013c2e  xchg    ax, ax
0x140013c30  mov     rax, [rbp+0F0h+arg_28]
0x140013c37  cmp     ecx, [rax+8]
0x140013c3a  jnb     loc_140013EB6
0x140013c40  mov     edx, ecx
0x140013c42  inc     ecx
0x140013c44  shl     rdx, 4
0x140013c48  add     rdx, [rax]
0x140013c4b  mov     dword ptr [rsp+1F0h+var_180], ecx
0x140013c4f  test    rdx, rdx
0x140013c52  jz      loc_140013EB6
0x140013c58  mov     rcx, [r12]
0x140013c5c  mov     r14, rdx
0x140013c5f  test    rcx, rcx
0x140013c62  jz      loc_140013DAF
0x140013c68  mov     rax, [r15+70h]
0x140013c6c  mov     r8, [rdx]
0x140013c6f  cmp     [rax+10h], r8
0x140013c73  jb      loc_140013DAF
0x140013c79  nop     dword ptr [rax+00000000h]
0x140013c80  cmp     [rcx+10h], r8
0x140013c84  jnb     short loc_140013C94
0x140013c86  mov     rax, [rcx]
0x140013c89  mov     r12, rcx
0x140013c8c  mov     rcx, rax
0x140013c8f  test    rax, rax
0x140013c92  jnz     short loc_140013C80
0x140013c94  mov     rax, [r12]
0x140013c98  mov     rdi, r12
0x140013c9b  test    rax, rax
0x140013c9e  jz      loc_140013D80
0x140013ca4  nop     dword ptr [rax+00h]
0x140013ca8  nop     dword ptr [rax+rax+00000000h]
0x140013cb0  mov     rcx, [r14+8]
0x140013cb4  mov     rdx, [rax+10h]
0x140013cb8  dec     rcx
0x140013cbb  add     rcx, [r14]
0x140013cbe  cmp     rdx, rcx
0x140013cc1  ja      loc_140013D52
0x140013cc7  movzx   eax, cs:byte_14005C48E
0x140013cce  test    al, al
0x140013cd0  jns     short loc_140013D30
0x140013cd2  test    rsi, rsi
0x140013cd5  jnz     short loc_140013CDC
0x140013cd7  lea     eax, [rsi+2Dh]
0x140013cda  jmp     short loc_140013CEA
0x140013cdc  cmp     dword ptr [rsi], 4
0x140013cdf  mov     rax, r11
0x140013ce2  setz    al
0x140013ce5  movsx   eax, byte ptr [rax+r10]
0x140013cea  mov     [rsp+1F0h+var_1C8], rdx
0x140013cef  lea     r9, aCTxLluSpurious; "[%c][TX][%llu] Spurious loss detected"
0x140013cf6  mov     edx, 80h; SizeInBytes
0x140013cfb  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x140013cff  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140013d06  lea     rcx, [rbp+0F0h+DstBuf]; DstBuf
0x140013d0a  call    cs:__imp__snprintf_s
0x140013d11  nop     dword ptr [rax+rax+00h]
0x140013d16  lea     r8, [rbp+0F0h+DstBuf]
0x140013d1a  lea     rdx, QuicLogVerbose
0x140013d21  call    McTemplateU0s_EtwWriteTransfer
0x140013d26  xor     r11d, r11d
0x140013d29  lea     r10, PacketLogPrefix; "CSTR"
0x140013d30  inc     qword ptr [rsi+0E98h]
0x140013d37  mov     rax, [rsi+48h]
0x140013d3b  lock dec qword ptr [rax+8E8h]
0x140013d43  mov     rdi, [rdi]
0x140013d46  mov     rax, [rdi]
0x140013d49  test    rax, rax
0x140013d4c  jnz     loc_140013CB0
0x140013d52  lea     r9, [r15+68h]
0x140013d56  cmp     r12, rdi
0x140013d59  jz      short loc_140013D80
0x140013d5b  mov     rax, [r12]
0x140013d5f  mov     rcx, [rsp+1F0h+var_188]
0x140013d64  mov     [rsp+1F0h+var_188], rdi
0x140013d69  mov     [rcx], rax
0x140013d6c  mov     rax, [rdi]
0x140013d6f  mov     [r12], rax
0x140013d73  mov     [rdi], r11
0x140013d76  cmp     rdi, [r15+70h]
0x140013d7a  jnz     short loc_140013D80
0x140013d7c  mov     [r15+70h], r12
0x140013d80  cmp     qword ptr [r9], 0
0x140013d84  jnz     short loc_140013DAB
0x140013d86  lea     rcx, [rsi+878h]
0x140013d8d  call    QuicCongestionControlOnSpuriousCongestionEvent
0x140013d92  test    al, al
0x140013d94  jz      short loc_140013DA7
0x140013d96  lea     rcx, [rsi+0D58h]
0x140013d9d  mov     edx, 6
0x140013da2  call    QuicSendQueueFlush
0x140013da7  lea     r9, [r15+68h]
0x140013dab  mov     edi, [rsp+1F0h+var_190]
0x140013daf  mov     rcx, [r13+0]
0x140013db3  test    rcx, rcx
0x140013db6  jz      loc_140013E43
0x140013dbc  mov     rdx, [r14]
0x140013dbf  nop
0x140013dc0  cmp     [rcx+10h], rdx
0x140013dc4  jnb     short loc_140013DD4
0x140013dc6  mov     rax, [rcx]
0x140013dc9  mov     r13, rcx
0x140013dcc  mov     rcx, rax
0x140013dcf  test    rax, rax
0x140013dd2  jnz     short loc_140013DC0
0x140013dd4  mov     rax, [r13+0]
0x140013dd8  mov     r8, r13
0x140013ddb  test    rax, rax
0x140013dde  jz      short loc_140013E43
0x140013de0  mov     rdx, [r14+8]
0x140013de4  dec     rdx
0x140013de7  add     rdx, [r14]
0x140013dea  cmp     [rax+10h], rdx
0x140013dee  ja      short loc_140013E10
0x140013df0  test    byte ptr [rax+58h], 4
0x140013df4  mov     rbx, rax
0x140013df7  jz      short loc_140013E05
0x140013df9  dec     dword ptr [r15]
0x140013dfc  mov     rbx, [r8]
0x140013dff  movzx   eax, word ptr [rbx+28h]
0x140013e03  add     edi, eax
0x140013e05  mov     rax, [rbx]
0x140013e08  mov     r8, rbx
0x140013e0b  test    rax, rax
0x140013e0e  jnz     short loc_140013DE0
0x140013e10  xor     r11d, r11d
0x140013e13  mov     [rsp+1F0h+var_190], edi
0x140013e17  cmp     r13, r8
0x140013e1a  jz      short loc_140013E46
0x140013e1c  mov     rax, [r13+0]
0x140013e20  mov     rcx, [rsp+1F0h+var_188]
0x140013e25  mov     [rsp+1F0h+var_188], r8
0x140013e2a  mov     [rcx], rax
0x140013e2d  mov     rax, [r8]
0x140013e30  mov     [r13+0], rax
0x140013e34  mov     [r8], r11
0x140013e37  cmp     r8, [r15+60h]
0x140013e3b  jnz     short loc_140013E46
0x140013e3d  mov     [r15+60h], r13
0x140013e41  jmp     short loc_140013E46
0x140013e43  xor     r11d, r11d
0x140013e46  mov     ecx, dword ptr [rsp+1F0h+var_180]
0x140013e4a  lea     r10, PacketLogPrefix; "CSTR"
0x140013e51  mov     r8d, [rsp+1F0h+var_19C]
0x140013e56  test    rbx, rbx
0x140013e59  jz      loc_140013C30
0x140013e5f  mov     rax, [rbx+10h]
0x140013e63  lea     r10, PacketLogPrefix; "CSTR"
0x140013e6a  cmp     [r15+8], rax
0x140013e6e  ja      loc_140013C30
0x140013e74  mov     [r15+8], rax
0x140013e78  cmp     r8d, [r15+10h]
0x140013e7c  jle     short loc_140013E82
0x140013e7e  mov     [r15+10h], r8d
0x140013e82  movzx   edx, byte ptr [rbx+58h]
0x140013e86  mov     rcx, [rsp+1F0h+var_198]
0x140013e8b  movzx   eax, byte ptr [rbx+2Ah]
0x140013e8f  shr     dl, 2
0x140013e92  and     dl, 1
0x140013e95  mov     [rsp+1F0h+var_19E], 1
0x140013e9a  cmp     [rcx], al
0x140013e9c  mov     ecx, dword ptr [rsp+1F0h+var_180]
0x140013ea0  mov     [rsp+1F0h+var_1A0], dl
0x140013ea4  setnz   [rsp+1F0h+var_19F]
0x140013ea9  mov     rdx, [rbx+20h]
0x140013ead  mov     [rbp+0F0h+var_170], rdx
0x140013eb1  jmp     loc_140013C27
0x140013eb6  mov     r14, [rbp+0F0h+var_160]
0x140013eba  test    r14, r14
0x140013ebd  jz      loc_140014585
0x140013ec3  mov     [rsp+1F0h+var_180], r11
0x140013ec8  xor     r12b, r12b
0x140013ecb  mov     [rsp+1F0h+var_188], r11
0x140013ed0  mov     r13, r14
0x140013ed3  mov     edx, 1
0x140013ed8  mov     r10, 624DD2F1A9FBE77h
0x140013ee2  jmp     short loc_140013EF5
0x140013ef0  mov     r8d, [rsp+1F0h+var_19C]
0x140013ef5  mov     rbx, r13
0x140013ef8  mov     r13, [r13+0]
0x140013efc  movzx   ecx, byte ptr [rbx+58h]
0x140013f00  and     ecx, 3
0x140013f03  jz      short loc_140013F1A
0x140013f05  sub     ecx, 1
0x140013f08  jz      short loc_140013F0F
0x140013f0a  cmp     ecx, 1
0x140013f0d  jz      short loc_140013F16
0x140013f0f  mov     eax, 2
0x140013f14  jmp     short loc_140013F1D
0x140013f16  mov     eax, edx
0x140013f18  jmp     short loc_140013F1D
0x140013f1a  mov     eax, r11d
0x140013f1d  cmp     eax, r8d
0x140013f20  jnz     loc_14001455F
0x140013f26  mov     rdi, [rbp+0F0h+var_168]
0x140013f2a  sub     rdi, [rbx+20h]
0x140013f2e  movzx   eax, cs:byte_14005C48E
0x140013f35  test    al, al
0x140013f37  jns     loc_140013FC8
0x140013f3d  test    rsi, rsi
0x140013f40  jnz     short loc_140013F48
0x140013f42  lea     r9d, [rsi+2Dh]
0x140013f46  jmp     short loc_140013F5D
0x140013f48  cmp     dword ptr [rsi], 4
0x140013f4b  lea     rcx, PacketLogPrefix; "CSTR"
0x140013f52  mov     rax, r11
0x140013f55  setz    al
0x140013f58  movsx   r9d, byte ptr [rax+rcx]
0x140013f5d  mov     rax, r10
0x140013f60  mov     ecx, edi
0x140013f62  mul     rdi
0x140013f65  mov     r8, rdi
0x140013f68  sub     r8, rdx
0x140013f6b  shr     r8, 1
0x140013f6e  add     r8, rdx
0x140013f71  mov     edx, 80h; SizeInBytes
0x140013f76  shr     r8, 9
0x140013f7a  imul    eax, r8d, 3E8h
0x140013f81  sub     ecx, eax
0x140013f83  mov     rax, [rbx+10h]
0x140013f87  mov     dword ptr [rsp+1F0h+var_1B8], ecx
0x140013f8b  lea     rcx, [rbp+0F0h+var_140]; DstBuf
0x140013f8f  mov     dword ptr [rsp+1F0h+var_1C0], r8d
0x140013f94  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140013f9b  mov     [rsp+1F0h+var_1C8], rax
0x140013fa0  mov     dword ptr [rsp+1F0h+var_1D0], r9d
0x140013fa5  lea     r9, aCTxLluAckedU03; "[%c][TX][%llu] ACKed (%u.%03u ms)"
0x140013fac  call    cs:__imp__snprintf_s
0x140013fb3  nop     dword ptr [rax+rax+00h]
0x140013fb8  lea     r8, [rbp+0F0h+var_140]
0x140013fbc  lea     rdx, QuicLogVerbose
0x140013fc3  call    McTemplateU0s_EtwWriteTransfer
0x140013fc8  test    cs:byte_14005C48B, 8
0x140013fcf  jz      short loc_140013FF8
  ... truncated ...
```
