# QuicConnRecvFrames

- ea: `0x1400108c0`
- end: `0x1400123a4`
- name: `QuicConnRecvFrames`
- size: `6884`
- prototype: `char __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `56`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140012c80`

## callees

- `0x1400049b0`
- `0x140007ac0`
- `0x1400093e4`
- `0x14000d490`
- `0x14000d638`
- `0x14000ed10`
- `0x140010440`
- `0x140010820`
- `0x1400108c0`
- `0x1400123c0`
- `0x140013b30`
- `0x14001c638`
- `0x14001c664`
- `0x14001da4c`
- `0x14001dcd0`
- `0x14001df0c`
- `0x14001ec28`
- `0x14001eee0`
- `0x14002157c`
- `0x1400216cc`
- `0x140021a98`
- `0x140021fb0`
- `0x14002202c`
- `0x140022950`
- `0x140022ac8`
- `0x140022b44`
- `0x140022c28`
- `0x1400262b4`
- `0x14002697c`
- `0x140026a88`
- `0x140027154`
- `0x1400291f0`
- `0x140029720`
- `0x140029ef0`
- `0x14002b8e8`
- `0x14002f688`
- `0x14002f858`
- `0x14002fb5c`
- `0x1400304c4`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003e884`
- `0x14003ead8`
- `0x14003ec10`
- `0x14003ed00`
- `0x14003fdf8`
- `0x140040c0c`
- `0x1400427e0`
- `0x140042bbc`
- `0x1400436a4`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400112a2`
- `ntoskrnl!_snprintf_s` at `0x140011441`
- `ntoskrnl!_snprintf_s` at `0x1400114f2`
- `ntoskrnl!_snprintf_s` at `0x14001159f`
- `ntoskrnl!_snprintf_s` at `0x140011a07`
- `ntoskrnl!_snprintf_s` at `0x140011b90`
- `ntoskrnl!_snprintf_s` at `0x1400120fd`
- `ntoskrnl!_snprintf_s` at `0x140012266`
- `ntoskrnl!_snprintf_s` at `0x140012359`
- `ntoskrnl!_snprintf_s` at `0x1400112a2`
- `ntoskrnl!_snprintf_s` at `0x140011441`
- `ntoskrnl!_snprintf_s` at `0x1400114f2`
- `ntoskrnl!_snprintf_s` at `0x14001159f`
- `ntoskrnl!_snprintf_s` at `0x140011a07`
- `ntoskrnl!_snprintf_s` at `0x140011b90`
- `ntoskrnl!_snprintf_s` at `0x1400120fd`
- `ntoskrnl!_snprintf_s` at `0x140012266`
- `ntoskrnl!_snprintf_s` at `0x140012359`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117a7`
- `HAL!KeQueryPerformanceCounter` at `0x140012294`
- `HAL!KeQueryPerformanceCounter` at `0x140012294`

## string_xrefs

- `0x140011d5b`: `Decoding NEW_TOKEN frame`
- `0x14001127f`: `Ignoring frame (%hhu) for already closed stream id = %llu`
- `0x140011f17`: `Decoding PATH_CHALLENGE frame`
- `0x140011f30`: `Decoding PATH_RESPONSE frame`

## pseudocode

```c
char __fastcall QuicConnRecvFrames(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  char v4; // r15
  int v6; // ecx
  int v7; // r14d
  __int64 v8; // r12
  char v9; // al
  bool v10; // di
  __int64 v11; // rsi
  unsigned __int16 v12; // r13
  __int64 v13; // rax
  __int64 v14; // rax
  char v15; // al
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  unsigned int v18; // r15d
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rbx
  unsigned __int64 v22; // rsi
  int v23; // r15d
  unsigned __int64 v24; // rcx
  __int64 v25; // r10
  unsigned __int8 v26; // dl
  unsigned __int64 v27; // rdi
  unsigned __int8 v28; // dl
  unsigned __int64 v29; // r10
  unsigned __int8 v30; // dl
  unsigned __int64 v31; // r12
  unsigned __int8 v32; // dl
  unsigned __int64 v33; // rsi
  unsigned __int64 v34; // rsi
  unsigned __int64 v35; // rdi
  int v36; // eax
  _QWORD *v37; // rax
  __int128 *v38; // rax
  int v39; // eax
  const char *v40; // r9
  unsigned __int64 v41; // rdi
  unsigned __int64 v42; // r9
  char v43; // al
  int v44; // r8d
  __int64 StreamForPeer; // rax
  __int64 v46; // rcx
  __int64 v47; // rsi
  int v48; // r14d
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned __int64 v51; // rsi
  char v52; // di
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rdx
  const char *v56; // rax
  __int64 v57; // rcx
  char v58; // si
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  _QWORD *v62; // rdi
  __int64 v63; // rcx
  int v64; // r9d
  __int64 v65; // rcx
  _QWORD *v66; // rax
  unsigned __int64 v67; // rax
  __int64 v68; // r8
  _BYTE *SourceCidFromSeq; // rax
  char v70; // di
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rax
  unsigned __int8 v74; // r9
  unsigned __int8 v75; // r8
  __int64 v76; // rdx
  int v77; // edx
  __int64 v78; // rcx
  unsigned __int64 v79; // rcx
  unsigned __int8 v80; // r8
  char v81; // dl
  __int64 v82; // rcx
  __int64 v83; // rax
  const char *v84; // r9
  __int64 v86; // rcx
  const char *v87; // r9
  int v88; // eax
  __int64 v89; // rdi
  _QWORD *v90; // rax
  int v91; // ecx
  int v92; // r13d
  __int64 v93; // rcx
  _QWORD *v94; // rax
  char v95; // cl
  int v96; // r13d
  int v97; // r13d
  unsigned __int16 v98; // si
  int v99; // r14d
  __int64 v100; // rcx
  unsigned int v101; // ebx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v103; // rcx
  __int64 v104; // [rsp+20h] [rbp-E0h]
  char v105; // [rsp+40h] [rbp-C0h]
  _WORD v106[2]; // [rsp+44h] [rbp-BCh] BYREF
  char v107; // [rsp+48h] [rbp-B8h] BYREF
  char v108; // [rsp+49h] [rbp-B7h] BYREF
  char v109; // [rsp+4Ah] [rbp-B6h] BYREF
  char v110; // [rsp+4Bh] [rbp-B5h]
  char v111; // [rsp+4Ch] [rbp-B4h] BYREF
  char v112; // [rsp+4Dh] [rbp-B3h] BYREF
  _BYTE v113[2]; // [rsp+4Eh] [rbp-B2h] BYREF
  unsigned __int16 v114; // [rsp+50h] [rbp-B0h]
  unsigned int v115; // [rsp+54h] [rbp-ACh]
  __int64 v116; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v117; // [rsp+60h] [rbp-A0h] BYREF
  int v118; // [rsp+68h] [rbp-98h]
  __int64 v119; // [rsp+70h] [rbp-90h]
  unsigned __int64 v120; // [rsp+78h] [rbp-88h] BYREF
  __int64 v121; // [rsp+80h] [rbp-80h] BYREF
  __int64 v122; // [rsp+88h] [rbp-78h]
  unsigned __int64 v123; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v124; // [rsp+98h] [rbp-68h] BYREF
  __int64 v125; // [rsp+A0h] [rbp-60h]
  __int64 v126; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v127; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v128; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v129; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v130; // [rsp+D0h] [rbp-30h]
  __int64 v131; // [rsp+E0h] [rbp-20h]
  __int64 v132; // [rsp+E8h] [rbp-18h]
  __int64 v133; // [rsp+F0h] [rbp-10h]
  __int128 v134; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v135; // [rsp+108h] [rbp+8h] BYREF
  __int128 v136; // [rsp+118h] [rbp+18h]
  __int128 v137; // [rsp+128h] [rbp+28h] BYREF
  __int64 v138; // [rsp+138h] [rbp+38h]
  _OWORD v139[3]; // [rsp+140h] [rbp+40h] BYREF
  int v140; // [rsp+170h] [rbp+70h]
  __int128 v141; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v142[3]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v143; // [rsp+1C0h] [rbp+C0h]
  char v144; // [rsp+1C8h] [rbp+C8h]
  __int64 v145; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v146; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v147; // [rsp+1E8h] [rbp+E8h]
  char v148[128]; // [rsp+1F0h] [rbp+F0h] BYREF
  char DstBuf[128]; // [rsp+270h] [rbp+170h] BYREF
  char v150[128]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v151[128]; // [rsp+370h] [rbp+270h] BYREF
  char v152[128]; // [rsp+3F0h] [rbp+2F0h] BYREF
  char v153[128]; // [rsp+470h] [rbp+370h] BYREF
  char v154[128]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v4 = 0;
  v118 = a4;
  v133 = a3;
  v6 = *(_DWORD *)(a3 + 88);
  v7 = 0;
  v125 = a2;
  v8 = a3;
  v105 = 0;
  v110 = 0;
  v109 = 0;
  if ( v6 )
  {
    if ( v6 == 2 )
      v115 = 1;
    else
      v115 = 2;
  }
  else
  {
    v115 = 0;
  }
  v9 = *(_BYTE *)(a1 + 248);
  v107 = v9 & 0x30;
  v10 = (v9 & 0x10) != 0 && (v9 & 0x20) == 0;
  v11 = *(_QWORD *)(a3 + 56) + *(unsigned __int16 *)(a3 + 82);
  v12 = *(_WORD *)(a3 + 84);
  v116 = v11;
  v114 = v12;
  v13 = QuicTimePlat();
  v14 = QuicTimePlatToUs64(v13);
  v132 = v14;
  if ( v10 && (*(_BYTE *)(a1 + 249) & 1) == 0 && (unsigned __int64)(v14 - *(_QWORD *)(a1 + 1376)) >= 0x1388 )
    QuicSendSetSendFlag(a1 + 3416, ((*(char *)(a1 + 248) >> 31) & 4u) + 4);
  if ( (unsigned __int8)QuicConnIsClient(a1) )
  {
    v15 = *(_BYTE *)(a1 + 249);
    if ( v15 >= 0 )
      *(_BYTE *)(a1 + 249) = v15 | 0x80;
  }
  v106[0] = 0;
  if ( !v12 )
    goto LABEL_37;
  while ( 2 )
  {
    v117 = 0;
    if ( !QuicVarIntDecode(v12, v11, v106, &v117) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        goto LABEL_276;
      v40 = "Frame type decode failure";
      goto LABEL_298;
    }
    v18 = v117;
    if ( v117 > 0x31 || (v19 = 0x30002FFFFFFFFLL, !_bittest64(&v19, v117)) )
    {
      if ( v117 != 175 && v117 != 757 )
      {
        if ( (byte_14005C48B & 4) == 0 )
          goto LABEL_276;
        v40 = "Unknown frame type";
        goto LABEL_298;
      }
    }
    if ( v115 != 2 )
    {
      switch ( v117 )
      {
        case 0uLL:
        case 1uLL:
        case 2uLL:
        case 3uLL:
        case 6uLL:
        case 0x1CuLL:
          goto LABEL_29;
        default:
          goto LABEL_256;
      }
    }
    if ( *(_DWORD *)(v8 + 88) == 1 && (v117 == 2 || v117 == 3 || v117 == 30) )
    {
LABEL_256:
      if ( (byte_14005C48B & 4) != 0 )
        McTemplateU0pqs_EtwWriteTransfer(
          v17,
          (unsigned int)QuicConnErrorStatus,
          a1,
          v117,
          (__int64)"Disallowed frame type");
      goto LABEL_276;
    }
LABEL_29:
    if ( v117 == 757 )
    {
      if ( (*(_BYTE *)(a1 + 252) & 0x10) != 0 )
      {
        v127 = 0;
        if ( (unsigned __int8)QuicTimestampFrameDecode(v12, v11, v106, &v127) )
        {
          v83 = v127;
          *(_BYTE *)(v8 + 93) |= 8u;
          *(_QWORD *)(v8 + 48) = v83;
          goto LABEL_179;
        }
        if ( (byte_14005C48B & 4) == 0 )
          goto LABEL_276;
        v40 = "Decoding TIMESTAMP frame";
LABEL_298:
        McTemplateU0ps_EtwWriteTransfer(v17, QuicConnError, a1, v40);
        goto LABEL_276;
      }
      if ( (byte_14005C48B & 4) == 0 )
        goto LABEL_303;
      v87 = "Received TIMESTAMP frame when not negotiated";
LABEL_334:
      McTemplateU0ps_EtwWriteTransfer(v17, QuicConnError, a1, v87);
      goto LABEL_303;
    }
    switch ( v117 )
    {
      case 0uLL:
        if ( v106[0] >= v12 )
          goto LABEL_34;
        while ( !*(_BYTE *)(v106[0] + v11) )
        {
          if ( ++v106[0] >= v12 )
            goto LABEL_34;
        }
        goto LABEL_179;
      case 1uLL:
        goto LABEL_108;
      case 2uLL:
      case 3uLL:
        v24 = v106[0];
        v25 = a1 + 1880;
        v147 = 0;
        v108 = 0;
        v146 = 0;
        if ( v114 < (unsigned __int64)v106[0] + 1 )
          goto LABEL_261;
        v26 = *(_BYTE *)(v106[0] + v11);
        if ( v26 >= 0x40u )
        {
          if ( v26 >= 0x80u )
          {
            if ( v26 >= 0xC0u )
            {
              if ( v114 < (unsigned __int64)v106[0] + 8 )
                goto LABEL_261;
              v27 = _byteswap_uint64(*(_QWORD *)(v106[0] + v11)) & 0x3FFFFFFFFFFFFFFFLL;
              LOWORD(v24) = v106[0] + 8;
            }
            else
            {
              if ( v114 < (unsigned __int64)v106[0] + 4 )
                goto LABEL_261;
              v27 = _byteswap_ulong(*(_DWORD *)(v106[0] + v11)) & 0x3FFFFFFF;
              LOWORD(v24) = v106[0] + 4;
            }
          }
          else
          {
            if ( v114 < (unsigned __int64)v106[0] + 2 )
              goto LABEL_261;
            v27 = ((unsigned __int64)(*(_BYTE *)(v106[0] + v11) & 0x3F) << 8) | *(unsigned __int8 *)(v106[0] + v11 + 1);
            LOWORD(v24) = v106[0] + 2;
          }
        }
        else
        {
          v27 = v26;
          LOWORD(v24) = v106[0] + 1;
        }
        if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 1 )
          goto LABEL_261;
        v28 = *(_BYTE *)((unsigned __int16)v24 + v11);
        if ( v28 >= 0x40u )
        {
          if ( v28 >= 0x80u )
          {
            if ( v28 >= 0xC0u )
            {
              if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 8 )
                goto LABEL_261;
              v29 = _byteswap_uint64(*(_QWORD *)((unsigned __int16)v24 + v11)) & 0x3FFFFFFFFFFFFFFFLL;
              LOWORD(v24) = v24 + 8;
            }
            else
            {
              if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 4 )
                goto LABEL_261;
              v29 = _byteswap_ulong(*(_DWORD *)((unsigned __int16)v24 + v11)) & 0x3FFFFFFF;
              LOWORD(v24) = v24 + 4;
            }
          }
          else
          {
            if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 2 )
              goto LABEL_261;
            v29 = ((unsigned __int64)(*(_BYTE *)((unsigned __int16)v24 + v11) & 0x3F) << 8)
                | *(unsigned __int8 *)((unsigned __int16)v24 + v11 + 1);
            LOWORD(v24) = v24 + 2;
          }
          v117 = v29;
          v25 = a1 + 1880;
        }
        else
        {
          LOWORD(v24) = v24 + 1;
          v117 = v28;
        }
        if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 1 )
          goto LABEL_261;
        v30 = *(_BYTE *)((unsigned __int16)v24 + v11);
        if ( v30 >= 0x40u )
        {
          if ( v30 >= 0x80u )
          {
            if ( v30 >= 0xC0u )
            {
              if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 8 )
                goto LABEL_261;
              v31 = _byteswap_uint64(*(_QWORD *)((unsigned __int16)v24 + v11)) & 0x3FFFFFFFFFFFFFFFLL;
              LOWORD(v24) = v24 + 8;
            }
            else
            {
              if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 4 )
                goto LABEL_261;
              v31 = _byteswap_ulong(*(_DWORD *)((unsigned __int16)v24 + v11)) & 0x3FFFFFFF;
              LOWORD(v24) = v24 + 4;
            }
          }
          else
          {
            if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 2 )
              goto LABEL_261;
            v31 = ((unsigned __int64)(*(_BYTE *)((unsigned __int16)v24 + v11) & 0x3F) << 8)
                | *(unsigned __int8 *)((unsigned __int16)v24 + v11 + 1);
            LOWORD(v24) = v24 + 2;
          }
        }
        else
        {
          v31 = v30;
          LOWORD(v24) = v24 + 1;
        }
        if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 1 )
          goto LABEL_261;
        v32 = *(_BYTE *)((unsigned __int16)v24 + v11);
        if ( v32 >= 0x40u )
        {
          if ( v32 >= 0x80u )
          {
            if ( v32 >= 0xC0u )
            {
              if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 8 )
                goto LABEL_261;
              v33 = _byteswap_uint64(*(_QWORD *)((unsigned __int16)v24 + v11)) & 0x3FFFFFFFFFFFFFFFLL;
              LOWORD(v24) = v24 + 8;
            }
            else
            {
              if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 4 )
                goto LABEL_261;
              v33 = _byteswap_ulong(*(_DWORD *)((unsigned __int16)v24 + v11)) & 0x3FFFFFFF;
              LOWORD(v24) = v24 + 4;
            }
          }
          else
          {
            if ( v114 < (unsigned __int64)(unsigned __int16)v24 + 2 )
              goto LABEL_261;
            v33 = ((unsigned __int64)(*(_BYTE *)((unsigned __int16)v24 + v11) & 0x3F) << 8)
                | *(unsigned __int8 *)((unsigned __int16)v24 + v11 + 1);
            LOWORD(v24) = v24 + 2;
          }
        }
        else
        {
          v33 = v32;
          LOWORD(v24) = v24 + 1;
        }
        v106[0] = v24;
        if ( v33 > v27 )
          goto LABEL_261;
        v34 = v33 + 1;
        v111 = 0;
        if ( !QuicRangeAddRange(v25, v27 - v34 + 1, v34, &v111) )
        {
          *(_DWORD *)(a1 + 1888) = 0;
          goto LABEL_263;
        }
        if ( v31 < 0x10000 )
        {
          if ( (_DWORD)v31 )
          {
            while ( v34 <= v27 )
            {
              v35 = v27 - v34;
              v134 = 0;
              if ( !(unsigned __int8)QuicAckBlockDecode(v114, v116, v106, &v134) )
                break;
              v24 = v134;
              if ( (__int64)v134 + 1 > v35 )
                break;
              v24 = v35 - v134;
              v34 = *((_QWORD *)&v134 + 1) + 1LL;
              v27 = v35 - v134 - 1;
              if ( *((_QWORD *)&v134 + 1) + 1LL > v24 )
                break;
              if ( !QuicRangeAddRange(a1 + 1880, v27 - *((_QWORD *)&v134 + 1), *((_QWORD *)&v134 + 1) + 1LL, &v111) )
                goto LABEL_258;
              if ( ++v7 >= (unsigned int)v31 )
                goto LABEL_98;
            }
LABEL_259:
            *(_DWORD *)(a1 + 1888) = 0;
            goto LABEL_262;
          }
LABEL_98:
          v11 = v116;
          if ( v18 == 3 && !(unsigned __int8)QuicResetStreamFrameDecode(v114, v116, v106, &v146) )
          {
LABEL_258:
            *(_DWORD *)(a1 + 1888) = 0;
            goto LABEL_263;
          }
          v36 = *(_DWORD *)(a1 + 1888);
          if ( !v36 )
            goto LABEL_259;
          v37 = (_QWORD *)(*(_QWORD *)(a1 + 1880) + 16LL * (unsigned int)(v36 - 1));
          v24 = *v37 + v37[1] - 1LL;
          if ( *(_QWORD *)(a1 + 2712) < v24 )
            goto LABEL_259;
          v38 = &v146;
          v8 = v133;
          v7 = 0;
          if ( v18 != 3 )
            v38 = 0;
          QuicLossDetectionProcessAckBlocks(
            a1 + 2632,
            v125,
            v133,
            v115,
            v117 << *(_QWORD *)(a1 + 1696),
            a1 + 1880,
            (__int64)&v108,
            (__int64)v38);
          *(_DWORD *)(a1 + 1888) = 0;
          ++*(_QWORD *)(a1 + 3824);
          *(_BYTE *)(v8 + 93) |= 8u;
          v12 = v114;
          goto LABEL_179;
        }
LABEL_261:
        *(_DWORD *)(a1 + 1888) = 0;
LABEL_262:
        v108 = 1;
LABEL_263:
        if ( v108 )
        {
          if ( (byte_14005C48B & 4) != 0 )
          {
            v84 = "Invalid ACK frame";
            goto LABEL_275;
          }
          goto LABEL_276;
        }
        return 0;
      case 4uLL:
      case 5uLL:
      case 8uLL:
      case 9uLL:
      case 0xAuLL:
      case 0xBuLL:
      case 0xCuLL:
      case 0xDuLL:
      case 0xEuLL:
      case 0xFuLL:
      case 0x11uLL:
      case 0x15uLL:
      case 0x21uLL:
        if ( v107 )
        {
          if ( !(unsigned __int8)QuicStreamFrameSkip((unsigned int)v117, v12, v11, v106) )
          {
            if ( (byte_14005C48B & 4) == 0 )
              goto LABEL_276;
            v40 = "Skipping closed stream frame";
            goto LABEL_298;
          }
        }
        else
        {
          v17 = v106[0];
          if ( v12 < (unsigned __int64)v106[0] + 1 )
            goto LABEL_288;
          LOBYTE(v41) = *(_BYTE *)(v106[0] + v11);
          if ( (unsigned __int8)v41 >= 0x40u )
          {
            if ( (unsigned __int8)v41 >= 0x80u )
            {
              if ( (unsigned __int8)v41 >= 0xC0u )
              {
                if ( v12 < (unsigned __int64)v106[0] + 8 )
                {
LABEL_288:
                  if ( (byte_14005C48B & 4) == 0 )
                    goto LABEL_276;
                  v40 = "Decoding stream ID from frame";
                  goto LABEL_298;
                }
                v41 = _byteswap_uint64(*(_QWORD *)(v106[0] + v11)) & 0x3FFFFFFFFFFFFFFFLL;
              }
              else
              {
                if ( v12 < (unsigned __int64)v106[0] + 4 )
                  goto LABEL_288;
                v41 = _byteswap_ulong(*(_DWORD *)(v106[0] + v11)) & 0x3FFFFFFF;
              }
            }
            else
            {
              if ( v12 < (unsigned __int64)v106[0] + 2 )
                goto LABEL_288;
              v41 = *(unsigned __int8 *)(v106[0] + v11 + 1)
                  | ((unsigned __int64)(*(_BYTE *)(v106[0] + v11) & 0x3F) << 8);
            }
          }
          else
          {
            v41 = (unsigned __int8)v41;
          }
          v105 = 1;
          v42 = v41 & 1;
          if ( *(_DWORD *)a1 == 4 )
            LOBYTE(v42) = !(v41 & 1);
          else
            LOBYTE(v42) = v42 != 0;
          if ( (v41 & 2) != 0 && (v117 == 17 || v117 == 5 ? (v43 = 1) : (v43 = 0), (_BYTE)v42 == v43) )
          {
            if ( (byte_14005C48B & 4) != 0 )
              McTemplateU0ps_EtwWriteTransfer(v106[0], QuicConnError, a1, "Invalid frame on unidirectional stream");
            QuicConnTransportError(a1, 5);
          }
          else
          {
            v44 = *(_BYTE *)(v8 + 92) >> 7;
            v112 = 0;
            StreamForPeer = QuicStreamSetGetStreamForPeer((int)a1 + 2032, v41, v44, v42, (__int64)&v112);
            v47 = StreamForPeer;
            if ( StreamForPeer )
            {
              v48 = QuicStreamRecv(StreamForPeer, v8, v18, v12, v116, (__int64)v106, (__int64)&v109);
              if ( *(__int64 *)(v47 + 16) <= 0 )
                CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\stream.h", 732, "Stream->RefCount > 0");
              if ( (unsigned __int8)CxPlatRefDecrement(v47 + 16) )
                QuicStreamFree(v47);
              if ( v48 == -1073741801 )
              {
                QuicPacketLogDrop(a1, v8, "Stream frame process OOM");
                return 0;
              }
              if ( v48 < 0 )
              {
                if ( (byte_14005C48B & 4) == 0 )
                  goto LABEL_276;
                v40 = "Invalid stream frame";
                goto LABEL_298;
              }
              v11 = v116;
              v7 = 0;
              *(_BYTE *)(v8 + 93) |= 8u;
            }
            else
            {
              if ( v112 )
              {
                if ( (byte_14005C48B & 4) == 0 )
                  return 0;
                McTemplateU0ps_EtwWriteTransfer(v46, QuicConnError, a1, "Getting stream from ID");
                return 0;
              }
              if ( (byte_14005C48B & 0x40) != 0 )
              {
                _snprintf_s(
                  DstBuf,
                  0x80u,
                  0xFFFFFFFFFFFFFFFFuLL,
                  "Ignoring frame (%hhu) for already closed stream id = %llu",
                  (unsigned __int8)v18,
                  v41);
                McTemplateU0ps_EtwWriteTransfer(v49, QuicConnLogWarning, a1, DstBuf);
              }
              v11 = v116;
              if ( !(unsigned __int8)QuicStreamFrameSkip(v18, v12, v116, v106) )
              {
                if ( (byte_14005C48B & 4) == 0 )
                  goto LABEL_276;
                v40 = "Skipping ignored stream frame";
                goto LABEL_298;
              }
              *(_BYTE *)(v8 + 93) |= 8u;
            }
          }
        }
        goto LABEL_179;
      case 6uLL:
        v138 = 0;
        v137 = 0;
        if ( !(unsigned __int8)QuicCryptoFrameDecode(v12, v11, v106, &v137) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding CRYPTO frame";
          goto LABEL_298;
        }
        if ( v107 )
          goto LABEL_179;
        v39 = QuicCryptoProcessFrame(a1 + 2784, *(unsigned int *)(v8 + 88), &v137);
        if ( v39 < 0 )
        {
          switch ( v39 )
          {
            case -1073741801:
              QuicPacketLogDrop(a1, v8, "Crypto frame process OOM");
              return 0;
            case -1071382527:
              if ( (unsigned __int8)QuicBindingQueueStatelessOperation(*(_QWORD *)(a1 + 360), 9, v8) )
                *(_BYTE *)(v8 + 93) |= 1u;
              QuicConnCloseLocally(a1, 3, 17);
              return 0;
            case -1073741436:
              return 0;
            default:
              if ( (byte_14005C48B & 4) != 0 )
              {
                v84 = "Invalid CRYPTO frame";
LABEL_275:
                McTemplateU0ps_EtwWriteTransfer(v24, QuicConnError, a1, v84);
              }
LABEL_276:
              QuicConnTransportError(a1, 7);
              return 0;
          }
        }
        goto LABEL_108;
      case 7uLL:
        v141 = 0;
        if ( (unsigned __int8)QuicNewTokenFrameDecode(v12, v11, v106, &v141) )
        {
          if ( !v107 )
          {
            *(_BYTE *)(v8 + 93) |= 8u;
            v105 = 1;
          }
          goto LABEL_179;
        }
        if ( (byte_14005C48B & 4) == 0 )
          goto LABEL_276;
        v40 = "Decoding NEW_TOKEN frame";
        goto LABEL_298;
      case 0x10uLL:
        v128 = 0;
        if ( !QuicVarIntDecode(v12, v11, v106, &v128) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding MAX_DATA frame";
          goto LABEL_298;
        }
        if ( v107 )
          goto LABEL_179;
        if ( *(_QWORD *)(a1 + 3456) >= v128 )
          goto LABEL_108;
        *(_QWORD *)(a1 + 3456) = v128;
        v109 = 1;
        QuicConnRemoveOutFlowBlockedReason(a1, 16);
        QuicSendQueueFlush(a1 + 3416, 7);
        *(_BYTE *)(v8 + 93) |= 8u;
        v105 = 1;
        goto LABEL_179;
      case 0x12uLL:
      case 0x13uLL:
        LOBYTE(v120) = 0;
        v119 = 0;
        if ( !QuicVarIntDecode(v12, v11, v106, &v120) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding MAX_STREAMS frame";
          goto LABEL_298;
        }
        LOBYTE(v119) = v18 == 18;
        if ( !v107 )
        {
          if ( v120 <= 0xFFFFFFFFFFFFFFFLL )
          {
            QuicStreamSetUpdateMaxStreams(a1 + 2032);
            *(_BYTE *)(v8 + 93) |= 8u;
            v105 = 1;
          }
          else
          {
            QuicConnTransportError(a1, 4);
          }
        }
        goto LABEL_179;
      case 0x14uLL:
        v123 = 0;
        if ( !QuicVarIntDecode(v12, v11, v106, &v123) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding BLOCKED frame";
          goto LABEL_298;
        }
        if ( !v107 )
        {
          if ( (byte_14005C48C & 1) != 0 )
          {
            _snprintf_s(v150, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Peer Connection FC blocked (%llu)", v123);
            McTemplateU0ps_EtwWriteTransfer(v50, QuicConnLogVerbose, a1, v150);
          }
          QuicSendSetSendFlag(a1 + 3416, 32);
          *(_BYTE *)(v8 + 93) |= 8u;
          v105 = 1;
        }
        goto LABEL_179;
      case 0x16uLL:
      case 0x17uLL:
        LOBYTE(v122) = 0;
        v121 = 0;
        if ( !(unsigned __int8)QuicStreamsBlockedFrameDecode(v117, v12, v11, (unsigned int)v106, (__int64)&v121) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding STREAMS_BLOCKED frame";
          goto LABEL_298;
        }
        if ( v107 )
          goto LABEL_179;
        v51 = v122;
        v52 = v121;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(
            v151,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Peer Streams[%hu] FC blocked (%llu)",
            (unsigned __int8)v121,
            v122);
          McTemplateU0ps_EtwWriteTransfer(v53, QuicConnLogVerbose, a1, v151);
        }
        v105 = 1;
        v54 = 0;
        v55 = 2;
        if ( v52 )
          v55 = 0;
        LOBYTE(v54) = *(_DWORD *)a1 != 4;
        if ( *(_QWORD *)(a1 + 24 * (v55 | v54) + 2032) <= v51 )
        {
          memset(v139, 0, sizeof(v139));
          LODWORD(v139[0]) = 8;
          BYTE8(v139[0]) = v52;
          v140 = 0;
          if ( (byte_14005C48C & 1) != 0 )
          {
            v56 = "Bidi";
            if ( !v52 )
              v56 = "Unidi";
            _snprintf_s(
              v152,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "Indicating QUIC_CONNECTION_EVENT_PEER_NEEDS_STREAMS type: %s",
              v56);
            McTemplateU0ps_EtwWriteTransfer(v57, QuicConnLogVerbose, a1, v152);
          }
          QuicConnIndicateEvent(a1, v139);
          *(_BYTE *)(v8 + 93) |= 8u;
        }
        goto LABEL_178;
      case 0x18uLL:
        v143 = 0;
        v144 = 0;
        memset(v142, 0, sizeof(v142));
        if ( !(unsigned __int8)QuicNewConnectionIDFrameDecode(v12, v11, v106, v142) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding NEW_CONNECTION_ID frame";
          goto LABEL_298;
        }
        if ( v107 )
          goto LABEL_179;
        v58 = 0;
        if ( *(_QWORD *)(a1 + 312) < *(_QWORD *)&v142[1] )
        {
          *(_QWORD *)(a1 + 312) = *(_QWORD *)&v142[1];
          v58 = QuicConnOnRetirePriorToUpdated(a1);
        }
        if ( QuicConnGetDestCidFromSeq(a1, *((_QWORD *)&v142[0] + 1), 0) )
          goto LABEL_192;
        v59 = QuicCidNewDestination(LOBYTE(v142[0]), (char *)&v142[1] + 8);
        v62 = (_QWORD *)v59;
        if ( !v59 )
        {
          if ( (Microsoft_QuicEnableBits & 2) != 0 )
            McTemplateU0sx_EtwWriteTransfer(v61, v60, "new DestCid", LOBYTE(v142[0]) + 48LL);
          v86 = a1;
          if ( !v58 )
          {
            QuicConnFatalError(a1, 3221225495LL, 0);
            return 0;
          }
          goto LABEL_307;
        }
        *(_BYTE *)(v59 + 32) |= 0x40u;
        v63 = LOBYTE(v142[0]);
        v64 = DWORD2(v142[0]);
        *(_QWORD *)(v59 + 40) = *((_QWORD *)&v142[0] + 1);
        *(_OWORD *)(v59 + 16) = *(_OWORD *)((char *)&v142[1] + v63 + 8);
        if ( byte_14005C48A < 0 )
          McTemplateU0pxubr2_EtwWriteTransfer(
            v63,
            (unsigned int)QuicConnDestCidAdded,
            a1,
            v64,
            *(_BYTE *)(v59 + 33),
            v59 + 48);
        v65 = a1 + 1288;
        v66 = *(_QWORD **)(a1 + 1296);
        *v62 = a1 + 1288;
        v62[1] = v66;
        *v66 = v62;
        v67 = *(_QWORD *)(a1 + 312);
        *(_QWORD *)(a1 + 1296) = v62;
        ++*(_BYTE *)(a1 + 272);
        if ( v62[5] < v67 )
          QuicConnRetireCid(a1, v62);
        if ( *(_BYTE *)(a1 + 272) > 4u )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0ps_EtwWriteTransfer(v65, QuicConnError, a1, "Peer exceeded CID limit");
          v86 = a1;
          if ( v58 )
          {
LABEL_307:
            QuicConnSilentlyAbort(v86);
            return 0;
          }
LABEL_303:
          QuicConnTransportError(a1, 10);
          return 0;
        }
LABEL_192:
        if ( v58 && !(unsigned __int8)QuicConnReplaceRetiredCids(a1) )
          return 0;
        v105 = 1;
LABEL_178:
        v11 = v116;
        goto LABEL_179;
      case 0x19uLL:
        v124 = 0;
        if ( !QuicVarIntDecode(v12, v11, v106, &v124) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding RETIRE_CONNECTION_ID frame";
          goto LABEL_298;
        }
        if ( v107 )
          goto LABEL_179;
        LOBYTE(v68) = 1;
        v113[0] = 0;
        SourceCidFromSeq = (_BYTE *)QuicConnGetSourceCidFromSeq(a1, v124, v68, v113);
        if ( SourceCidFromSeq )
        {
          v70 = SourceCidFromSeq[40];
          ExFreePoolWithTag(SourceCidFromSeq, 0x44306351u);
          if ( v113[0] )
          {
            if ( (byte_14005C48B & 4) != 0 )
              McTemplateU0ps_EtwWriteTransfer(v71, QuicConnError, a1, "Last Source CID Retired!");
            QuicConnCloseLocally(a1, 3, 10);
            *(_BYTE *)(v8 + 93) |= 8u;
            v105 = 1;
            goto LABEL_179;
          }
          if ( (v70 & 0x20) == 0 )
          {
            if ( QuicConnGenerateNewSourceCid(a1, 0) )
            {
              *(_BYTE *)(v8 + 93) |= 8u;
              v105 = 1;
            }
            goto LABEL_179;
          }
        }
        goto LABEL_108;
      case 0x1AuLL:
        v126 = 0;
        if ( (unsigned __int8)QuicPathChallengeFrameDecode(v12, v11, v106, &v126) )
        {
          if ( !v107 )
          {
            v72 = v125;
            v73 = v126;
            *(_BYTE *)(v125 + 2) |= 2u;
            *(_QWORD *)(v72 + 212) = v73;
            QuicSendSetSendFlag(a1 + 3416, 2048);
            v105 = 1;
          }
          goto LABEL_179;
        }
        if ( (byte_14005C48B & 4) == 0 )
          goto LABEL_276;
        v40 = "Decoding PATH_CHALLENGE frame";
        goto LABEL_298;
      case 0x1BuLL:
        v145 = 0;
        if ( (unsigned __int8)QuicPathChallengeFrameDecode(v12, v11, v106, &v145) )
        {
          if ( !v107 )
          {
            v74 = *(_BYTE *)(a1 + 275);
            v75 = 0;
            if ( v74 )
            {
              while ( 1 )
              {
                v76 = a1 + 240LL * v75 + 320;
                if ( (*(_BYTE *)(v76 + 1) & 0x20) == 0 && v145 == *(_QWORD *)(v76 + 220) )
                  break;
                if ( ++v75 >= v74 )
                {
                  v105 = 1;
                  goto LABEL_179;
                }
              }
              _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 72) + 2424LL));
              QuicPathSetValid(a1, v76, 2);
            }
            v105 = 1;
          }
          goto LABEL_179;
        }
        if ( (byte_14005C48B & 4) == 0 )
          goto LABEL_276;
        v40 = "Decoding PATH_RESPONSE frame";
        goto LABEL_298;
      case 0x1CuLL:
      case 0x1DuLL:
        LOBYTE(v131) = 0;
        v129 = 0;
        v130 = 0;
        if ( !(unsigned __int8)QuicConnCloseFrameDecode(v117, v12, v11, (unsigned int)v106, (__int64)&v129) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding CONNECTION_CLOSE frame";
          goto LABEL_298;
        }
        v77 = 10;
        if ( (_BYTE)v129 )
        {
          v77 = 14;
        }
        else if ( *((_QWORD *)&v129 + 1) == 11 )
        {
          if ( (byte_14005C489 & 0x40) != 0 )
            McTemplateU0p_EtwWriteTransfer(v17, QuicConnDelayCloseApplicationError);
          *(_BYTE *)(a1 + 252) |= 0x20u;
          goto LABEL_221;
        }
        QuicConnTryClose(a1, v77, DWORD2(v129), v131, SWORD4(v130));
LABEL_221:
        *(_BYTE *)(v8 + 93) |= 8u;
        v105 = 1;
        if ( (*(_BYTE *)(a1 + 249) & 2) == 0 )
          goto LABEL_179;
LABEL_34:
        if ( v109 )
          QuicConnLogOutFlowStats(a1);
        v4 = v110;
LABEL_37:
        if ( (*(_BYTE *)(a1 + 249) & 3) != 0 )
        {
          if ( byte_14005C48E < 0 )
          {
            LODWORD(v104) = PacketLogPrefix[*(_DWORD *)a1 == 4];
            _snprintf_s(
              v148,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "[%c][RX][%llu] not acked (connection is closed)",
              v104,
              *(_QWORD *)(v8 + 40));
            McTemplateU0s_EtwWriteTransfer(v103, QuicLogVerbose, v148);
          }
        }
        else
        {
          v20 = a1 + 8LL * v115;
          v21 = *(_QWORD *)(v20 + 2760);
          if ( v21 )
          {
            v22 = *(_QWORD *)(v8 + 40);
            if ( *(_QWORD *)(v21 + 8) <= v22 )
            {
              *(_QWORD *)(v21 + 8) = v22 + 1;
              *(_BYTE *)(v8 + 93) |= 4u;
              v21 = *(_QWORD *)(v20 + 2760);
              v22 = *(_QWORD *)(v8 + 40);
            }
            if ( v4 )
              v23 = 2;
            else
              v23 = v105 != 0;
            v88 = *(_DWORD *)(v21 + 208);
            v89 = *(_QWORD *)(v21 + 32);
            if ( v88 )
            {
              v90 = (_QWORD *)(*(_QWORD *)(v21 + 200) + 16LL * (unsigned int)(v88 - 1));
              if ( *v90 + v90[1] - 1LL > v22 )
                ++*(_QWORD *)(v89 + 3784);
            }
            v107 = 0;
            if ( QuicRangeAddRange(v21 + 200, v22, 1, &v107) )
            {
              if ( byte_14005C48E >= 0 )
              {
                v92 = v118;
              }
              else
              {
                if ( v89 )
                  v91 = PacketLogPrefix[*(_DWORD *)v89 == 4];
                else
                  v91 = 45;
                v92 = v118;
                LODWORD(v104) = v91;
                _snprintf_s(
                  v148,
                  0x80u,
                  0xFFFFFFFFFFFFFFFFuLL,
                  "[%c][RX][%llu] Marked for ACK (ECN=%hhu)",
                  v104,
                  v22,
                  (unsigned __int8)v118);
                McTemplateU0s_EtwWriteTransfer(v93, QuicLogVerbose, v148);
              }
              v94 = (_QWORD *)(*(_QWORD *)(v21 + 200) + 16LL * (unsigned int)(*(_DWORD *)(v21 + 208) - 1));
              if ( v22 == *v94 + v94[1] - 1LL )
              {
                v95 = 1;
                *(_QWORD *)(v21 + 384) = v132;
              }
              else
              {
                v95 = 0;
              }
              v96 = v92 - 1;
              if ( v96 )
              {
                v97 = v96 - 1;
                if ( v97 )
                {
                  if ( v97 == 1 )
                  {
                    *(_BYTE *)(v21 + 394) |= 2u;
                    ++*(_QWORD *)(v21 + 368);
                  }
                }
                else
                {
                  *(_BYTE *)(v21 + 394) |= 2u;
                  ++*(_QWORD *)(v21 + 352);
                }
              }
              else
              {
                *(_BYTE *)(v21 + 394) |= 2u;
                ++*(_QWORD *)(v21 + 360);
              }
              *(_BYTE *)(v21 + 394) &= ~1u;
              if ( v23 )
              {
                v98 = *(_WORD *)(v21 + 392) + 1;
                *(_WORD *)(v21 + 392) = v98;
                if ( (*(_DWORD *)(v89 + 3488) & 1) == 0 )
                {
                  if ( v23 == 2
                    || (v99 = *(_DWORD *)(v89 + 196)) == 0
                    || v98 >= *(unsigned __int8 *)(v89 + 280)
                    || v95
                    && (unsigned __int8)QuicAckTrackerDidHitReorderingThreshold(
                                          v21 + 48,
                                          *(unsigned __int8 *)(v89 + 282)) )
                  {
                    QuicSendSetSendFlag(v89 + 3416, 1);
                  }
                  else if ( v98 == 1
                         && (*(_BYTE *)(v89 + 3416) & 2) == 0
                         && (*(_DWORD *)(v89 + 3488) & 1) == 0
                         && (*(_BYTE *)(v89 + 248) & 0x30) == 0 )
                  {
                    if ( (byte_14005C48C & 1) != 0 )
                    {
                      _snprintf_s(v148, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Starting ACK_DELAY timer for %u ms", v99);
                      McTemplateU0ps_EtwWriteTransfer(v100, QuicConnLogVerbose, v89, v148);
                    }
                    v101 = 1000 * *(_DWORD *)(v89 + 196);
                    PerformanceCounter = KeQueryPerformanceCounter(0);
                    QuicConnTimerSetEx(
                      v89,
                      1,
                      v101,
                      ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
                    + (1000000LL * PerformanceCounter.LowPart
                     + ((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
                    / CxPlatPerfFreq.QuadPart);
                    *(_BYTE *)(v89 + 3416) |= 2u;
                  }
                }
              }
            }
            else
            {
              QuicConnCloseLocally(v89, 2, 1);
            }
          }
        }
        *(_BYTE *)(v8 + 93) |= 2u;
        return 1;
      case 0x1EuLL:
        if ( *(_DWORD *)a1 == 4 )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_303;
          v87 = "Client sent HANDSHAKE_DONE frame";
          goto LABEL_334;
        }
        if ( (*(_BYTE *)(a1 + 250) & 2) == 0 )
        {
          if ( byte_14005C48B < 0 )
          {
            _snprintf_s(v153, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Handshake confirmed (frame)");
            McTemplateU0ps_EtwWriteTransfer(v78, QuicConnLogInfo, a1, v153);
          }
          LOBYTE(v16) = 1;
          QuicCryptoHandshakeConfirmed(a1 + 2784, v16);
          *(_BYTE *)(v8 + 93) |= 8u;
          v105 = 1;
          goto LABEL_179;
        }
LABEL_108:
        *(_BYTE *)(v8 + 93) |= 8u;
        v105 = 1;
LABEL_179:
        if ( v106[0] >= v12 )
          goto LABEL_34;
        continue;
      case 0x1FuLL:
        v110 = 1;
        goto LABEL_179;
      case 0x30uLL:
      case 0x31uLL:
        if ( (*(_BYTE *)(a1 + 235) & 8) == 0 )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_303;
          v87 = "Received DATAGRAM frame when not negotiated";
          goto LABEL_334;
        }
        if ( !(unsigned __int8)QuicDatagramProcessFrame((int)a1 + 3552, v8, v117, v12, v11, (__int64)v106) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding DATAGRAM frame";
          goto LABEL_298;
        }
        v105 = 1;
        goto LABEL_179;
      case 0xAFuLL:
        v135 = 0;
        v136 = 0;
        if ( !(unsigned __int8)QuicAckFrequencyFrameDecode(v12, v11, v106, &v135) )
        {
          if ( (byte_14005C48B & 4) == 0 )
            goto LABEL_276;
          v40 = "Decoding ACK_FREQUENCY frame";
          goto LABEL_298;
        }
        v17 = v136;
        if ( (unsigned __int64)v136 >= 1000 * (unsigned int)(unsigned __int8)byte_14005C560 )
        {
          v105 = 1;
          if ( (unsigned __int64)v135 >= *(_QWORD *)(a1 + 296) )
          {
            *(_QWORD *)(a1 + 296) = v135 + 1;
            if ( v17 )
            {
              if ( v17 >= 0x3E8 )
                v79 = v17 / 0x3E8;
              else
                LODWORD(v79) = 1;
            }
            else
            {
              LODWORD(v79) = 0;
            }
            *(_DWORD *)(a1 + 196) = v79;
            v80 = BYTE8(v135);
            if ( *((_QWORD *)&v135 + 1) >= 0xFFu )
            {
              *(_BYTE *)(a1 + 280) = -1;
              v80 = -1;
            }
            else
            {
              *(_BYTE *)(a1 + 280) = BYTE8(v135);
            }
            v81 = -1;
            if ( *((_QWORD *)&v136 + 1) < 0xFFu )
              v81 = BYTE8(v136);
            *(_BYTE *)(a1 + 282) = v81;
            if ( byte_14005C48B < 0 )
            {
              _snprintf_s(v154, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Updating packet tolerance to %hhu", v80);
              McTemplateU0ps_EtwWriteTransfer(v82, QuicConnLogInfo, a1, v154);
            }
          }
          goto LABEL_179;
        }
        if ( (byte_14005C48B & 4) == 0 )
          goto LABEL_303;
        v87 = "RequestedMaxAckDelay is less than TimerResolution";
        goto LABEL_334;
      default:
        goto LABEL_179;
    }
  }
}

```

## disassembly

```asm
0x1400108c0  push    rbp
0x1400108c2  push    rbx
0x1400108c3  push    rsi
0x1400108c4  push    rdi
0x1400108c5  push    r12
0x1400108c7  push    r13
0x1400108c9  push    r14
0x1400108cb  push    r15
0x1400108cd  lea     rbp, [rsp-488h]
0x1400108d5  sub     rsp, 588h
0x1400108dc  mov     rax, cs:__security_cookie
0x1400108e3  xor     rax, rsp
0x1400108e6  mov     [rbp+4C0h+var_50], rax
0x1400108ed  xor     r15b, r15b
0x1400108f0  mov     [rsp+5C0h+var_558], r9d
0x1400108f5  mov     rbx, rcx
0x1400108f8  mov     [rbp+4C0h+var_4D0], r8
0x1400108fc  mov     ecx, [r8+58h]
0x140010900  xor     r14d, r14d
0x140010903  mov     [rbp+4C0h+var_520], rdx
0x140010907  mov     r12, r8
0x14001090a  mov     [rsp+5C0h+var_580], 0
0x14001090f  mov     [rsp+5C0h+var_575], r15b
0x140010914  mov     [rsp+5C0h+var_576], r15b
0x140010919  test    ecx, ecx
0x14001091b  jz      short loc_14001093B
0x14001091d  sub     ecx, 1
0x140010920  jz      short loc_140010927
0x140010922  cmp     ecx, 1
0x140010925  jz      short loc_140010931
0x140010927  mov     [rsp+5C0h+var_56C], 2
0x14001092f  jmp     short loc_140010940
0x140010931  mov     [rsp+5C0h+var_56C], 1
0x140010939  jmp     short loc_140010940
0x14001093b  mov     [rsp+5C0h+var_56C], r14d
0x140010940  movzx   eax, byte ptr [rbx+0F8h]
0x140010947  movzx   ecx, al
0x14001094a  and     cl, 30h
0x14001094d  mov     [rsp+5C0h+var_578], cl
0x140010951  test    al, 10h
0x140010953  jz      short loc_14001095E
0x140010955  test    al, 20h
0x140010957  jnz     short loc_14001095E
0x140010959  mov     dil, 1
0x14001095c  jmp     short loc_140010961
0x14001095e  xor     dil, dil
0x140010961  movzx   esi, word ptr [r8+52h]
0x140010966  add     rsi, [r8+38h]
0x14001096a  movzx   r13d, word ptr [r8+54h]
0x14001096f  mov     [rsp+5C0h+var_568], rsi
0x140010974  mov     [rsp+5C0h+var_570], r13w
0x14001097a  call    QuicTimePlat
0x14001097f  mov     rcx, rax
0x140010982  call    QuicTimePlatToUs64
0x140010987  mov     [rbp+4C0h+var_4D8], rax
0x14001098b  test    dil, dil
0x14001098e  jz      short loc_1400109C8
0x140010990  test    byte ptr [rbx+0F9h], 1
0x140010997  jnz     short loc_1400109C8
0x140010999  mov     rcx, rax
0x14001099c  sub     rcx, [rbx+560h]
0x1400109a3  cmp     rcx, 1388h
0x1400109aa  jb      short loc_1400109C8
0x1400109ac  movsx   edx, byte ptr [rbx+0F8h]
0x1400109b3  lea     rcx, [rbx+0D58h]
0x1400109ba  sar     edx, 1Fh
0x1400109bd  and     edx, 4
0x1400109c0  add     edx, 4
0x1400109c3  call    QuicSendSetSendFlag
0x1400109c8  mov     rcx, rbx
0x1400109cb  call    QuicConnIsClient
0x1400109d0  test    al, al
0x1400109d2  jz      short loc_1400109E7
0x1400109d4  movzx   eax, byte ptr [rbx+0F9h]
0x1400109db  test    al, al
0x1400109dd  js      short loc_1400109E7
0x1400109df  or      al, 80h
0x1400109e1  mov     [rbx+0F9h], al
0x1400109e7  mov     [rsp+5C0h+var_57C], r14w
0x1400109ed  lea     rdi, cs:140000000h
0x1400109f4  cmp     r14w, r13w
0x1400109f8  jnb     loc_140010B27
0x1400109fe  xchg    ax, ax
0x140010a00  lea     r9, [rsp+5C0h+var_560]
0x140010a05  mov     [rsp+5C0h+var_560], r14
0x140010a0a  lea     r8, [rsp+5C0h+var_57C]
0x140010a0f  mov     rdx, rsi
0x140010a12  movzx   ecx, r13w
0x140010a16  call    QuicVarIntDecode
0x140010a1b  test    al, al
0x140010a1d  jz      loc_14001200D
0x140010a23  mov     r15, [rsp+5C0h+var_560]
0x140010a28  cmp     r15, 31h ; '1'
0x140010a2c  ja      short loc_140010A3E
0x140010a2e  mov     rax, 30002FFFFFFFFh
0x140010a38  bt      rax, r15
0x140010a3c  jb      short loc_140010A54
0x140010a3e  cmp     r15, 0AFh
0x140010a45  jz      short loc_140010A54
0x140010a47  cmp     r15, 2F5h
0x140010a4e  jnz     loc_140011C03
0x140010a54  cmp     [rsp+5C0h+var_56C], 2
0x140010a59  jz      short loc_140010A7E
0x140010a5b  cmp     r15, 1Ch; switch 29 cases
0x140010a5f  ja      def_140010A78; jumptable 0000000140010A78 default case, cases 4,5,7-27
0x140010a65  movzx   eax, ds:(byte_140056B5C - 140000000h)[rdi+r15]
0x140010a6e  mov     ecx, ds:(jpt_140010A78 - 140000000h)[rdi+rax*4]
0x140010a75  add     rcx, rdi
0x140010a78  jmp     rcx; switch jump
0x140010a7e  cmp     dword ptr [r12+58h], 1
0x140010a84  jnz     short loc_140010AA7; jumptable 0000000140010A78 cases 0-3,6,28
0x140010a86  mov     rax, r15
0x140010a89  sub     rax, 2
0x140010a8d  jz      def_140010A78; jumptable 0000000140010A78 default case, cases 4,5,7-27
0x140010a93  sub     rax, 1
0x140010a97  jz      def_140010A78; jumptable 0000000140010A78 default case, cases 4,5,7-27
0x140010a9d  cmp     rax, 1Bh
0x140010aa1  jz      def_140010A78; jumptable 0000000140010A78 default case, cases 4,5,7-27
0x140010aa7  cmp     r15, 2F5h; jumptable 0000000140010A78 cases 0-3,6,28
0x140010aae  ja      def_140010ADA; jumptable 0000000140010ADA default case, cases 32,34-47,50-174
0x140010ab4  jz      loc_140011BC1
0x140010aba  cmp     r15, 0AFh; switch 176 cases
0x140010ac1  ja      def_140010ADA; jumptable 0000000140010ADA default case, cases 32,34-47,50-174
0x140010ac7  movzx   eax, ds:(byte_140056BC9 - 140000000h)[rdi+r15]
0x140010ad0  mov     ecx, ds:(jpt_140010ADA - 140000000h)[rdi+rax*4]
0x140010ad7  add     rcx, rdi
0x140010ada  jmp     rcx; switch jump
0x140010ae0  cmp     [rsp+5C0h+var_57C], r13w; jumptable 0000000140010ADA case 0
0x140010ae6  jnb     short loc_140010B12
0x140010ae8  nop     dword ptr [rax+rax+00000000h]
0x140010af0  movzx   eax, [rsp+5C0h+var_57C]
0x140010af5  cmp     byte ptr [rax+rsi], 0
0x140010af9  jnz     def_140010ADA; jumptable 0000000140010ADA default case, cases 32,34-47,50-174
0x140010aff  movzx   eax, [rsp+5C0h+var_57C]
0x140010b04  inc     ax
0x140010b07  mov     [rsp+5C0h+var_57C], ax
0x140010b0c  cmp     ax, r13w
0x140010b10  jb      short loc_140010AF0
0x140010b12  cmp     [rsp+5C0h+var_576], 0
0x140010b17  jz      short loc_140010B21
0x140010b19  mov     rcx, rbx
0x140010b1c  call    QuicConnLogOutFlowStats
0x140010b21  movzx   r15d, [rsp+5C0h+var_575]
0x140010b27  test    byte ptr [rbx+0F9h], 3
0x140010b2e  jnz     loc_140012313
0x140010b34  mov     eax, [rsp+5C0h+var_56C]
0x140010b38  lea     rcx, [rbx+rax*8]
0x140010b3c  mov     rbx, [rcx+0AC8h]
0x140010b43  test    rbx, rbx
0x140010b46  jz      loc_140012378
0x140010b4c  mov     rsi, [r12+28h]
0x140010b51  cmp     [rbx+8], rsi
0x140010b55  ja      short loc_140010B71
0x140010b57  lea     rax, [rsi+1]
0x140010b5b  mov     [rbx+8], rax
0x140010b5f  or      byte ptr [r12+5Dh], 4
0x140010b65  mov     rbx, [rcx+0AC8h]
0x140010b6c  mov     rsi, [r12+28h]
0x140010b71  test    r15b, r15b
0x140010b74  jz      loc_140012026
0x140010b7a  mov     r15d, 2
0x140010b80  jmp     loc_140012032
0x140010b85  movzx   ecx, [rsp+5C0h+var_57C]; jumptable 0000000140010ADA cases 2,3
0x140010b8a  lea     r13, [rbx+0A48h]
0x140010b91  movzx   r9d, [rsp+5C0h+var_570]
0x140010b97  lea     r10, [r13-2F0h]
0x140010b9e  xor     eax, eax
0x140010ba0  xorps   xmm0, xmm0
0x140010ba3  mov     [rbp+4C0h+var_3D8], rax
0x140010baa  mov     [rsp+5C0h+var_577], al
0x140010bae  lea     rax, [rcx+1]
0x140010bb2  movups  [rbp+4C0h+var_3E8], xmm0
0x140010bb9  cmp     r9, rax
0x140010bbc  jb      loc_140011C6B
0x140010bc2  movzx   edx, byte ptr [rcx+rsi]
0x140010bc6  cmp     dl, 40h ; '@'
0x140010bc9  jnb     short loc_140010BE0
0x140010bcb  movzx   edi, dl
0x140010bce  inc     cx
0x140010bd1  mov     r11, 3FFFFFFFFFFFFFFFh
0x140010bdb  jmp     loc_140010C63
0x140010be0  cmp     dl, 80h
0x140010be3  jnb     short loc_140010C11
0x140010be5  lea     rax, [rcx+2]
0x140010be9  cmp     r9, rax
0x140010bec  jb      loc_140011C6B
0x140010bf2  movzx   edi, byte ptr [rcx+rsi+1]
0x140010bf7  and     edx, 3Fh
0x140010bfa  shl     rdx, 8
0x140010bfe  mov     r11, 3FFFFFFFFFFFFFFFh
0x140010c08  or      rdi, rdx
0x140010c0b  add     cx, 2
0x140010c0f  jmp     short loc_140010C63
0x140010c11  cmp     dl, 0C0h
0x140010c14  jnb     short loc_140010C3E
0x140010c16  lea     rax, [rcx+4]
0x140010c1a  cmp     r9, rax
0x140010c1d  jb      loc_140011C6B
0x140010c23  mov     edi, [rcx+rsi]
0x140010c26  mov     r11, 3FFFFFFFFFFFFFFFh
0x140010c30  bswap   edi
0x140010c32  and     edi, 3FFFFFFFh
0x140010c38  add     cx, 4
0x140010c3c  jmp     short loc_140010C63
0x140010c3e  lea     rax, [rcx+8]
0x140010c42  cmp     r9, rax
0x140010c45  jb      loc_140011C6B
0x140010c4b  mov     rdi, [rcx+rsi]
0x140010c4f  mov     r11, 3FFFFFFFFFFFFFFFh
0x140010c59  bswap   rdi
0x140010c5c  and     rdi, r11
0x140010c5f  add     cx, 8
0x140010c63  movzx   r8d, cx
0x140010c67  lea     rax, [r8+1]
0x140010c6b  cmp     r9, rax
0x140010c6e  jb      loc_140011C6B
0x140010c74  movzx   edx, byte ptr [r8+rsi]
0x140010c79  cmp     dl, 40h ; '@'
0x140010c7c  jnb     short loc_140010C8B
0x140010c7e  movzx   eax, dl
0x140010c81  inc     cx
0x140010c84  mov     [rsp+5C0h+var_560], rax
0x140010c89  jmp     short loc_140010D03
0x140010c8b  cmp     dl, 80h
0x140010c8e  jnb     short loc_140010CB6
0x140010c90  lea     rax, [r8+2]
0x140010c94  cmp     r9, rax
0x140010c97  jb      loc_140011C6B
0x140010c9d  movzx   eax, cx
0x140010ca0  and     edx, 3Fh
0x140010ca3  shl     rdx, 8
0x140010ca7  movzx   r10d, byte ptr [rax+rsi+1]
0x140010cad  or      r10, rdx
0x140010cb0  add     cx, 2
0x140010cb4  jmp     short loc_140010CF7
0x140010cb6  cmp     dl, 0C0h
0x140010cb9  jnb     short loc_140010CDC
0x140010cbb  lea     rax, [r8+4]
0x140010cbf  cmp     r9, rax
0x140010cc2  jb      loc_140011C6B
0x140010cc8  mov     r10d, [r8+rsi]
0x140010ccc  bswap   r10d
0x140010ccf  and     r10d, 3FFFFFFFh
0x140010cd6  add     cx, 4
0x140010cda  jmp     short loc_140010CF7
0x140010cdc  lea     rax, [r8+8]
0x140010ce0  cmp     r9, rax
0x140010ce3  jb      loc_140011C6B
0x140010ce9  mov     r10, [r8+rsi]
0x140010ced  bswap   r10
0x140010cf0  and     r10, r11
0x140010cf3  add     cx, 8
0x140010cf7  mov     [rsp+5C0h+var_560], r10
0x140010cfc  lea     r10, [r13-2F0h]
0x140010d03  movzx   r8d, cx
0x140010d07  lea     rax, [r8+1]
0x140010d0b  cmp     r9, rax
0x140010d0e  jb      loc_140011C6B
0x140010d14  movzx   edx, byte ptr [r8+rsi]
0x140010d19  cmp     dl, 40h ; '@'
0x140010d1c  jnb     short loc_140010D27
0x140010d1e  movzx   r12d, dl
0x140010d22  inc     cx
0x140010d25  jmp     short loc_140010D93
0x140010d27  cmp     dl, 80h
0x140010d2a  jnb     short loc_140010D52
0x140010d2c  lea     rax, [r8+2]
0x140010d30  cmp     r9, rax
0x140010d33  jb      loc_140011C6B
0x140010d39  movzx   eax, cx
0x140010d3c  and     edx, 3Fh
0x140010d3f  shl     rdx, 8
0x140010d43  movzx   r12d, byte ptr [rax+rsi+1]
0x140010d49  or      r12, rdx
0x140010d4c  add     cx, 2
0x140010d50  jmp     short loc_140010D93
0x140010d52  cmp     dl, 0C0h
0x140010d55  jnb     short loc_140010D78
0x140010d57  lea     rax, [r8+4]
0x140010d5b  cmp     r9, rax
0x140010d5e  jb      loc_140011C6B
0x140010d64  mov     r12d, [r8+rsi]
0x140010d68  bswap   r12d
0x140010d6b  and     r12d, 3FFFFFFFh
0x140010d72  add     cx, 4
0x140010d76  jmp     short loc_140010D93
0x140010d78  lea     rax, [r8+8]
0x140010d7c  cmp     r9, rax
0x140010d7f  jb      loc_140011C6B
0x140010d85  mov     r12, [r8+rsi]
0x140010d89  bswap   r12
0x140010d8c  and     r12, r11
0x140010d8f  add     cx, 8
0x140010d93  movzx   r8d, cx
0x140010d97  lea     rax, [r8+1]
0x140010d9b  cmp     r9, rax
0x140010d9e  jb      loc_140011C6B
0x140010da4  movzx   edx, byte ptr [r8+rsi]
0x140010da9  cmp     dl, 40h ; '@'
0x140010dac  jnb     short loc_140010DB6
  ... truncated ...
```
