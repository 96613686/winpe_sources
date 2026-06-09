# QuicFrameLog

- ea: `0x140046ea8`
- end: `0x14004884d`
- name: `QuicFrameLog`
- size: `6565`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x140048854`

## callees

- `0x14000ed10`
- `0x1400123b0`
- `0x140021a98`
- `0x14002202c`
- `0x140022be4`
- `0x140022c28`
- `0x14002f688`
- `0x14002f858`
- `0x14002f9f0`
- `0x14002fb5c`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003ec10`
- `0x140040b80`
- `0x140040c0c`
- `0x140046acc`
- `0x140046c3c`
- `0x140046d44`
- `0x140046ea8`
- `0x1400488d0`
- `0x140048920`
- `0x140048980`
- `0x140048be8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140046fe5`
- `ntoskrnl!_snprintf_s` at `0x1400470f5`
- `ntoskrnl!_snprintf_s` at `0x140047166`
- `ntoskrnl!_snprintf_s` at `0x140047248`
- `ntoskrnl!_snprintf_s` at `0x1400473e5`
- `ntoskrnl!_snprintf_s` at `0x1400474ca`
- `ntoskrnl!_snprintf_s` at `0x14004754d`
- `ntoskrnl!_snprintf_s` at `0x1400475bb`
- `ntoskrnl!_snprintf_s` at `0x140047698`
- `ntoskrnl!_snprintf_s` at `0x140047704`
- `ntoskrnl!_snprintf_s` at `0x140047825`
- `ntoskrnl!_snprintf_s` at `0x1400478ed`
- `ntoskrnl!_snprintf_s` at `0x140047c85`
- `ntoskrnl!_snprintf_s` at `0x140047eb9`
- `ntoskrnl!_snprintf_s` at `0x14004877e`
- `ntoskrnl!_snprintf_s` at `0x1400487fe`
- `ntoskrnl!_snprintf_s` at `0x140046fe5`
- `ntoskrnl!_snprintf_s` at `0x1400470f5`
- `ntoskrnl!_snprintf_s` at `0x140047166`
- `ntoskrnl!_snprintf_s` at `0x140047248`
- `ntoskrnl!_snprintf_s` at `0x1400473e5`
- `ntoskrnl!_snprintf_s` at `0x1400474ca`
- `ntoskrnl!_snprintf_s` at `0x14004754d`
- `ntoskrnl!_snprintf_s` at `0x1400475bb`
- `ntoskrnl!_snprintf_s` at `0x140047698`
- `ntoskrnl!_snprintf_s` at `0x140047704`
- `ntoskrnl!_snprintf_s` at `0x140047825`
- `ntoskrnl!_snprintf_s` at `0x1400478ed`
- `ntoskrnl!_snprintf_s` at `0x140047c85`
- `ntoskrnl!_snprintf_s` at `0x140047eb9`
- `ntoskrnl!_snprintf_s` at `0x14004877e`
- `ntoskrnl!_snprintf_s` at `0x1400487fe`

## string_xrefs

- `0x1400470cd`: `[%c][%cX][%llu]   NEW_TOKEN [Invalid]`
- `0x14004713a`: `[%c][%cX][%llu]   NEW_TOKEN Length:%llu`
- `0x140047e75`: `[%c][%cX][%llu]   NEW_CONN_ID Seq:%llu RPT:%llu CID:%s Token:%s`
- `0x1400481ab`: `[%c][%cX][%llu]   PATH_CHALLENGE [Invalid]`
- `0x1400481ea`: `[%c][%cX][%llu]   PATH_CHALLENGE [%llu]`
- `0x1400485b4`: `[%c][%cX][%llu]   PATH_RESPONSE [Invalid]`
- `0x1400485f3`: `[%c][%cX][%llu]   PATH_RESPONSE [%llu]`

## pseudocode

```c
char __fastcall QuicFrameLog(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, __int64 a5, _WORD *a6)
{
  __int64 v7; // r15
  __int64 v9; // r12
  __int64 v10; // rcx
  unsigned __int16 *v11; // r8
  unsigned __int64 v13; // r13
  __int64 v14; // rax
  int v15; // esi
  __int64 v16; // rcx
  char *v17; // r8
  int v18; // esi
  const char *v19; // r9
  int v20; // esi
  __int64 v21; // rcx
  char *v22; // r8
  int v23; // esi
  const char *v24; // r9
  int v25; // esi
  __int64 v26; // r8
  int v27; // esi
  int v28; // edx
  __int64 v29; // rcx
  int v30; // edx
  __int64 v31; // rcx
  int v32; // r9d
  unsigned __int64 v33; // r8
  int v34; // edx
  __int64 v35; // rcx
  int v36; // r9d
  unsigned __int16 v37; // r13
  _WORD *v38; // r8
  _WORD *v39; // r8
  const char *v40; // r9
  const char *v41; // r9
  int v42; // esi
  const char *v43; // r9
  unsigned __int16 v44; // r9
  unsigned __int16 v45; // dx
  unsigned __int16 v46; // cx
  int v47; // esi
  __int16 v48; // dx
  const char *v49; // r9
  int v50; // esi
  const char *v51; // r9
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r9
  int v55; // esi
  __int64 v56; // rax
  __int64 v57; // r8
  __int64 v58; // rbx
  __int64 v59; // r9
  __int64 v60; // rax
  const char *v61; // r9
  _WORD *v62; // rax
  __int64 v63; // [rsp+20h] [rbp-E0h]
  __int64 v64; // [rsp+28h] [rbp-D8h]
  int v65; // [rsp+28h] [rbp-D8h]
  int v66; // [rsp+28h] [rbp-D8h]
  __int64 v67; // [rsp+30h] [rbp-D0h]
  __int64 v68; // [rsp+30h] [rbp-D0h]
  __int64 v69; // [rsp+30h] [rbp-D0h]
  unsigned __int128 v70; // [rsp+38h] [rbp-C8h]
  unsigned __int128 v71; // [rsp+38h] [rbp-C8h]
  unsigned __int128 v72; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v73; // [rsp+48h] [rbp-B8h]
  __int128 v74; // [rsp+48h] [rbp-B8h]
  _WORD *v75; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+68h] [rbp-98h]
  unsigned __int128 v77; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v78; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v79; // [rsp+88h] [rbp-78h]
  unsigned __int64 v80; // [rsp+90h] [rbp-70h] BYREF
  __int64 v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A0h] [rbp-60h]
  char v83[512]; // [rsp+A8h] [rbp-58h] BYREF
  char v84[520]; // [rsp+2A8h] [rbp+1A8h] BYREF
  char v85[128]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char DstBuf[16]; // [rsp+530h] [rbp+430h] BYREF
  __int128 v87; // [rsp+540h] [rbp+440h] BYREF
  __int128 v88; // [rsp+550h] [rbp+450h]
  __int64 v89; // [rsp+560h] [rbp+460h]
  char v90; // [rsp+568h] [rbp+468h]

  v7 = a2;
  v9 = a3;
  v82 = a3;
  v79 = a4;
  v75 = a6;
  v81 = a5;
  v80 = 0;
  if ( !QuicVarIntDecode(a4, a5, a6, &v80) )
  {
    if ( (byte_14005C48B & 4) != 0 )
      McTemplateU0ps_EtwWriteTransfer(v10, QuicConnError, a1, "Frame type decode failure");
    QuicConnTransportError(a1, 7);
    return 0;
  }
  v13 = v80;
  if ( v80 > 0x31 || (v14 = 0x30002FFFFFFFFLL, !_bittest64(&v14, v80)) )
  {
    if ( v80 == 175 )
    {
      *(_OWORD *)DstBuf = 0;
      v87 = 0;
      if ( !(unsigned __int8)QuicAckFrequencyFrameDecode(a4, a5, v11, DstBuf) )
      {
        if ( byte_14005C48E < 0 )
        {
          if ( a1 )
            v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v27 = 45;
          v41 = "[%c][%cX][%llu]   ACK_FREQUENCY [Invalid]";
          goto LABEL_368;
        }
        return 0;
      }
      if ( (byte_14005C48E & 0x80) == 0 )
        return 1;
      if ( a1 )
        v55 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v55 = 45;
      v61 = "[%c][%cX][%llu]   ACK_FREQUENCY SeqNum:%llu AckElicitThreshold:%llu MaxAckDelay:%llu ReorderThreshold:%llu";
      v74 = v87;
      v72 = *(_OWORD *)DstBuf;
      v69 = v9;
      v66 = PacketLogPrefix[v7 + 2];
      goto LABEL_226;
    }
    if ( v80 != 757 )
    {
      if ( byte_14005C48E >= 0 )
        return 0;
      if ( a1 )
        v15 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v15 = 45;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[%c][%cX][%llu]   unknown frame (%llu)",
        v15,
        PacketLogPrefix[v7 + 2],
        v9,
        v13);
LABEL_15:
      v17 = DstBuf;
      goto LABEL_369;
    }
  }
  if ( v80 > 0xAF )
  {
    v75 = 0;
    if ( !(unsigned __int8)QuicTimestampFrameDecode(a4, a5, v11, &v75) )
    {
      if ( byte_14005C48E < 0 )
      {
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v27 = 45;
        v41 = "[%c][%cX][%llu]   TIMESTAMP [Invalid]";
        goto LABEL_368;
      }
      return 0;
    }
    if ( (byte_14005C48E & 0x80) == 0 )
      return 1;
    if ( a1 )
      v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v47 = 45;
    v49 = "[%c][%cX][%llu]   TIMESTAMP %llu";
    goto LABEL_375;
  }
  if ( v80 > 0x11 )
  {
    if ( v80 > 0x1A )
    {
      switch ( v80 )
      {
        case 0x1BuLL:
          v75 = 0;
          if ( !(unsigned __int8)QuicPathChallengeFrameDecode(a4, a5, v11, &v75) )
          {
            if ( byte_14005C48E < 0 )
            {
              if ( a1 )
                v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
              else
                v27 = 45;
              v41 = "[%c][%cX][%llu]   PATH_RESPONSE [Invalid]";
              goto LABEL_368;
            }
            return 0;
          }
          if ( (byte_14005C48E & 0x80) == 0 )
            return 1;
          if ( a1 )
            v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v47 = 45;
          v49 = "[%c][%cX][%llu]   PATH_RESPONSE [%llu]";
          *(_QWORD *)&v70 = _byteswap_uint64((unsigned __int64)v75);
          goto LABEL_377;
        case 0x1CuLL:
        case 0x1DuLL:
          LOBYTE(v88) = 0;
          *(_OWORD *)DstBuf = 0;
          v87 = 0;
          if ( !(unsigned __int8)QuicConnCloseFrameDecode(v80, a4, a5, (_DWORD)v11, (__int64)DstBuf) )
          {
            if ( byte_14005C48E < 0 )
            {
              if ( a1 )
                v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
              else
                v27 = 45;
              v41 = "[%c][%cX][%llu]   CONN_CLOSE [Invalid]";
              goto LABEL_368;
            }
            return 0;
          }
          if ( DstBuf[0] )
          {
            if ( (byte_14005C48E & 0x80) == 0 )
              return 1;
            if ( a1 )
              v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
            else
              v47 = 45;
            v62 = *(_WORD **)&DstBuf[8];
            v49 = "[%c][%cX][%llu]   CONN_CLOSE (App) ErrorCode:0x%llX";
            goto LABEL_376;
          }
          if ( (byte_14005C48E & 0x80) == 0 )
            return 1;
          if ( a1 )
            v50 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v50 = 45;
          v51 = "[%c][%cX][%llu]   CONN_CLOSE ErrorCode:0x%llX FrameType:%llu";
          *((_QWORD *)&v70 + 1) = v87;
          v52 = *(_QWORD *)&DstBuf[8];
          goto LABEL_193;
        case 0x1EuLL:
          if ( byte_14005C48E >= 0 )
            return 1;
          if ( a1 )
            v42 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v42 = 45;
          v43 = "[%c][%cX][%llu]   HANDSHAKE_DONE";
          break;
        case 0x1FuLL:
          if ( byte_14005C48E >= 0 )
            return 1;
          if ( a1 )
            v42 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v42 = 45;
          v43 = "[%c][%cX][%llu]   IMMEDIATE_ACK";
          break;
        case 0x21uLL:
          *(_OWORD *)DstBuf = 0;
          v87 = 0;
          if ( !(unsigned __int8)QuicAckFrequencyFrameDecode(a4, a5, v11, DstBuf) )
          {
            if ( byte_14005C48E < 0 )
            {
              if ( a1 )
                v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
              else
                v27 = 45;
              v41 = "[%c][%cX][%llu]   RELIABLE_RESET_STREAM [Invalid]";
              goto LABEL_368;
            }
            return 0;
          }
          if ( (byte_14005C48E & 0x80) == 0 )
            return 1;
          if ( a1 )
            v55 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v55 = 45;
          v61 = "[%c][%cX][%llu]   RELIABLE_RESET_STREAM ID:%llu ErrorCode:0x%llX FinalSize:%llu ReliableSize:%llu";
          v74 = v87;
          v72 = *(_OWORD *)DstBuf;
          v69 = v9;
          v66 = PacketLogPrefix[v7 + 2];
          goto LABEL_226;
        default:
          if ( v80 - 48 > 1 )
          {
            CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\frame.c", 2017, "0");
            __int2c();
            return 1;
          }
          LOBYTE(v78) = 0;
          v77 = 0;
          if ( !QuicDatagramFrameDecode(v80, a4, a5, v11, (__int64)&v77) )
          {
            if ( byte_14005C48E < 0 )
            {
              if ( a1 )
                v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
              else
                v27 = 45;
              v41 = "[%c][%cX][%llu]   DATAGRAM [Invalid]";
              goto LABEL_368;
            }
            return 0;
          }
          if ( (byte_14005C48E & 0x80) == 0 )
            return 1;
          if ( a1 )
            v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v47 = 45;
          v49 = "[%c][%cX][%llu]   DATAGRAM Len:%hu";
          LODWORD(v70) = WORD4(v77);
          goto LABEL_377;
      }
LABEL_135:
      _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v43, v42, PacketLogPrefix[v7 + 2], v9);
      goto LABEL_378;
    }
    if ( v80 == 26 )
    {
      v75 = 0;
      if ( !(unsigned __int8)QuicPathChallengeFrameDecode(a4, a5, v11, &v75) )
      {
        if ( byte_14005C48E < 0 )
        {
          if ( a1 )
            v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v27 = 45;
          v41 = "[%c][%cX][%llu]   PATH_CHALLENGE [Invalid]";
          goto LABEL_368;
        }
        return 0;
      }
      if ( (byte_14005C48E & 0x80) == 0 )
        return 1;
      if ( a1 )
        v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v47 = 45;
      v49 = "[%c][%cX][%llu]   PATH_CHALLENGE [%llu]";
      *(_QWORD *)&v70 = _byteswap_uint64((unsigned __int64)v75);
      goto LABEL_377;
    }
    if ( v80 == 18 || v80 == 19 )
    {
      LOBYTE(v76) = 0;
      v75 = 0;
      if ( !(unsigned __int8)QuicMaxStreamsFrameDecode(v80, a4, a5, (_DWORD)v11, (__int64)&v75) )
      {
        if ( byte_14005C48E < 0 )
        {
          if ( a1 )
            v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v27 = 45;
          v41 = "[%c][%cX][%llu]   MAX_STREAMS [Invalid]";
          goto LABEL_368;
        }
        return 0;
      }
      if ( (byte_14005C48E & 0x80) == 0 )
        return 1;
      if ( a1 )
        v50 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v50 = 45;
      v51 = "[%c][%cX][%llu]   MAX_STREAMS[%hu] Count:%llu";
      *((_QWORD *)&v70 + 1) = v76;
      LODWORD(v70) = (unsigned __int8)v75;
      goto LABEL_194;
    }
    if ( v80 != 20 )
    {
      if ( v80 == 21 )
      {
        v77 = 0;
        if ( !(unsigned __int8)QuicStreamDataBlockedFrameDecode(a4, a5, v11, &v77) )
        {
          if ( byte_14005C48E < 0 )
          {
            if ( a1 )
              v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
            else
              v27 = 45;
            v41 = "[%c][%cX][%llu]   STREAM_DATA_BLOCKED [Invalid]";
            goto LABEL_368;
          }
          return 0;
        }
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v50 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v50 = 45;
        v51 = "[%c][%cX][%llu]   STREAM_DATA_BLOCKED ID:%llu Limit:%llu";
LABEL_192:
        *((_QWORD *)&v70 + 1) = *((_QWORD *)&v77 + 1);
        v52 = v77;
LABEL_193:
        *(_QWORD *)&v70 = v52;
LABEL_194:
        LODWORD(v63) = v50;
        _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v51, v63, PacketLogPrefix[v7 + 2], v9, v70);
        goto LABEL_378;
      }
      if ( v80 == 22 || v80 == 23 )
      {
        LOBYTE(v76) = 0;
        v75 = 0;
        if ( !(unsigned __int8)QuicStreamsBlockedFrameDecode(v80, a4, a5, (_DWORD)v11, (__int64)&v75) )
        {
          if ( byte_14005C48E < 0 )
          {
            if ( a1 )
              v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
            else
              v27 = 45;
            v41 = "[%c][%cX][%llu]   STREAMS_BLOCKED [Invalid]";
            goto LABEL_368;
          }
          return 0;
        }
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v50 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v50 = 45;
        v51 = "[%c][%cX][%llu]   STREAMS_BLOCKED[%hu] ID:%llu";
        *((_QWORD *)&v70 + 1) = v76;
        LODWORD(v70) = (unsigned __int8)v75;
        goto LABEL_194;
      }
      if ( v80 != 24 )
      {
        v75 = 0;
        if ( !QuicVarIntDecode(a4, a5, v11, (unsigned __int64 *)&v75) )
        {
          if ( byte_14005C48E < 0 )
          {
            if ( a1 )
              v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
            else
              v27 = 45;
            v41 = "[%c][%cX][%llu]   RETIRE_CONN_ID [Invalid]";
            goto LABEL_368;
          }
          return 0;
        }
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v47 = 45;
        v49 = "[%c][%cX][%llu]   RETIRE_CONN_ID Seq:%llu";
        goto LABEL_375;
      }
      v89 = 0;
      *(_OWORD *)DstBuf = 0;
      v90 = 0;
      v87 = 0;
      v88 = 0;
      if ( !QuicNewConnectionIDFrameDecode(a4, a5, v11, (unsigned __int64 *)DstBuf) )
      {
        if ( byte_14005C48E < 0 )
        {
          if ( a1 )
            v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v27 = 45;
          v41 = "[%c][%cX][%llu]   NEW_CONN_ID [Invalid]";
          goto LABEL_368;
        }
        return 0;
      }
      if ( (byte_14005C48E & 0x80) == 0 )
        return 1;
      if ( a1 )
        v55 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v55 = 45;
      LOBYTE(v53) = 16;
      v56 = QuicCidBufToStr(v83, (char *)&v87 + (unsigned __int8)DstBuf[0] + 8, v53, v54);
      LOBYTE(v57) = DstBuf[0];
      v58 = v56;
      v60 = QuicCidBufToStr(v84, (char *)&v87 + 8, v57, v59);
      v61 = "[%c][%cX][%llu]   NEW_CONN_ID Seq:%llu RPT:%llu CID:%s Token:%s";
      *((_QWORD *)&v74 + 1) = v58;
      *(_QWORD *)&v74 = v60;
      v72 = __PAIR128__(v87, *(unsigned __int64 *)&DstBuf[8]);
      v69 = v9;
      v66 = PacketLogPrefix[v7 + 2];
LABEL_226:
      _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v61, v55, v66, v69, v72, v74);
      goto LABEL_378;
    }
    v75 = 0;
    if ( !QuicVarIntDecode(a4, a5, v11, (unsigned __int64 *)&v75) )
    {
      if ( byte_14005C48E < 0 )
      {
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v27 = 45;
        v41 = "[%c][%cX][%llu]   DATA_BLOCKED [Invalid]";
        goto LABEL_368;
      }
      return 0;
    }
    if ( (byte_14005C48E & 0x80) == 0 )
      return 1;
    if ( a1 )
      v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v47 = 45;
    v49 = "[%c][%cX][%llu]   DATA_BLOCKED Limit:%llu";
LABEL_375:
    v62 = v75;
LABEL_376:
    *(_QWORD *)&v70 = v62;
LABEL_377:
    LODWORD(v63) = v47;
    _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v49, v63, PacketLogPrefix[v7 + 2], v9, (_QWORD)v70);
    goto LABEL_378;
  }
  if ( v80 == 17 )
  {
    v77 = 0;
    if ( !QuicAckBlockDecode(a4, a5, v11, (unsigned __int64 *)&v77) )
    {
      if ( byte_14005C48E < 0 )
      {
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v27 = 45;
        v41 = "[%c][%cX][%llu]   MAX_STREAM_DATA [Invalid]";
        goto LABEL_368;
      }
      return 0;
    }
    if ( (byte_14005C48E & 0x80) == 0 )
      return 1;
    if ( a1 )
      v50 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v50 = 45;
    v51 = "[%c][%cX][%llu]   MAX_STREAM_DATA ID:%llu Max:%llu";
    goto LABEL_192;
  }
  if ( v80 > 8 )
  {
    if ( v80 == 9 || v80 == 10 || v80 == 11 || v80 == 12 || v80 == 13 || v80 == 14 || v80 == 15 )
    {
LABEL_164:
      *(_QWORD *)&v88 = 0;
      *(_OWORD *)DstBuf = 0;
      v87 = 0;
      if ( !QuicStreamFrameDecode(v80, a4, a5, v11, (__int64)DstBuf) )
      {
        if ( byte_14005C48E < 0 )
        {
          if ( a1 )
            v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v27 = 45;
          v41 = "[%c][%cX][%llu]   STREAM [Invalid]";
          goto LABEL_368;
        }
        return 0;
      }
      if ( DstBuf[0] )
      {
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v27 = 45;
        v40 = "[%c][%cX][%llu]   STREAM ID:%llu Offset:%llu Len:%hu Fin";
        LODWORD(v73) = WORD4(v87);
        v71 = __PAIR128__(v87, *(unsigned __int64 *)&DstBuf[8]);
        v68 = v9;
        LODWORD(v64) = PacketLogPrefix[v7 + 2];
      }
      else
      {
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v27 = 45;
        v40 = "[%c][%cX][%llu]   STREAM ID:%llu Offset:%llu Len:%hu";
        LODWORD(v73) = WORD4(v87);
        v71 = __PAIR128__(v87, *(unsigned __int64 *)&DstBuf[8]);
        v68 = v9;
        LODWORD(v64) = PacketLogPrefix[v7 + 2];
      }
      goto LABEL_121;
    }
    v75 = 0;
    if ( !QuicVarIntDecode(a4, a5, v11, (unsigned __int64 *)&v75) )
    {
      if ( byte_14005C48E < 0 )
      {
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v27 = 45;
        v41 = "[%c][%cX][%llu]   MAX_DATA [Invalid]";
        goto LABEL_368;
      }
      return 0;
    }
    if ( (byte_14005C48E & 0x80) == 0 )
      return 1;
    if ( a1 )
      v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v47 = 45;
    v49 = "[%c][%cX][%llu]   MAX_DATA Max:%llu";
    goto LABEL_375;
  }
  switch ( v80 )
  {
    case 8uLL:
      goto LABEL_164;
    case 0uLL:
      v44 = *v11;
      v45 = *v11;
      if ( *v11 < a4 )
      {
        v46 = *v11;
        do
        {
          if ( *(_BYTE *)(v46 + a5) )
            break;
          *v11 = ++v46;
          v45 = v46;
        }
        while ( v46 < a4 );
        v9 = v82;
      }
      if ( byte_14005C48E >= 0 )
        return 1;
      if ( a1 )
        v47 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v47 = 45;
      v48 = v45 - v44;
      v49 = "[%c][%cX][%llu]   PADDING Len:%hu";
      LODWORD(v70) = (unsigned __int16)(v48 + 1);
      goto LABEL_377;
    case 1uLL:
      if ( byte_14005C48E >= 0 )
        return 1;
      if ( a1 )
        v42 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v42 = 45;
      v43 = "[%c][%cX][%llu]   PING";
      goto LABEL_135;
  }
  if ( v80 != 2 && v80 != 3 )
  {
    if ( v80 != 4 )
    {
      if ( v80 == 5 )
      {
        v77 = 0;
        if ( !QuicAckBlockDecode(a4, a5, v11, (unsigned __int64 *)&v77) )
        {
          if ( (byte_14005C48E & 0x80) == 0 )
            return 0;
          if ( a1 )
            v18 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v18 = 45;
          v19 = "[%c][%cX][%llu]   STOP_SENDING [Invalid]";
          goto LABEL_34;
        }
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v23 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v23 = 45;
        v24 = "[%c][%cX][%llu]   STOP_SENDING ID:%llu Error:0x%llX";
        v70 = v77;
        v67 = v9;
        v65 = PacketLogPrefix[v7 + 2];
      }
      else
      {
        if ( v80 != 6 )
        {
          v77 = 0;
          if ( !(unsigned __int8)QuicNewTokenFrameDecode(a4, a5, v11, &v77) )
          {
            if ( (byte_14005C48E & 0x80) == 0 )
              return 0;
            if ( a1 )
              v18 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
            else
              v18 = 45;
            v19 = "[%c][%cX][%llu]   NEW_TOKEN [Invalid]";
LABEL_34:
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v19, v18, PacketLogPrefix[v7 + 2], v9);
            goto LABEL_15;
          }
          if ( byte_14005C48E < 0 )
          {
            if ( a1 )
              v20 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
            else
              v20 = 45;
            _snprintf_s(
              DstBuf,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "[%c][%cX][%llu]   NEW_TOKEN Length:%llu",
              v20,
              PacketLogPrefix[v7 + 2],
              v9,
              (_QWORD)v77);
            goto LABEL_40;
          }
          return 1;
        }
        v78 = 0;
        v77 = 0;
        if ( !QuicCryptoFrameDecode(a4, a5, v11, (unsigned __int64 *)&v77) )
        {
          if ( (byte_14005C48E & 0x80) == 0 )
            return 0;
          if ( a1 )
            v18 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
          else
            v18 = 45;
          v19 = "[%c][%cX][%llu]   CRYPTO [Invalid]";
          goto LABEL_34;
        }
        if ( (byte_14005C48E & 0x80) == 0 )
          return 1;
        if ( a1 )
          v23 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v23 = 45;
        v24 = "[%c][%cX][%llu]   CRYPTO Offset:%llu Len:%hu";
        DWORD2(v70) = WORD4(v77);
        *(_QWORD *)&v70 = v77;
        v67 = v9;
        v65 = PacketLogPrefix[v7 + 2];
      }
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v24, v23, v65, v67, v70);
LABEL_40:
      v22 = DstBuf;
LABEL_379:
      McTemplateU0s_EtwWriteTransfer(v21, QuicLogVerbose, v22);
      return 1;
    }
    v78 = 0;
    v77 = 0;
    if ( !(unsigned __int8)QuicResetStreamFrameDecode(a4, a5, v11, &v77) )
    {
      if ( (byte_14005C48E & 0x80) == 0 )
        return 0;
      if ( a1 )
        v18 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v18 = 45;
      v19 = "[%c][%cX][%llu]   RESET_STREAM [Invalid]";
      goto LABEL_34;
    }
    if ( byte_14005C48E < 0 )
    {
      if ( a1 )
        v25 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v25 = 45;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[%c][%cX][%llu]   RESET_STREAM ID:%llu ErrorCode:0x%llX FinalSize:%llu",
        v25,
        PacketLogPrefix[v7 + 2],
        v9,
        (_QWORD)v77,
        *((_QWORD *)&v77 + 1),
        v78);
      goto LABEL_40;
    }
    return 1;
  }
  *(_OWORD *)DstBuf = 0;
  v87 = 0;
  if ( !QuicAckHeaderDecode(a4, a5, v11, (unsigned __int64 *)DstBuf) )
  {
    if ( (byte_14005C48E & 0x80) == 0 )
      return 0;
    if ( a1 )
      v18 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v18 = 45;
    v19 = "[%c][%cX][%llu]   ACK [Invalid]";
    goto LABEL_34;
  }
  v26 = *(_QWORD *)DstBuf;
  v27 = 45;
  if ( byte_14005C48E < 0 )
  {
    if ( a1 )
      v28 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v28 = 45;
    _snprintf_s(
      v85,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[%c][%cX][%llu]   ACK Largest:%llu Delay:%llu",
      v28,
      PacketLogPrefix[v7 + 2],
      v9,
      v26,
      *(_QWORD *)&DstBuf[8]);
    McTemplateU0s_EtwWriteTransfer(v29, QuicLogVerbose, v85);
    v26 = *(_QWORD *)DstBuf;
  }
  if ( *((_QWORD *)&v87 + 1) )
  {
    if ( (byte_14005C48E & 0x80) == 0 )
      goto LABEL_98;
    if ( a1 )
      v32 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v32 = 45;
    LODWORD(v64) = PacketLogPrefix[v7 + 2];
    LODWORD(v63) = v32;
    _snprintf_s(
      v85,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[%c][%cX][%llu]     %llu - %llu",
      v63,
      v64,
      v9,
      v26 - *((_QWORD *)&v87 + 1),
      v26);
  }
  else
  {
    if ( (byte_14005C48E & 0x80) == 0 )
      goto LABEL_98;
    if ( a1 )
      v30 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    else
      v30 = 45;
    LODWORD(v64) = PacketLogPrefix[v7 + 2];
    LODWORD(v63) = v30;
    _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%c][%cX][%llu]     %llu", v63, v64, v9, v26);
  }
  McTemplateU0s_EtwWriteTransfer(v31, QuicLogVerbose, v85);
LABEL_98:
  v82 = 0;
  v80 = -1LL - *((_QWORD *)&v87 + 1) + *(_QWORD *)DstBuf;
  if ( !(_QWORD)v87 )
  {
LABEL_113:
    if ( v13 != 3 )
      return 1;
    v37 = v79;
    v78 = 0;
    v77 = 0;
    if ( !QuicVarIntDecode(v79, v81, v75, (unsigned __int64 *)&v77)
      || !QuicVarIntDecode(v37, v81, v38, (unsigned __int64 *)&v77 + 1)
      || !QuicVarIntDecode(v37, v81, v39, &v78) )
    {
      if ( byte_14005C48E < 0 )
      {
        if ( a1 )
          v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        v41 = "[%c][%cX][%llu]     ECN [Invalid]";
        goto LABEL_368;
      }
      return 0;
    }
    if ( (byte_14005C48E & 0x80) == 0 )
      return 1;
    if ( a1 )
      v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    v40 = "[%c][%cX][%llu]     ECN [ECT0=%llu,ECT1=%llu,CE=%llu]";
    v73 = v78;
    v71 = v77;
    v68 = v9;
    LODWORD(v64) = PacketLogPrefix[v7 + 2];
LABEL_121:
    LODWORD(v63) = v27;
    _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v40, v63, v64, v68, v71, v73);
LABEL_378:
    v22 = v85;
    goto LABEL_379;
  }
  while ( 1 )
  {
    v77 = 0;
    if ( !QuicAckBlockDecode(v79, v81, v75, (unsigned __int64 *)&v77) )
      break;
    v33 = v80 - v77 - 1;
    v80 = v33;
    if ( *((_QWORD *)&v77 + 1) )
    {
      if ( byte_14005C48E < 0 )
      {
        if ( a1 )
          v36 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
        else
          v36 = 45;
        LODWORD(v64) = PacketLogPrefix[v7 + 2];
        LODWORD(v63) = v36;
        _snprintf_s(
          v85,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "[%c][%cX][%llu]     %llu - %llu",
          v63,
          v64,
          v9,
          v33 - *((_QWORD *)&v77 + 1),
          v33);
        goto LABEL_111;
      }
    }
    else if ( byte_14005C48E < 0 )
    {
      if ( a1 )
        v34 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
      else
        v34 = 45;
      LODWORD(v64) = PacketLogPrefix[v7 + 2];
      LODWORD(v63) = v34;
      _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%c][%cX][%llu]     %llu", v63, v64, v9, v33);
LABEL_111:
      McTemplateU0s_EtwWriteTransfer(v35, QuicLogVerbose, v85);
      v33 = v80;
    }
    v80 = -1LL - *((_QWORD *)&v77 + 1) + v33;
    if ( ++v82 >= (unsigned __int64)v87 )
      goto LABEL_113;
  }
  if ( byte_14005C48E < 0 )
  {
    if ( a1 )
      v27 = PacketLogPrefix[(unsigned __int8)QuicConnIsServer(a1)];
    v41 = "[%c][%cX][%llu]     [Invalid Block]";
LABEL_368:
    LODWORD(v64) = PacketLogPrefix[v7 + 2];
    LODWORD(v63) = v27;
    _snprintf_s(v85, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v41, v63, v64, v9);
    v17 = v85;
LABEL_369:
    McTemplateU0s_EtwWriteTransfer(v16, QuicLogVerbose, v17);
  }
  return 0;
}

```

## disassembly

```asm
0x140046ea8  mov     [rsp-8+arg_18], rbx
0x140046ead  push    rbp
0x140046eae  push    rsi
0x140046eaf  push    rdi
0x140046eb0  push    r12
0x140046eb2  push    r13
0x140046eb4  push    r14
0x140046eb6  push    r15
0x140046eb8  lea     rbp, [rsp-4C0h]
0x140046ec0  sub     rsp, 5C0h
0x140046ec7  mov     rax, cs:__security_cookie
0x140046ece  xor     rax, rsp
0x140046ed1  mov     [rbp+4F0h+var_40], rax
0x140046ed8  mov     rsi, [rbp+4F0h+arg_20]
0x140046edf  movzx   edi, r9w
0x140046ee3  movzx   r15d, dl
0x140046ee7  mov     rbx, rcx
0x140046eea  mov     r12, r8
0x140046eed  mov     [rbp+4F0h+var_550], r8
0x140046ef1  mov     r8, [rbp+4F0h+arg_28]
0x140046ef8  xor     r14d, r14d
0x140046efb  mov     [rbp+4F0h+var_568], r9w
0x140046f00  mov     rdx, rsi
0x140046f03  movzx   ecx, di
0x140046f06  mov     [rsp+5F0h+var_590], r8
0x140046f0b  lea     r9, [rbp+4F0h+var_560]
0x140046f0f  mov     [rbp+4F0h+var_558], rsi
0x140046f13  mov     [rbp+4F0h+var_560], r14
0x140046f17  call    QuicVarIntDecode
0x140046f1c  test    al, al
0x140046f1e  jnz     short loc_140046F53
0x140046f20  test    cs:byte_14005C48B, 4
0x140046f27  jz      short loc_140046F3F
0x140046f29  lea     r9, aFrameTypeDecod; "Frame type decode failure"
0x140046f30  mov     r8, rbx
0x140046f33  lea     rdx, QuicConnError
0x140046f3a  call    McTemplateU0ps_EtwWriteTransfer
0x140046f3f  mov     edx, 7
0x140046f44  mov     rcx, rbx
0x140046f47  call    QuicConnTransportError
0x140046f4c  xor     al, al
0x140046f4e  jmp     loc_140048822
0x140046f53  mov     r13, [rbp+4F0h+var_560]
0x140046f57  mov     edx, 2F5h
0x140046f5c  mov     ecx, 0AFh
0x140046f61  cmp     r13, 31h ; '1'
0x140046f65  ja      short loc_140046F7B
0x140046f67  mov     rax, 30002FFFFFFFFh
0x140046f71  bt      rax, r13
0x140046f75  jb      loc_140046FFD
0x140046f7b  cmp     r13, rcx
0x140046f7e  jz      loc_140048607
0x140046f84  cmp     r13, rdx
0x140046f87  jz      short loc_140046FFD
0x140046f89  mov     edi, 80h
0x140046f8e  test    cs:byte_14005C48E, dil
0x140046f95  jz      short loc_140046F4C
0x140046f97  lea     r14, PacketLogPrefix; "CSTR"
0x140046f9e  test    rbx, rbx
0x140046fa1  jnz     short loc_140046FA8
0x140046fa3  lea     esi, [rdi-53h]
0x140046fa6  jmp     short loc_140046FB8
0x140046fa8  mov     rcx, rbx
0x140046fab  call    QuicConnIsServer
0x140046fb0  movzx   ecx, al
0x140046fb3  movsx   esi, byte ptr [rcx+r14]
0x140046fb8  movsx   ecx, byte ptr [r15+r14+2]
0x140046fbe  lea     r9, aCCxLluUnknownF; "[%c][%cX][%llu]   unknown frame (%llu)"
0x140046fc5  mov     qword ptr [rsp+5F0h+var_5B8], r13
0x140046fca  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140046fce  mov     [rsp+5F0h+var_5C0], r12
0x140046fd3  mov     rdx, rdi; SizeInBytes
0x140046fd6  mov     dword ptr [rsp+5F0h+var_5C8], ecx
0x140046fda  lea     rcx, [rbp+4F0h+DstBuf]; DstBuf
0x140046fe1  mov     dword ptr [rsp+5F0h+var_5D0], esi
0x140046fe5  call    cs:__imp__snprintf_s
0x140046fec  nop     dword ptr [rax+rax+00h]
0x140046ff1  lea     r8, [rbp+4F0h+DstBuf]
0x140046ff8  jmp     loc_140048791
0x140046ffd  cmp     r13, rcx
0x140047000  ja      loc_1400486E6
0x140047006  jz      loc_140048607
0x14004700c  cmp     r13, 11h
0x140047010  ja      loc_140047C96
0x140047016  jz      loc_140047BC0
0x14004701c  cmp     r13, 8
0x140047020  ja      loc_140047980
0x140047026  jz      loc_140047A65
0x14004702c  mov     rax, r13
0x14004702f  test    r13, r13
0x140047032  jz      loc_1400478FE
0x140047038  sub     rax, 1
0x14004703c  jz      loc_140047892
0x140047042  sub     rax, 1
0x140047046  jz      loc_1400473F6
0x14004704c  sub     rax, 1
0x140047050  jz      loc_1400473F6
0x140047056  sub     rax, 1
0x14004705a  jz      loc_140047311
0x140047060  sub     rax, 1
0x140047064  jz      loc_140047259
0x14004706a  sub     rax, 1
0x14004706e  jz      loc_14004717E
0x140047074  cmp     rax, 1
0x140047078  jnz     loc_1400486EB
0x14004707e  xorps   xmm0, xmm0
0x140047081  lea     r9, [rsp+5F0h+var_580]
0x140047086  mov     rdx, rsi
0x140047089  movzx   ecx, di
0x14004708c  movups  [rsp+5F0h+var_580], xmm0
0x140047091  call    QuicNewTokenFrameDecode
0x140047096  mov     edi, 80h
0x14004709b  test    al, al
0x14004709d  jnz     short loc_140047106
0x14004709f  test    cs:byte_14005C48E, dil
0x1400470a6  jz      loc_140046F4C
0x1400470ac  lea     r14, PacketLogPrefix; "CSTR"
0x1400470b3  test    rbx, rbx
0x1400470b6  jnz     short loc_1400470BD
0x1400470b8  lea     esi, [rdi-53h]
0x1400470bb  jmp     short loc_1400470CD
0x1400470bd  mov     rcx, rbx
0x1400470c0  call    QuicConnIsServer
0x1400470c5  movzx   ecx, al
0x1400470c8  movsx   esi, byte ptr [rcx+r14]
0x1400470cd  lea     r9, aCCxLluNewToken_0; "[%c][%cX][%llu]   NEW_TOKEN [Invalid]"
0x1400470d4  movsx   eax, byte ptr [r15+r14+2]
0x1400470da  lea     rcx, [rbp+4F0h+DstBuf]; DstBuf
0x1400470e1  mov     [rsp+5F0h+var_5C0], r12
0x1400470e6  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400470ea  mov     dword ptr [rsp+5F0h+var_5C8], eax
0x1400470ee  mov     rdx, rdi; SizeInBytes
0x1400470f1  mov     dword ptr [rsp+5F0h+var_5D0], esi
0x1400470f5  call    cs:__imp__snprintf_s
0x1400470fc  nop     dword ptr [rax+rax+00h]
0x140047101  jmp     loc_140046FF1
0x140047106  test    cs:byte_14005C48E, dil
0x14004710d  jz      loc_14004881D
0x140047113  lea     r14, PacketLogPrefix; "CSTR"
0x14004711a  test    rbx, rbx
0x14004711d  jnz     short loc_140047124
0x14004711f  lea     esi, [rbx+2Dh]
0x140047122  jmp     short loc_140047134
0x140047124  mov     rcx, rbx
0x140047127  call    QuicConnIsServer
0x14004712c  movzx   ecx, al
0x14004712f  movsx   esi, byte ptr [rcx+r14]
0x140047134  movsx   ecx, byte ptr [r15+r14+2]
0x14004713a  lea     r9, aCCxLluNewToken; "[%c][%cX][%llu]   NEW_TOKEN Length:%llu"
0x140047141  mov     rax, qword ptr [rsp+5F0h+var_580]
0x140047146  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14004714a  mov     qword ptr [rsp+5F0h+var_5B8], rax
0x14004714f  mov     rdx, rdi; SizeInBytes
0x140047152  mov     [rsp+5F0h+var_5C0], r12
0x140047157  mov     dword ptr [rsp+5F0h+var_5C8], ecx
0x14004715b  lea     rcx, [rbp+4F0h+DstBuf]; DstBuf
0x140047162  mov     dword ptr [rsp+5F0h+var_5D0], esi
0x140047166  call    cs:__imp__snprintf_s
0x14004716d  nop     dword ptr [rax+rax+00h]
0x140047172  lea     r8, [rbp+4F0h+DstBuf]
0x140047179  jmp     loc_140048811
0x14004717e  xor     eax, eax
0x140047180  lea     r9, [rsp+5F0h+var_580]
0x140047185  xorps   xmm0, xmm0
0x140047188  mov     [rbp+4F0h+var_570], rax
0x14004718c  mov     rdx, rsi
0x14004718f  movzx   ecx, di
0x140047192  movups  [rsp+5F0h+var_580], xmm0
0x140047197  call    QuicCryptoFrameDecode
0x14004719c  mov     edi, 80h
0x1400471a1  test    al, al
0x1400471a3  jnz     short loc_1400471DF
0x1400471a5  test    cs:byte_14005C48E, dil
0x1400471ac  jz      loc_140046F4C
0x1400471b2  lea     r14, PacketLogPrefix; "CSTR"
0x1400471b9  test    rbx, rbx
0x1400471bc  jnz     short loc_1400471C3
0x1400471be  lea     esi, [rdi-53h]
0x1400471c1  jmp     short loc_1400471D3
0x1400471c3  mov     rcx, rbx
0x1400471c6  call    QuicConnIsServer
0x1400471cb  movzx   ecx, al
0x1400471ce  movsx   esi, byte ptr [rcx+r14]
0x1400471d3  lea     r9, aCCxLluCryptoIn; "[%c][%cX][%llu]   CRYPTO [Invalid]"
0x1400471da  jmp     loc_1400470D4
0x1400471df  test    cs:byte_14005C48E, dil
0x1400471e6  jz      loc_14004881D
0x1400471ec  lea     r14, PacketLogPrefix; "CSTR"
0x1400471f3  test    rbx, rbx
0x1400471f6  jnz     short loc_1400471FD
0x1400471f8  lea     esi, [rbx+2Dh]
0x1400471fb  jmp     short loc_14004720D
0x1400471fd  mov     rcx, rbx
0x140047200  call    QuicConnIsServer
0x140047205  movzx   ecx, al
0x140047208  movsx   esi, byte ptr [rcx+r14]
0x14004720d  movzx   ecx, word ptr [rsp+5F0h+var_580+8]
0x140047212  lea     r9, aCCxLluCryptoOf; "[%c][%cX][%llu]   CRYPTO Offset:%llu Le"...
0x140047219  mov     rax, qword ptr [rsp+5F0h+var_580]
0x14004721e  movsx   edx, byte ptr [r15+r14+2]
0x140047224  mov     dword ptr [rsp+5F0h+var_5B8+8], ecx
0x140047228  mov     qword ptr [rsp+5F0h+var_5B8], rax
0x14004722d  mov     [rsp+5F0h+var_5C0], r12
0x140047232  mov     dword ptr [rsp+5F0h+var_5C8], edx
0x140047236  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14004723a  mov     dword ptr [rsp+5F0h+var_5D0], esi
0x14004723e  mov     rdx, rdi; SizeInBytes
0x140047241  lea     rcx, [rbp+4F0h+DstBuf]; DstBuf
0x140047248  call    cs:__imp__snprintf_s
0x14004724f  nop     dword ptr [rax+rax+00h]
0x140047254  jmp     loc_140047172
0x140047259  xorps   xmm0, xmm0
0x14004725c  lea     r9, [rsp+5F0h+var_580]
0x140047261  mov     rdx, rsi
0x140047264  movzx   ecx, di
0x140047267  movups  [rsp+5F0h+var_580], xmm0
0x14004726c  call    QuicAckBlockDecode
0x140047271  mov     edi, 80h
0x140047276  test    al, al
0x140047278  jnz     short loc_1400472B4
0x14004727a  test    cs:byte_14005C48E, dil
0x140047281  jz      loc_140046F4C
0x140047287  lea     r14, PacketLogPrefix; "CSTR"
0x14004728e  test    rbx, rbx
0x140047291  jnz     short loc_140047298
0x140047293  lea     esi, [rdi-53h]
0x140047296  jmp     short loc_1400472A8
0x140047298  mov     rcx, rbx
0x14004729b  call    QuicConnIsServer
0x1400472a0  movzx   ecx, al
0x1400472a3  movsx   esi, byte ptr [rcx+r14]
0x1400472a8  lea     r9, aCCxLluStopSend_0; "[%c][%cX][%llu]   STOP_SENDING [Invalid"...
0x1400472af  jmp     loc_1400470D4
0x1400472b4  test    cs:byte_14005C48E, dil
0x1400472bb  jz      loc_14004881D
0x1400472c1  lea     r14, PacketLogPrefix; "CSTR"
0x1400472c8  test    rbx, rbx
0x1400472cb  jnz     short loc_1400472D2
0x1400472cd  lea     esi, [rbx+2Dh]
0x1400472d0  jmp     short loc_1400472E2
0x1400472d2  mov     rcx, rbx
0x1400472d5  call    QuicConnIsServer
0x1400472da  movzx   ecx, al
0x1400472dd  movsx   esi, byte ptr [rcx+r14]
0x1400472e2  mov     rax, qword ptr [rsp+5F0h+var_580+8]
0x1400472e7  lea     r9, aCCxLluStopSend; "[%c][%cX][%llu]   STOP_SENDING ID:%llu "...
0x1400472ee  movsx   ecx, byte ptr [r15+r14+2]
0x1400472f4  mov     qword ptr [rsp+5F0h+var_5B8+8], rax
0x1400472f9  mov     rax, qword ptr [rsp+5F0h+var_580]
0x1400472fe  mov     qword ptr [rsp+5F0h+var_5B8], rax
0x140047303  mov     [rsp+5F0h+var_5C0], r12
0x140047308  mov     dword ptr [rsp+5F0h+var_5C8], ecx
0x14004730c  jmp     loc_140047236
0x140047311  xor     eax, eax
0x140047313  lea     r9, [rsp+5F0h+var_580]
0x140047318  xorps   xmm0, xmm0
0x14004731b  mov     [rbp+4F0h+var_570], rax
0x14004731f  mov     rdx, rsi
0x140047322  movzx   ecx, di
0x140047325  movups  [rsp+5F0h+var_580], xmm0
0x14004732a  call    QuicResetStreamFrameDecode
0x14004732f  mov     edi, 80h
0x140047334  test    al, al
0x140047336  jnz     short loc_140047372
0x140047338  test    cs:byte_14005C48E, dil
0x14004733f  jz      loc_140046F4C
0x140047345  lea     r14, PacketLogPrefix; "CSTR"
0x14004734c  test    rbx, rbx
0x14004734f  jnz     short loc_140047356
0x140047351  lea     esi, [rdi-53h]
0x140047354  jmp     short loc_140047366
0x140047356  mov     rcx, rbx
0x140047359  call    QuicConnIsServer
0x14004735e  movzx   ecx, al
0x140047361  movsx   esi, byte ptr [rcx+r14]
0x140047366  lea     r9, aCCxLluResetStr; "[%c][%cX][%llu]   RESET_STREAM [Invalid"...
0x14004736d  jmp     loc_1400470D4
0x140047372  test    cs:byte_14005C48E, dil
0x140047379  jz      loc_14004881D
0x14004737f  lea     r14, PacketLogPrefix; "CSTR"
0x140047386  test    rbx, rbx
0x140047389  jnz     short loc_140047390
0x14004738b  lea     esi, [rbx+2Dh]
0x14004738e  jmp     short loc_1400473A0
0x140047390  mov     rcx, rbx
0x140047393  call    QuicConnIsServer
0x140047398  movzx   ecx, al
0x14004739b  movsx   esi, byte ptr [rcx+r14]
0x1400473a0  movsx   ecx, byte ptr [r15+r14+2]
0x1400473a6  lea     r9, aCCxLluResetStr_0; "[%c][%cX][%llu]   RESET_STREAM ID:%llu "...
0x1400473ad  mov     rax, [rbp+4F0h+var_570]
0x1400473b1  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400473b5  mov     qword ptr [rsp+5F0h+var_5A8], rax
0x1400473ba  mov     rdx, rdi; SizeInBytes
0x1400473bd  mov     rax, qword ptr [rsp+5F0h+var_580+8]
0x1400473c2  mov     qword ptr [rsp+5F0h+var_5B8+8], rax
0x1400473c7  mov     rax, qword ptr [rsp+5F0h+var_580]
0x1400473cc  mov     qword ptr [rsp+5F0h+var_5B8], rax
0x1400473d1  mov     [rsp+5F0h+var_5C0], r12
0x1400473d6  mov     dword ptr [rsp+5F0h+var_5C8], ecx
  ... truncated ...
```
