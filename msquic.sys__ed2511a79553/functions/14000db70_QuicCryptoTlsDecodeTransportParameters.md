# QuicCryptoTlsDecodeTransportParameters

- ea: `0x14000db70`
- end: `0x14000ed03`
- name: `QuicCryptoTlsDecodeTransportParameters`
- size: `4499`
- prototype: `char __fastcall(__int64, unsigned __int8, __int64, unsigned __int16, char *)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001df60`
- `0x140020e98`
- `0x140045e34`
- `0x1400460b4`

## callees

- `0x14000db70`
- `0x14000ed10`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003ed00`
- `0x14003fdf8`
- `0x140040b80`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000dc47`
- `ntoskrnl!_snprintf_s` at `0x14000ddb6`
- `ntoskrnl!_snprintf_s` at `0x14000e13b`
- `ntoskrnl!_snprintf_s` at `0x14000e199`
- `ntoskrnl!_snprintf_s` at `0x14000e463`
- `ntoskrnl!_snprintf_s` at `0x14000e51c`
- `ntoskrnl!_snprintf_s` at `0x14000e647`
- `ntoskrnl!_snprintf_s` at `0x14000dc47`
- `ntoskrnl!_snprintf_s` at `0x14000ddb6`
- `ntoskrnl!_snprintf_s` at `0x14000e13b`
- `ntoskrnl!_snprintf_s` at `0x14000e199`
- `ntoskrnl!_snprintf_s` at `0x14000e463`
- `ntoskrnl!_snprintf_s` at `0x14000e51c`
- `ntoskrnl!_snprintf_s` at `0x14000e647`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dbdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dbdc`
- `ntoskrnl!ExAllocatePool2` at `0x14000e32e`
- `ntoskrnl!ExAllocatePool2` at `0x14000e32e`

## string_xrefs

- `0x14000de83`: `TP: Stateless Reset Token (%s)`
- `0x14000e777`: `Invalid length of QUIC_TP_ID_STATELESS_RESET_TOKEN`
- `0x14000e75e`: `Client incorrectly provided stateless reset token`

## pseudocode

```c
char __fastcall QuicCryptoTlsDecodeTransportParameters(
        __int64 a1,
        unsigned __int8 a2,
        __int64 a3,
        unsigned __int16 a4,
        char *a5)
{
  int v6; // edi
  int v7; // r13d
  __int64 v9; // r15
  void *v10; // rcx
  unsigned __int64 *v11; // rsi
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  __int64 v15; // r9
  __int64 v16; // r13
  unsigned __int16 v17; // di
  __int64 v18; // r15
  __int64 v19; // r9
  __int64 v20; // rax
  const char *v21; // r9
  __int64 v22; // rcx
  __int64 *v23; // rdx
  unsigned __int16 v24; // r13
  int v25; // ecx
  __int64 *v26; // r9
  int v27; // ecx
  unsigned __int64 *v28; // r9
  int v29; // ecx
  __int64 *v30; // r9
  int v31; // ecx
  __int64 *v32; // r9
  int v33; // ecx
  __int64 *v34; // r9
  int v35; // ecx
  __int64 *v36; // r9
  int v37; // ecx
  unsigned __int64 *v38; // r9
  int v39; // ecx
  unsigned __int64 *v40; // r9
  int v41; // ecx
  unsigned __int64 *v42; // r9
  int v43; // ecx
  __int64 v44; // rcx
  int v45; // ecx
  unsigned __int64 *v46; // r9
  __int64 v47; // r9
  __int64 v48; // r9
  int v49; // ecx
  __int64 *v50; // r9
  void *Pool2; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r15
  __int64 v55; // rcx
  __int64 *v56; // r9
  __int64 v57; // rdx
  const char *v58; // r9
  int v59; // ecx
  unsigned __int64 *v60; // r9
  int v61; // esi
  __int64 v62; // rcx
  const char *v63; // r9
  __int64 v65; // [rsp+20h] [rbp-E0h]
  __int64 v66; // [rsp+28h] [rbp-D8h]
  __int64 v67; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v68; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v69; // [rsp+40h] [rbp-C0h]
  char v70[520]; // [rsp+48h] [rbp-B8h] BYREF
  char DstBuf[128]; // [rsp+250h] [rbp+150h] BYREF

  v6 = a4;
  v7 = a2;
  HIWORD(v67) = a4;
  v9 = 0;
  v10 = (void *)*((_QWORD *)a5 + 31);
  BYTE4(v67) = a2;
  v69 = 0;
  LOWORD(v67) = 0;
  if ( v10 )
    ExFreePoolWithTag(v10, 0x32346351u);
  memset(a5, 0, 0x100u);
  v11 = (unsigned __int64 *)(a5 + 80);
  *((_QWORD *)a5 + 8) = 65527;
  *((_QWORD *)a5 + 10) = 25;
  *((_QWORD *)a5 + 9) = 3;
  *((_QWORD *)a5 + 12) = 2;
  if ( (byte_14005C48C & 1) != 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "Decoding Transport Parameters (Server = %hhu) (%hu bytes)",
      v7,
      v6);
    McTemplateU0ps_EtwWriteTransfer(v12, QuicConnLogVerbose, a1, DstBuf);
  }
  v13 = 0;
  if ( !(_WORD)v6 )
  {
LABEL_214:
    if ( (*(_DWORD *)a5 & 0x100000) == 0 || *((_QWORD *)a5 + 11) <= 1000 * *v11 )
      return 1;
    if ( (byte_14005C48B & 4) == 0 )
      return 0;
    v63 = "MIN_ACK_DELAY is larger than MAX_ACK_DELAY";
LABEL_134:
    McTemplateU0ps_EtwWriteTransfer(v13, QuicConnError, a1, v63);
    return 0;
  }
  while ( 1 )
  {
    v68 = 0;
    if ( !QuicVarIntDecode(v6, a3, &v67, &v68) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return 0;
      v63 = "No room for QUIC TP ID";
      goto LABEL_134;
    }
    v14 = v68;
    if ( v68 < 0x40 )
    {
      if ( _bittest64(&v9, v68) )
      {
        if ( (byte_14005C48B & 4) == 0 )
          return 0;
        v63 = "Duplicate QUIC TP ID";
        goto LABEL_134;
      }
      v69 = v9 | (1LL << v68);
    }
    v68 = 0;
    if ( !QuicVarIntDecode(v6, a3, &v67, &v68) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return 0;
      v63 = "No room for QUIC TP length";
      goto LABEL_134;
    }
    v16 = (unsigned __int16)v67;
    v17 = v68;
    v18 = (unsigned __int16)v67;
    v13 = v68 + (unsigned __int16)v67;
    if ( v13 > HIWORD(v67) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return 0;
      v63 = "QUIC TP length too big";
      goto LABEL_134;
    }
    v13 = 0;
    LOWORD(v67) = 0;
    if ( v14 <= 0x1000 )
    {
      if ( v14 == 4096 )
      {
        v54 = a3 + v18;
        if ( !QuicVarIntDecode(v68, v54, &v67, (unsigned __int64 *)a5 + 17)
          || (unsigned __int64)(*((_QWORD *)a5 + 17) - 1LL) > 0xFE
          || !QuicVarIntDecode(v17, v54, &v67, (unsigned __int64 *)a5 + 18)
          || (v55 = *v56, (unsigned __int64)*v56 > 0xFF)
          || (v57 = *((_QWORD *)a5 + 17), (unsigned __int64)(v55 + v57) > 0xFF) )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              v55,
              (unsigned int)QuicConnErrorStatus,
              a1,
              v17,
              (__int64)"Invalid QUIC_TP_ID_CIBIR_ENCODING");
          return 0;
        }
        *(_DWORD *)a5 |= 0x200000u;
        if ( (byte_14005C48C & 1) == 0 )
          goto LABEL_22;
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: CIBIR Encoding (%llu length, %llu offset)", v57, v55);
      }
      else
      {
        switch ( v14 )
        {
          case 0uLL:
            if ( (unsigned __int16)v68 > 0x14u )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  0,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  (unsigned __int16)v68,
                  (__int64)"Invalid length of QUIC_TP_ID_ORIGINAL_DESTINATION_CONNECTION_ID");
              return 0;
            }
            if ( !BYTE4(v67) )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Client incorrectly provided original destination connection ID";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x2000u;
            a5[216] = v17;
            memmove(a5 + 196, (const void *)(a3 + v16), v17);
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = QuicCidBufToStr(v70, a5 + 196, (unsigned __int8)a5[216], v19);
            v21 = "TP: Original Connection Destination ID (%s)";
            goto LABEL_19;
          case 1uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 1) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v25,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_IDLE_TIMEOUT");
              return 0;
            }
            *(_DWORD *)a5 |= 0x800u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = *v26;
            v21 = "TP: Idle Timeout (%llu ms)";
            goto LABEL_19;
          case 2uLL:
            if ( (_WORD)v68 != 16 )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  0,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  (unsigned __int16)v68,
                  (__int64)"Invalid length of QUIC_TP_ID_STATELESS_RESET_TOKEN");
              return 0;
            }
            if ( !BYTE4(v67) )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Client incorrectly provided stateless reset token";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x100u;
            *(_OWORD *)(a5 + 152) = *(_OWORD *)(v16 + a3);
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_131;
            v20 = QuicCidBufToStr(v70, a5 + 152, 16, v15);
            v21 = "TP: Stateless Reset Token (%s)";
            goto LABEL_19;
          case 3uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 8) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v27,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_MAX_UDP_PAYLOAD_SIZE");
              return 0;
            }
            v13 = *v28;
            if ( *v28 < 0x4B0 )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "TP MaxUdpPayloadSize too small";
              goto LABEL_134;
            }
            if ( v13 > 0xFFF7 )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "TP MaxUdpPayloadSize too big";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x40u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Udp Payload Size (%llu bytes)", v13);
            break;
          case 4uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 5) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v29,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_MAX_DATA");
              return 0;
            }
            *(_DWORD *)a5 |= 1u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = *v30;
            v21 = "TP: Max Data (%llu bytes)";
            goto LABEL_19;
          case 5uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 2) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v31,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_MAX_STREAM_DATA_BIDI_LOCAL");
              return 0;
            }
            *(_DWORD *)a5 |= 2u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = *v32;
            v21 = "TP: Max Local Bidirectional Stream Data (%llu bytes)";
            goto LABEL_19;
          case 6uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 3) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v33,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_MAX_STREAM_DATA_BIDI_REMOTE");
              return 0;
            }
            *(_DWORD *)a5 |= 4u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = *v34;
            v21 = "TP: Max Remote Bidirectional Stream Data (%llu bytes)";
            goto LABEL_19;
          case 7uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 4) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v35,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_MAX_STREAM_DATA_UNI");
              return 0;
            }
            *(_DWORD *)a5 |= 8u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = *v36;
            v21 = "TP: Max Unidirectional Stream Data (%llu)";
            goto LABEL_19;
          case 8uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 6) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v37,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_MAX_STREAMS_BIDI");
              return 0;
            }
            v13 = *v38;
            if ( *v38 > 0xFFFFFFFFFFFFFFFLL )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Invalid value of QUIC_TP_ID_INITIAL_MAX_STREAMS_BIDI";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x10u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Bidirectional Streams (%llu)", v13);
            break;
          case 9uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 7) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v39,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_MAX_STREAMS_UNI");
              return 0;
            }
            v13 = *v40;
            if ( *v40 > 0xFFFFFFFFFFFFFFFLL )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Invalid value of QUIC_TP_ID_INITIAL_MAX_STREAMS_UNI";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x20u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Unidirectional Streams (%llu)", v13);
            break;
          case 0xAuLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 9) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v41,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ACK_DELAY_EXPONENT");
              return 0;
            }
            v13 = *v42;
            if ( *v42 > 0x14 )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Invalid value of QUIC_TP_ACK_DELAY_EXPONENT";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x80u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: ACK Delay Exponent (%llu)", v13);
            break;
          case 0xBuLL:
            v11 = (unsigned __int64 *)(a5 + 80);
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 10) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v43,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_MAX_ACK_DELAY");
              return 0;
            }
            v13 = *v11;
            if ( *v11 > 0x3FFF )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Invalid value of QUIC_TP_MAX_ACK_DELAY";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x1000u;
            if ( (byte_14005C48C & 1) != 0 )
            {
              _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max ACK Delay (%llu ms)", v13);
              McTemplateU0ps_EtwWriteTransfer(v44, QuicConnLogVerbose, a1, DstBuf);
            }
            goto LABEL_23;
          case 0xCuLL:
            if ( (_WORD)v68 )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  0,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  (unsigned __int16)v68,
                  (__int64)"Invalid length of QUIC_TP_ID_DISABLE_ACTIVE_MIGRATION");
              return 0;
            }
            *(_DWORD *)a5 |= 0x400u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_131;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Disable Active Migration");
            break;
          case 0xDuLL:
            if ( !BYTE4(v67) )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Client incorrectly provided preferred address";
              goto LABEL_134;
            }
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_131;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Preferred Address");
            break;
          case 0xEuLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 12) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v45,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_ACTIVE_CONNECTION_ID_LIMIT");
              return 0;
            }
            v13 = *v46;
            if ( *v46 < 2 )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Invalid value of QUIC_TP_ACTIVE_CONNECTION_ID_LIMIT";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x4000u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Connection ID Limit (%llu)", v13);
            break;
          case 0xFuLL:
            if ( (unsigned __int16)v68 > 0x14u )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  0,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  (unsigned __int16)v68,
                  (__int64)"Invalid length of QUIC_TP_ID_INITIAL_SOURCE_CONNECTION_ID");
              return 0;
            }
            *(_DWORD *)a5 |= 0x10000u;
            a5[132] = v17;
            memmove(a5 + 112, (const void *)(a3 + v16), v17);
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = QuicCidBufToStr(v70, a5 + 112, (unsigned __int8)a5[132], v47);
            v21 = "TP: Initial Source Connection ID (%s)";
            goto LABEL_19;
          case 0x10uLL:
            if ( (unsigned __int16)v68 > 0x14u )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  0,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  (unsigned __int16)v68,
                  (__int64)"Invalid length of QUIC_TP_ID_RETRY_SOURCE_CONNECTION_ID");
              return 0;
            }
            if ( !BYTE4(v67) )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 0;
              v63 = "Client incorrectly provided retry source connection ID";
              goto LABEL_134;
            }
            *(_DWORD *)a5 |= 0x20000u;
            a5[237] = v17;
            memmove(a5 + 217, (const void *)(a3 + v16), v17);
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = QuicCidBufToStr(v70, a5 + 217, (unsigned __int8)a5[237], v48);
            v21 = "TP: Retry Source Connection ID (%s)";
            goto LABEL_19;
          case 0x11uLL:
            if ( (_WORD)v68 )
            {
              Pool2 = (void *)ExAllocatePool2(66, (unsigned __int16)v68, 842294097);
              *((_QWORD *)a5 + 31) = Pool2;
              if ( !Pool2 )
              {
                if ( (Microsoft_QuicEnableBits & 2) != 0 )
                  McTemplateU0sx_EtwWriteTransfer(v53, v52, "Version Negotiation Info", v17);
                goto LABEL_22;
              }
              memmove(Pool2, (const void *)(a3 + v16), v17);
            }
            else
            {
              *((_QWORD *)a5 + 31) = 0;
            }
            *(_DWORD *)a5 |= 0x80000u;
            *((_DWORD *)a5 + 60) = v17;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            LODWORD(v65) = v17;
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Version Negotiation Info (%hu bytes)", v65);
            break;
          case 0x20uLL:
            if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 13) )
            {
              if ( (byte_14005C48B & 4) != 0 )
                McTemplateU0pqs_EtwWriteTransfer(
                  v49,
                  (unsigned int)QuicConnErrorStatus,
                  a1,
                  v17,
                  (__int64)"Invalid length of QUIC_TP_ID_MAX_DATAGRAM_FRAME_SIZE");
              return 0;
            }
            *(_DWORD *)a5 |= 0x8000u;
            if ( (byte_14005C48C & 1) == 0 )
              goto LABEL_22;
            v20 = *v50;
            v21 = "TP: Max Datagram Frame Size (%llu bytes)";
LABEL_19:
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v21, v20);
            break;
          default:
            goto LABEL_107;
        }
      }
LABEL_20:
      v23 = QuicConnLogVerbose;
LABEL_21:
      McTemplateU0ps_EtwWriteTransfer(v22, v23, a1, DstBuf);
      goto LABEL_22;
    }
    if ( v14 == 10930 )
      break;
    switch ( v14 )
    {
      case 0x7158uLL:
        v68 = 0;
        if ( !QuicVarIntDecode(v17, a3 + v16, &v67, &v68) )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              v13,
              (unsigned int)QuicConnErrorStatus,
              a1,
              v17,
              (__int64)"Invalid length of QUIC_TP_ID_ENABLE_TIMESTAMP");
          return 0;
        }
        v61 = v68;
        if ( v68 > 3 )
        {
          if ( (byte_14005C48B & 4) == 0 )
            return 0;
          v63 = "Invalid value of QUIC_TP_ID_ENABLE_TIMESTAMP";
          goto LABEL_134;
        }
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Timestamp (%u)", v68);
          McTemplateU0ps_EtwWriteTransfer(v62, QuicConnLogVerbose, a1, DstBuf);
        }
        *(_DWORD *)a5 |= v61 << 24;
        goto LABEL_22;
      case 0xBAADuLL:
        if ( (_WORD)v68 )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              0,
              (unsigned int)QuicConnErrorStatus,
              a1,
              (unsigned __int16)v68,
              (__int64)"Invalid length of QUIC_TP_ID_DISABLE_1RTT_ENCRYPTION");
          return 0;
        }
        *(_DWORD *)a5 |= 0x40000u;
        if ( (byte_14005C48C & 1) == 0 )
        {
LABEL_131:
          v11 = (unsigned __int64 *)(a5 + 80);
          goto LABEL_24;
        }
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Disable 1-RTT Encryption");
        goto LABEL_20;
      case 0xFF04DE1BuLL:
        if ( !QuicVarIntDecode(v68, a3 + v16, &v67, (unsigned __int64 *)a5 + 11) )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              v59,
              (unsigned int)QuicConnErrorStatus,
              a1,
              v17,
              (__int64)"Invalid length of QUIC_TP_MIN_ACK_DELAY");
          return 0;
        }
        v13 = *v60;
        if ( *v60 > 0xFFFFFF )
        {
          if ( (byte_14005C48B & 4) == 0 )
            return 0;
          v63 = "Invalid value of QUIC_TP_MIN_ACK_DELAY";
          goto LABEL_134;
        }
        *(_DWORD *)a5 |= 0x100000u;
        if ( (byte_14005C48C & 1) == 0 )
          goto LABEL_22;
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Min ACK Delay (%llu us)", v13);
        goto LABEL_20;
      case 0x17F7586D2CB570uLL:
        if ( (_WORD)v68 )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              0,
              (unsigned int)QuicConnErrorStatus,
              a1,
              (unsigned __int16)v68,
              (__int64)"Invalid length of QUIC_TP_ID_RELIABLE_RESET_ENABLED");
          return 0;
        }
        *(_DWORD *)a5 |= 0x800000u;
        if ( (byte_14005C48C & 1) == 0 )
          goto LABEL_131;
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Reliable Reset");
        goto LABEL_20;
    }
LABEL_107:
    if ( v14 % 0x1F == 27 )
    {
      if ( (byte_14005C48B & 0x40) != 0 )
      {
        v58 = "TP: Reserved ID %llu, length %hu";
LABEL_110:
        LODWORD(v66) = (unsigned __int16)v68;
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v58, v14, v66, v67);
        v23 = QuicConnLogWarning;
        goto LABEL_21;
      }
    }
    else if ( (byte_14005C48B & 0x40) != 0 )
    {
      v58 = "TP: Unknown ID %llu, length %hu";
      goto LABEL_110;
    }
LABEL_22:
    v11 = (unsigned __int64 *)(a5 + 80);
LABEL_23:
    v13 = 0;
LABEL_24:
    v24 = v17 + v16;
    LOWORD(v6) = HIWORD(v67);
    LOWORD(v67) = v24;
    if ( v24 >= HIWORD(v67) )
      goto LABEL_214;
    v9 = v69;
  }
  if ( !(_WORD)v68 )
  {
    *(_DWORD *)a5 |= 0x400000u;
    if ( (byte_14005C48C & 1) == 0 )
      goto LABEL_131;
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Grease QUIC Bit");
    goto LABEL_20;
  }
  if ( (byte_14005C48B & 4) != 0 )
    McTemplateU0pqs_EtwWriteTransfer(
      0,
      (unsigned int)QuicConnErrorStatus,
      a1,
      (unsigned __int16)v68,
      (__int64)"Invalid length of QUIC_TP_ID_GREASE_QUIC_BIT");
  return 0;
}

```

## disassembly

```asm
0x14000db70  push    rbp
0x14000db72  push    rbx
0x14000db73  push    rsi
0x14000db74  push    rdi
0x14000db75  push    r12
0x14000db77  push    r13
0x14000db79  push    r14
0x14000db7b  push    r15
0x14000db7d  lea     rbp, [rsp-1E8h]
0x14000db85  sub     rsp, 2E8h
0x14000db8c  mov     rax, cs:__security_cookie
0x14000db93  xor     rax, rsp
0x14000db96  mov     [rbp+220h+var_50], rax
0x14000db9d  mov     r14, [rbp+220h+arg_20]
0x14000dba4  xor     eax, eax
0x14000dba6  mov     rbx, rcx
0x14000dba9  movzx   edi, r9w
0x14000dbad  movzx   r13d, dl
0x14000dbb1  mov     r12, r8
0x14000dbb4  mov     [rsp+320h+var_2EA], di
0x14000dbb9  mov     r15d, eax
0x14000dbbc  mov     rcx, [r14+0F8h]; P
0x14000dbc3  mov     [rsp+320h+var_2EC], r13b
0x14000dbc8  mov     [rsp+320h+var_2E0], rax
0x14000dbcd  mov     [rsp+320h+var_2F0], ax
0x14000dbd2  test    rcx, rcx
0x14000dbd5  jz      short loc_14000DBE8
0x14000dbd7  mov     edx, 32346351h; Tag
0x14000dbdc  call    cs:__imp_ExFreePoolWithTag
0x14000dbe3  nop     dword ptr [rax+rax+00h]
0x14000dbe8  xor     edx, edx; Val
0x14000dbea  mov     r8d, 100h; Size
0x14000dbf0  mov     rcx, r14; void *
0x14000dbf3  call    memset
0x14000dbf8  lea     rsi, [r14+50h]
0x14000dbfc  mov     qword ptr [r14+40h], 0FFF7h
0x14000dc04  mov     qword ptr [rsi], 19h
0x14000dc0b  mov     qword ptr [r14+48h], 3
0x14000dc13  mov     qword ptr [r14+60h], 2
0x14000dc1b  test    cs:byte_14005C48C, 1
0x14000dc22  jz      short loc_14000DC69
0x14000dc24  mov     dword ptr [rsp+320h+var_2F8], edi
0x14000dc28  lea     r9, aDecodingTransp; "Decoding Transport Parameters (Server ="...
0x14000dc2f  mov     edx, 80h; SizeInBytes
0x14000dc34  mov     dword ptr [rsp+320h+var_300], r13d
0x14000dc39  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000dc40  lea     rcx, [rbp+220h+DstBuf]; DstBuf
0x14000dc47  call    cs:__imp__snprintf_s
0x14000dc4e  nop     dword ptr [rax+rax+00h]
0x14000dc53  lea     r9, [rbp+220h+DstBuf]
0x14000dc5a  mov     r8, rbx
0x14000dc5d  lea     rdx, QuicConnLogVerbose
0x14000dc64  call    McTemplateU0ps_EtwWriteTransfer
0x14000dc69  xor     ecx, ecx
0x14000dc6b  cmp     cx, di
0x14000dc6e  jnb     loc_14000ECCD
0x14000dc74  nop     dword ptr [rax+00h]
0x14000dc78  nop     dword ptr [rax+rax+00000000h]
0x14000dc80  mov     [rsp+320h+var_2E8], rcx
0x14000dc85  lea     r9, [rsp+320h+var_2E8]
0x14000dc8a  movzx   ecx, di
0x14000dc8d  lea     r8, [rsp+320h+var_2F0]
0x14000dc92  mov     rdx, r12
0x14000dc95  call    QuicVarIntDecode
0x14000dc9a  test    al, al
0x14000dc9c  jz      loc_14000ECB4
0x14000dca2  mov     rsi, [rsp+320h+var_2E8]
0x14000dca7  cmp     rsi, 40h ; '@'
0x14000dcab  jnb     short loc_14000DCC0
0x14000dcad  bt      r15, rsi
0x14000dcb1  jb      loc_14000E6A3
0x14000dcb7  bts     r15, rsi
0x14000dcbb  mov     [rsp+320h+var_2E0], r15
0x14000dcc0  xor     eax, eax
0x14000dcc2  lea     r9, [rsp+320h+var_2E8]
0x14000dcc7  lea     r8, [rsp+320h+var_2F0]
0x14000dccc  mov     [rsp+320h+var_2E8], rax
0x14000dcd1  mov     rdx, r12
0x14000dcd4  movzx   ecx, di
0x14000dcd7  call    QuicVarIntDecode
0x14000dcdc  test    al, al
0x14000dcde  jz      loc_14000EC9B
0x14000dce4  movzx   r13d, [rsp+320h+var_2F0]
0x14000dcea  mov     rdi, [rsp+320h+var_2E8]
0x14000dcef  mov     r15d, r13d
0x14000dcf2  movzx   eax, [rsp+320h+var_2EA]
0x14000dcf7  lea     rcx, [rdi+r13]
0x14000dcfb  cmp     rcx, rax
0x14000dcfe  ja      loc_14000EC82
0x14000dd04  xor     ecx, ecx
0x14000dd06  mov     [rsp+320h+var_2F0], cx
0x14000dd0b  cmp     rsi, 1000h
0x14000dd12  ja      loc_14000E474
0x14000dd18  jz      loc_14000E3AD
0x14000dd1e  cmp     rsi, 20h; switch 33 cases
0x14000dd22  ja      def_14000DD39; jumptable 000000014000DD39 default case, cases 18-31
0x14000dd28  lea     rdx, cs:140000000h
0x14000dd2f  mov     eax, ds:(jpt_14000DD39 - 140000000h)[rdx+rsi*4]
0x14000dd36  add     rax, rdx
0x14000dd39  jmp     rax; switch jump
0x14000dd3f  cmp     di, 14h; jumptable 000000014000DD39 case 0
0x14000dd43  ja      loc_14000E6FA
0x14000dd49  cmp     [rsp+320h+var_2EC], cl
0x14000dd4d  jz      loc_14000E6E8
0x14000dd53  or      dword ptr [r14], 2000h
0x14000dd5a  lea     rdx, [r12+r13]; Src
0x14000dd5e  movzx   r8d, di; Size
0x14000dd62  lea     rcx, [r14+0C4h]; void *
0x14000dd69  mov     [r14+0D8h], dil
0x14000dd70  call    memmove
0x14000dd75  test    cs:byte_14005C48C, 1
0x14000dd7c  jz      short loc_14000DDD8
0x14000dd7e  movzx   r8d, byte ptr [r14+0D8h]
0x14000dd86  lea     rdx, [r14+0C4h]
0x14000dd8d  lea     rcx, [rsp+320h+var_2D8]
0x14000dd92  call    QuicCidBufToStr
0x14000dd97  lea     r9, aTpOriginalConn; "TP: Original Connection Destination ID "...
0x14000dd9e  mov     [rsp+320h+var_300], rax
0x14000dda3  mov     edx, 80h; SizeInBytes
0x14000dda8  lea     rcx, [rbp+220h+DstBuf]; DstBuf
0x14000ddaf  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000ddb6  call    cs:__imp__snprintf_s
0x14000ddbd  nop     dword ptr [rax+rax+00h]
0x14000ddc2  lea     rdx, QuicConnLogVerbose
0x14000ddc9  mov     r8, rbx
0x14000ddcc  lea     r9, [rbp+220h+DstBuf]
0x14000ddd3  call    McTemplateU0ps_EtwWriteTransfer
0x14000ddd8  lea     rsi, [r14+50h]
0x14000dddc  xor     ecx, ecx
0x14000ddde  add     r13w, di
0x14000dde2  movzx   edi, [rsp+320h+var_2EA]
0x14000dde7  mov     [rsp+320h+var_2F0], r13w
0x14000dded  cmp     r13w, di
0x14000ddf1  jnb     loc_14000ECCD
0x14000ddf7  mov     r15, [rsp+320h+var_2E0]
0x14000ddfc  jmp     loc_14000DC80
0x14000de01  lea     r9, [r14+8]; jumptable 000000014000DD39 case 1
0x14000de05  movzx   ecx, di
0x14000de08  lea     rdx, [r12+r13]
0x14000de0c  lea     r8, [rsp+320h+var_2F0]
0x14000de11  call    QuicVarIntDecode
0x14000de16  test    al, al
0x14000de18  jz      loc_14000E724
0x14000de1e  or      dword ptr [r14], 800h
0x14000de25  test    cs:byte_14005C48C, 1
0x14000de2c  jz      short loc_14000DDD8
0x14000de2e  mov     rax, [r9]
0x14000de31  lea     r9, aTpIdleTimeoutL; "TP: Idle Timeout (%llu ms)"
0x14000de38  jmp     loc_14000DD9E
0x14000de3d  cmp     di, 10h; jumptable 000000014000DD39 case 2
0x14000de41  jnz     loc_14000E76A
0x14000de47  cmp     [rsp+320h+var_2EC], cl
0x14000de4b  jz      loc_14000E751
0x14000de51  or      dword ptr [r14], 100h
0x14000de58  lea     rdx, [r14+98h]
0x14000de5f  movups  xmm0, xmmword ptr [r13+r12+0]
0x14000de65  movups  xmmword ptr [rdx], xmm0
0x14000de68  test    cs:byte_14005C48C, 1
0x14000de6f  jz      loc_14000E69A
0x14000de75  movzx   r8d, dil
0x14000de79  lea     rcx, [rsp+320h+var_2D8]
0x14000de7e  call    QuicCidBufToStr
0x14000de83  lea     r9, aTpStatelessRes; "TP: Stateless Reset Token (%s)"
0x14000de8a  jmp     loc_14000DD9E
0x14000de8f  lea     rdx, [r12+r13]; jumptable 000000014000DD39 case 3
0x14000de93  movzx   ecx, di
0x14000de96  lea     r9, [r14+40h]
0x14000de9a  lea     r8, [rsp+320h+var_2F0]
0x14000de9f  call    QuicVarIntDecode
0x14000dea4  test    al, al
0x14000dea6  jz      loc_14000E7CD
0x14000deac  mov     rcx, [r9]
0x14000deaf  cmp     rcx, 4B0h
0x14000deb6  jb      loc_14000E7B4
0x14000debc  cmp     rcx, 0FFF7h
0x14000dec3  ja      loc_14000E79B
0x14000dec9  or      dword ptr [r14], 40h
0x14000decd  test    cs:byte_14005C48C, 1
0x14000ded4  jz      loc_14000DDD8
0x14000deda  mov     [rsp+320h+var_300], rcx
0x14000dedf  lea     r9, aTpMaxUdpPayloa; "TP: Max Udp Payload Size (%llu bytes)"
0x14000dee6  jmp     loc_14000DDA3
0x14000deeb  lea     r9, [r14+28h]; jumptable 000000014000DD39 case 4
0x14000deef  movzx   ecx, di
0x14000def2  lea     rdx, [r12+r13]
0x14000def6  lea     r8, [rsp+320h+var_2F0]
0x14000defb  call    QuicVarIntDecode
0x14000df00  test    al, al
0x14000df02  jz      loc_14000E7FE
0x14000df08  or      dword ptr [r14], 1
0x14000df0c  test    cs:byte_14005C48C, 1
0x14000df13  jz      loc_14000DDD8
0x14000df19  mov     rax, [r9]
0x14000df1c  lea     r9, aTpMaxDataLluBy; "TP: Max Data (%llu bytes)"
0x14000df23  jmp     loc_14000DD9E
0x14000df28  lea     r9, [r14+10h]; jumptable 000000014000DD39 case 5
0x14000df2c  movzx   ecx, di
0x14000df2f  lea     rdx, [r12+r13]
0x14000df33  lea     r8, [rsp+320h+var_2F0]
0x14000df38  call    QuicVarIntDecode
0x14000df3d  test    al, al
0x14000df3f  jz      loc_14000E82F
0x14000df45  or      dword ptr [r14], 2
0x14000df49  test    cs:byte_14005C48C, 1
0x14000df50  jz      loc_14000DDD8
0x14000df56  mov     rax, [r9]
0x14000df59  lea     r9, aTpMaxLocalBidi; "TP: Max Local Bidirectional Stream Data"...
0x14000df60  jmp     loc_14000DD9E
0x14000df65  lea     r9, [r14+18h]; jumptable 000000014000DD39 case 6
0x14000df69  movzx   ecx, di
0x14000df6c  lea     rdx, [r12+r13]
0x14000df70  lea     r8, [rsp+320h+var_2F0]
0x14000df75  call    QuicVarIntDecode
0x14000df7a  test    al, al
0x14000df7c  jz      loc_14000E860
0x14000df82  or      dword ptr [r14], 4
0x14000df86  test    cs:byte_14005C48C, 1
0x14000df8d  jz      loc_14000DDD8
0x14000df93  mov     rax, [r9]
0x14000df96  lea     r9, aTpMaxRemoteBid; "TP: Max Remote Bidirectional Stream Dat"...
0x14000df9d  jmp     loc_14000DD9E
0x14000dfa2  lea     r9, [r14+20h]; jumptable 000000014000DD39 case 7
0x14000dfa6  movzx   ecx, di
0x14000dfa9  lea     rdx, [r12+r13]
0x14000dfad  lea     r8, [rsp+320h+var_2F0]
0x14000dfb2  call    QuicVarIntDecode
0x14000dfb7  test    al, al
0x14000dfb9  jz      loc_14000E891
0x14000dfbf  or      dword ptr [r14], 8
0x14000dfc3  test    cs:byte_14005C48C, 1
0x14000dfca  jz      loc_14000DDD8
0x14000dfd0  mov     rax, [r9]
0x14000dfd3  lea     r9, aTpMaxUnidirect; "TP: Max Unidirectional Stream Data (%ll"...
0x14000dfda  jmp     loc_14000DD9E
0x14000dfdf  lea     r9, [r14+30h]; jumptable 000000014000DD39 case 8
0x14000dfe3  movzx   ecx, di
0x14000dfe6  lea     rdx, [r12+r13]
0x14000dfea  lea     r8, [rsp+320h+var_2F0]
0x14000dfef  call    QuicVarIntDecode
0x14000dff4  test    al, al
0x14000dff6  jz      loc_14000E8DB
0x14000dffc  mov     rcx, [r9]
0x14000dfff  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000e009  cmp     rcx, rax
0x14000e00c  ja      loc_14000E8C2
0x14000e012  or      dword ptr [r14], 10h
0x14000e016  test    cs:byte_14005C48C, 1
0x14000e01d  jz      loc_14000DDD8
0x14000e023  mov     [rsp+320h+var_300], rcx
0x14000e028  lea     r9, aTpMaxBidirecti; "TP: Max Bidirectional Streams (%llu)"
0x14000e02f  jmp     loc_14000DDA3
0x14000e034  lea     r9, [r14+38h]; jumptable 000000014000DD39 case 9
0x14000e038  movzx   ecx, di
0x14000e03b  lea     rdx, [r12+r13]
0x14000e03f  lea     r8, [rsp+320h+var_2F0]
0x14000e044  call    QuicVarIntDecode
0x14000e049  test    al, al
0x14000e04b  jz      loc_14000E925
0x14000e051  mov     rcx, [r9]
0x14000e054  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000e05e  cmp     rcx, rax
0x14000e061  ja      loc_14000E90C
0x14000e067  or      dword ptr [r14], 20h
0x14000e06b  test    cs:byte_14005C48C, 1
0x14000e072  jz      loc_14000DDD8
0x14000e078  mov     [rsp+320h+var_300], rcx
0x14000e07d  lea     r9, aTpMaxUnidirect_0; "TP: Max Unidirectional Streams (%llu)"
0x14000e084  jmp     loc_14000DDA3
0x14000e089  lea     rdx, [r12+r13]; jumptable 000000014000DD39 case 10
0x14000e08d  movzx   ecx, di
0x14000e090  lea     r9, [r14+48h]
0x14000e094  lea     r8, [rsp+320h+var_2F0]
0x14000e099  call    QuicVarIntDecode
0x14000e09e  test    al, al
0x14000e0a0  jz      loc_14000E96F
0x14000e0a6  mov     rcx, [r9]
0x14000e0a9  cmp     rcx, 14h
0x14000e0ad  ja      loc_14000E956
0x14000e0b3  or      dword ptr [r14], 80h
0x14000e0ba  test    cs:byte_14005C48C, 1
0x14000e0c1  jz      loc_14000DDD8
0x14000e0c7  mov     [rsp+320h+var_300], rcx
0x14000e0cc  lea     r9, aTpAckDelayExpo; "TP: ACK Delay Exponent (%llu)"
0x14000e0d3  jmp     loc_14000DDA3
0x14000e0d8  lea     rsi, [r14+50h]; jumptable 000000014000DD39 case 11
0x14000e0dc  movzx   ecx, di
0x14000e0df  mov     r9, rsi
0x14000e0e2  lea     rdx, [r12+r13]
0x14000e0e6  lea     r8, [rsp+320h+var_2F0]
0x14000e0eb  call    QuicVarIntDecode
0x14000e0f0  test    al, al
0x14000e0f2  jz      loc_14000E9B9
0x14000e0f8  mov     rcx, [rsi]
0x14000e0fb  cmp     rcx, 3FFFh
0x14000e102  ja      loc_14000E9A0
0x14000e108  or      dword ptr [r14], 1000h
0x14000e10f  test    cs:byte_14005C48C, 1
0x14000e116  jz      loc_14000DDDC
0x14000e11c  mov     [rsp+320h+var_300], rcx
0x14000e121  lea     r9, aTpMaxAckDelayL; "TP: Max ACK Delay (%llu ms)"
  ... truncated ...
```
