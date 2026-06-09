# QuicSettingsLoad

- ea: `0x140024810`
- end: `0x1400255d6`
- name: `QuicSettingsLoad`
- size: `3526`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024240`
- `0x140025d70`

## callees

- `0x140022dcc`
- `0x140024810`
- `0x140033e30`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003ed00`
- `0x140042650`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140025119`
- `ntoskrnl!_snprintf_s` at `0x140025119`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400250de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002513d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400250de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002513d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025196`
- `ntoskrnl!ExAllocatePool2` at `0x140024eb1`
- `ntoskrnl!ExAllocatePool2` at `0x140024eb1`

## string_xrefs

- `0x14002521c`: `MtuDiscoverySearchCompleteTimeoutUs`
- `0x1400252eb`: `DestCidUpdateIdleTimeoutMs`

## pseudocode

```c
char __fastcall QuicSettingsLoad(int *a1, __int64 a2)
{
  int v2; // eax
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned int v7; // ecx
  unsigned int v8; // r14d
  __int64 v9; // r12
  unsigned int v10; // r15d
  unsigned __int64 v11; // r13
  __int64 Pool2; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rsi
  unsigned __int8 v16; // cf
  unsigned __int16 v17; // si
  unsigned __int16 v18; // r14
  char result; // al
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r8
  unsigned int v26; // edx
  __int64 v27; // r8
  int v28; // edx
  int v29; // r9d
  unsigned int v30; // edx
  __int64 v31; // r8
  int v32; // edx
  int v33; // r9d
  unsigned int v34; // edx
  __int64 v35; // r8
  int v36; // edx
  int v37; // r9d
  void *v38; // rcx
  __int64 v39; // rcx
  void *v40; // rcx
  unsigned int v41; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v42; // [rsp+34h] [rbp-75h] BYREF
  unsigned __int64 v43; // [rsp+38h] [rbp-71h] BYREF
  char DstBuf[128]; // [rsp+40h] [rbp-69h] BYREF

  v2 = *a1;
  v42 = 0;
  v43 = 0;
  if ( (v2 & 0x2000000) == 0 )
  {
    v42 = 1;
    v41 = 4;
    CxPlatStorageReadValue(a2, "SendBufferingDefault", &v42, &v41);
    *((_BYTE *)a1 + 139) = (v42 != 0) | *((_BYTE *)a1 + 139) & 0xFE;
  }
  if ( (*a1 & 0x4000000) == 0 )
  {
    v42 = 1;
    v41 = 4;
    CxPlatStorageReadValue(a2, "SendPacingDefault", &v42, &v41);
    *((_BYTE *)a1 + 139) = (v42 != 0 ? 2 : 0) | *((_BYTE *)a1 + 139) & 0xFD;
  }
  if ( (*a1 & 0x8000000) == 0 )
  {
    v42 = 1;
    v41 = 4;
    CxPlatStorageReadValue(a2, "MigrationEnabled", &v42, &v41);
    *((_BYTE *)a1 + 139) = (v42 != 0 ? 4 : 0) | *((_BYTE *)a1 + 139) & 0xFB;
  }
  if ( (*a1 & 0x10000000) == 0 )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "DatagramReceiveEnabled", &v42, &v41);
    *((_BYTE *)a1 + 139) = (v42 != 0 ? 8 : 0) | *((_BYTE *)a1 + 139) & 0xF7;
  }
  if ( (*a1 & 0x1000000) == 0 )
  {
    v42 = 16;
    v41 = 4;
    CxPlatStorageReadValue(a2, "MaxOperationsPerDrain", &v42, &v41);
    if ( v42 - 1 <= 0xFE )
      *((_BYTE *)a1 + 138) = v42;
  }
  if ( (*a1 & 0x200000LL) == 0 )
  {
    v42 = 65;
    v41 = 4;
    CxPlatStorageReadValue(a2, "RetryMemoryFraction", &v42, &v41);
    if ( v42 <= 0xFFFF )
      *((_WORD *)a1 + 62) = v42;
  }
  if ( (*a1 & 0x400000LL) == 0 && !byte_14005C491 )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "LoadBalancingMode", &v42, &v41);
    if ( v42 < 3 )
      *((_WORD *)a1 + 63) = v42;
  }
  if ( (*a1 & 0x800000LL) == 0 && !byte_14005C491 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "FixedServerID", a1 + 29, &v41);
  }
  if ( (*a1 & 0x800LL) == 0 )
  {
    v42 = 250;
    v41 = 4;
    CxPlatStorageReadValue(a2, "MaxWorkerQueueDelayMs", &v42, &v41);
    a1[20] = 1000 * v42;
  }
  if ( (*a1 & 0x1000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "MaxStatelessOperations", a1 + 21, &v41);
  }
  if ( (*a1 & 0x2000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "InitialWindowPackets", a1 + 22, &v41);
  }
  if ( (*a1 & 0x4000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "SendIdleTimeoutMs", a1 + 23, &v41);
  }
  if ( (*a1 & 0x8000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "InitialRttMs", a1 + 24, &v41);
  }
  if ( (*a1 & 0x10000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "MaxAckDelayMs", a1 + 25, &v41);
    if ( (unsigned int)a1[25] > 0x3FFF )
      a1[25] = 25;
  }
  if ( (*a1 & 0x20000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "DisconnectTimeoutMs", a1 + 26, &v41);
    if ( (unsigned int)a1[26] > 0x927C0 )
      a1[26] = 600000;
  }
  if ( (*a1 & 0x40000LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "KeepAliveIntervalMs", a1 + 27, &v41);
  }
  if ( (*(_BYTE *)a1 & 4) == 0 )
  {
    v41 = 8;
    if ( (int)CxPlatStorageReadValue(a2, "IdleTimeoutMs", &v43, &v41) >= 0 )
    {
      v5 = (unsigned int)v43;
      if ( v41 != 4 )
        v5 = v43;
      *((_QWORD *)a1 + 4) = v5;
      if ( v5 > 0x3FFFFFFFFFFFFFFFLL )
        *((_QWORD *)a1 + 4) = 30000;
    }
  }
  if ( (*(_BYTE *)a1 & 2) == 0 )
  {
    v41 = 8;
    if ( (int)CxPlatStorageReadValue(a2, "HandshakeIdleTimeoutMs", &v43, &v41) >= 0 )
    {
      v6 = (unsigned int)v43;
      if ( v41 != 4 )
        v6 = v43;
      *((_QWORD *)a1 + 3) = v6;
      if ( v6 > 0x3FFFFFFFFFFFFFFFLL )
        *((_QWORD *)a1 + 3) = 30000;
    }
  }
  if ( (*(_BYTE *)a1 & 8) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "TlsClientMaxSendBuffer", a1 + 12, &v41);
  }
  if ( (*(_BYTE *)a1 & 0x10) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "TlsServerMaxSendBuffer", a1 + 13, &v41);
  }
  if ( (*(_BYTE *)a1 & 0x20) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "StreamRecvWindowDefault", a1 + 14, &v41);
  }
  if ( (*(_BYTE *)a1 & 0x40) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "StreamRecvWindowBidiLocalDefault", a1 + 15, &v41);
  }
  if ( *(char *)a1 >= 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "StreamRecvWindowBidiRemoteDefault", a1 + 16, &v41);
  }
  if ( (*a1 & 0x100LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "StreamRecvWindowUnidiDefault", a1 + 17, &v41);
  }
  if ( (*a1 & 0x200LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "StreamRecvBufferDefault", a1 + 18, &v41);
    v7 = a1[18];
    if ( !v7 || ((v7 - 1) & v7) != 0 || v7 < 0x1000 )
      a1[18] = 4096;
  }
  if ( (*a1 & 0x400LL) == 0 )
  {
    v41 = 4;
    CxPlatStorageReadValue(a2, "ConnFlowControlWindow", a1 + 19, &v41);
  }
  if ( (*(_BYTE *)a1 & 1) == 0 )
  {
    v41 = 8;
    CxPlatStorageReadValue(a2, "MaxBytesPerKey", a1 + 4, &v41);
    if ( *((_QWORD *)a1 + 2) > 0x4000000000uLL )
      *((_QWORD *)a1 + 2) = 0x4000000000LL;
  }
  if ( (*a1 & 0x20000000) == 0 )
  {
    v41 = 4;
    if ( (int)CxPlatStorageReadValue(a2, "ResumptionLevel", &v42, &v41) >= 0 && v42 <= 2 )
      *((_BYTE *)a1 + 139) = *((_BYTE *)a1 + 139) & 0xCF | (16 * (v42 & 3));
  }
  if ( (*a1 & 0x80000000) == 0 )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "VersionNegotiationExtEnabled", &v42, &v41);
    *((_BYTE *)a1 + 139) = (v42 != 0 ? 0x40 : 0) | *((_BYTE *)a1 + 139) & 0xBF;
  }
  if ( (*a1 & 0x40000000) == 0 )
  {
    v42 = 0;
    v41 = 0;
    LODWORD(v43) = 0;
    if ( (int)CxPlatStorageReadValue(a2, "AcceptableVersions", 0, &v41) >= 0
      && (int)CxPlatStorageReadValue(a2, "OfferedVersions", 0, &v42) >= 0
      && (int)CxPlatStorageReadValue(a2, "FullyDeployedVersions", 0, &v43) >= 0
      && (v8 = v41) != 0
      && (v9 = v42) != 0
      && (v10 = v43) != 0 )
    {
      v11 = v41 + (unsigned __int64)(unsigned int)v43;
      Pool2 = ExAllocatePool2(66, v11 + v42 + 40LL, 808739665);
      v15 = Pool2;
      if ( !Pool2 )
      {
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(v14, v13, "VersionSettings", v11 + v9 + 40);
        goto LABEL_90;
      }
      v41 = v8;
      *(_QWORD *)Pool2 = Pool2 + 40;
      *(_DWORD *)(Pool2 + 24) = v8 >> 2;
      if ( (int)CxPlatStorageReadValue(a2, "AcceptableVersions", Pool2 + 40, &v41) < 0 )
        goto LABEL_120;
      v20 = *(unsigned int *)(v15 + 24);
      v21 = *(_QWORD *)v15;
      v41 = v9;
      v22 = v21 + 4 * v20;
      *(_DWORD *)(v15 + 28) = (unsigned int)v9 >> 2;
      *(_QWORD *)(v15 + 8) = v22;
      if ( (int)CxPlatStorageReadValue(a2, "OfferedVersions", v22, &v41) < 0
        || (v23 = *(unsigned int *)(v15 + 28),
            v24 = *(_QWORD *)(v15 + 8),
            v41 = v10,
            v25 = v24 + 4 * v23,
            *(_DWORD *)(v15 + 32) = v10 >> 2,
            *(_QWORD *)(v15 + 16) = v25,
            (int)CxPlatStorageReadValue(a2, "FullyDeployedVersions", v25, &v41) < 0) )
      {
LABEL_120:
        ExFreePoolWithTag((PVOID)v15, 0x30346351u);
        goto LABEL_90;
      }
      v26 = 0;
      if ( *(_DWORD *)(v15 + 24) )
      {
        v27 = *(_QWORD *)v15;
        while ( 1 )
        {
          *(_DWORD *)(v27 + 4LL * v26) = _byteswap_ulong(*(_DWORD *)(v27 + 4LL * v26));
          if ( !(unsigned __int8)QuicIsVersionSupported(*(unsigned int *)(*(_QWORD *)v15 + 4LL * v26))
            && !(unsigned __int8)QuicIsVersionReserved() )
          {
            break;
          }
          v26 = v28 + 1;
          if ( v26 >= *(_DWORD *)(v15 + 24) )
            goto LABEL_104;
        }
        if ( (byte_14005C48E & 0x10) == 0 )
          goto LABEL_120;
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Invalid AcceptableVersion loaded from storage! 0x%x at position %d",
          v29,
          v28);
LABEL_119:
        McTemplateU0s_EtwWriteTransfer(v39, QuicLogError, DstBuf);
        goto LABEL_120;
      }
LABEL_104:
      v30 = 0;
      if ( *(_DWORD *)(v15 + 28) )
      {
        v31 = *(_QWORD *)(v15 + 8);
        while ( 1 )
        {
          *(_DWORD *)(v31 + 4LL * v30) = _byteswap_ulong(*(_DWORD *)(v31 + 4LL * v30));
          if ( !(unsigned __int8)QuicIsVersionSupported(*(unsigned int *)(*(_QWORD *)(v15 + 8) + 4LL * v30))
            && !(unsigned __int8)QuicIsVersionReserved() )
          {
            break;
          }
          v30 = v32 + 1;
          if ( v30 >= *(_DWORD *)(v15 + 28) )
            goto LABEL_109;
        }
        if ( (byte_14005C48E & 0x10) == 0 )
          goto LABEL_120;
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Invalid OfferedVersion loaded from storage! 0x%x at position %d",
          v33,
          v32);
        goto LABEL_119;
      }
LABEL_109:
      v34 = 0;
      if ( *(_DWORD *)(v15 + 32) )
      {
        v35 = *(_QWORD *)(v15 + 16);
        while ( 1 )
        {
          *(_DWORD *)(v35 + 4LL * v34) = _byteswap_ulong(*(_DWORD *)(v35 + 4LL * v34));
          if ( !(unsigned __int8)QuicIsVersionSupported(*(unsigned int *)(*(_QWORD *)(v15 + 16) + 4LL * v34))
            && !(unsigned __int8)QuicIsVersionReserved() )
          {
            break;
          }
          v34 = v36 + 1;
          if ( v34 >= *(_DWORD *)(v15 + 32) )
            goto LABEL_114;
        }
        if ( (byte_14005C48E & 0x10) == 0 )
          goto LABEL_120;
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Invalid FullyDeployedVersion loaded from storage! 0x%x at position %d",
          v37,
          v36);
        goto LABEL_119;
      }
LABEL_114:
      v38 = (void *)*((_QWORD *)a1 + 1);
      if ( v38 )
        ExFreePoolWithTag(v38, 0x30346351u);
      *((_QWORD *)a1 + 1) = v15;
    }
    else
    {
      v40 = (void *)*((_QWORD *)a1 + 1);
      if ( v40 )
      {
        ExFreePoolWithTag(v40, 0x30346351u);
        *((_QWORD *)a1 + 1) = 0;
      }
    }
  }
LABEL_90:
  v16 = _bittest64((const signed __int64 *)a1, 0x20u);
  v17 = *((_WORD *)a1 + 64);
  v18 = *((_WORD *)a1 + 65);
  LOWORD(v43) = v17;
  LOWORD(v42) = v18;
  if ( !v16 )
  {
    v41 = 2;
    CxPlatStorageReadValue(a2, "MinimumMtu", &v43, &v41);
    v17 = v43;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x21u) )
  {
    v41 = 2;
    CxPlatStorageReadValue(a2, "MaximumMtu", &v42, &v41);
    v18 = v42;
  }
  result = -32;
  if ( v18 <= 0x5DCu )
  {
    if ( v18 < 0x4E0u )
      v18 = 1248;
  }
  else
  {
    v18 = 1500;
  }
  if ( v17 <= 0x5DCu )
  {
    if ( v17 < 0x4E0u )
      v17 = 1248;
  }
  else
  {
    v17 = 1500;
  }
  if ( v17 <= v18 )
  {
    *((_WORD *)a1 + 65) = v18;
    *((_WORD *)a1 + 64) = v17;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x23u) )
  {
    v41 = 1;
    result = CxPlatStorageReadValue(a2, "MtuDiscoveryMissingProbeCount", (char *)a1 + 142, &v41);
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x22u) )
  {
    v41 = 8;
    result = CxPlatStorageReadValue(a2, "MtuDiscoverySearchCompleteTimeoutUs", a1 + 10, &v41);
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x24u) )
  {
    v42 = 100;
    v41 = 4;
    CxPlatStorageReadValue(a2, "MaxBindingStatelessOperations", &v42, &v41);
    result = v42;
    if ( v42 < 0xFFFF )
      *((_WORD *)a1 + 66) = v42;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x25u) )
  {
    v42 = 100;
    v41 = 4;
    CxPlatStorageReadValue(a2, "StatelessOperationExpirationMs", &v42, &v41);
    result = v42;
    if ( v42 < 0xFFFF )
      *((_WORD *)a1 + 67) = v42;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x26u) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "CongestionControlAlgorithm", &v42, &v41);
    result = v42;
    if ( v42 < 2 )
      *((_WORD *)a1 + 68) = v42;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x27u) )
  {
    v42 = 20000;
    v41 = 4;
    CxPlatStorageReadValue(a2, "DestCidUpdateIdleTimeoutMs", &v42, &v41);
    result = v42;
    a1[28] = v42;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x28u) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "GreaseQuicBitEnabled", &v42, &v41);
    result = (v42 != 0 ? 0x80 : 0) | *((_BYTE *)a1 + 139) & 0x7F;
    *((_BYTE *)a1 + 139) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x29u) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "EcnEnabled", &v42, &v41);
    result = (v42 != 0) | a1[35] & 0xFE;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x2Au) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "HyStartEnabled", &v42, &v41);
    result = (v42 != 0 ? 2 : 0) | a1[35] & 0xFD;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x2Bu) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "EncryptionOffloadAllowed", &v42, &v41);
    result = (v42 != 0 ? 4 : 0) | a1[35] & 0xFB;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x2Cu) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "ReliableResetEnabled", &v42, &v41);
    result = (v42 != 0 ? 8 : 0) | a1[35] & 0xF7;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( (*((_BYTE *)a1 + 6) & 1) == 0 )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "XdpEnabled", &v42, &v41);
    result = (v42 != 0 ? 0x80 : 0) | a1[35] & 0x7F;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x31u) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "QTIPEnabled", &v42, &v41);
    result = (v42 != 0) | *((_BYTE *)a1 + 141) & 0xFE;
    *((_BYTE *)a1 + 141) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x32u) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "RioEnabled", &v42, &v41);
    result = (v42 != 0 ? 2 : 0) | *((_BYTE *)a1 + 141) & 0xFD;
    *((_BYTE *)a1 + 141) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x2Du) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "OneWayDelayEnabled", &v42, &v41);
    result = (v42 != 0 ? 0x10 : 0) | a1[35] & 0xEF;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x2Eu) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "NetStatsEventEnabled", &v42, &v41);
    result = (v42 != 0 ? 0x20 : 0) | a1[35] & 0xDF;
    *((_BYTE *)a1 + 140) = result;
  }
  if ( !_bittest64((const signed __int64 *)a1, 0x2Fu) )
  {
    v42 = 0;
    v41 = 4;
    CxPlatStorageReadValue(a2, "StreamMultiReceiveEnabled", &v42, &v41);
    result = (v42 != 0 ? 0x40 : 0) | a1[35] & 0xBF;
    *((_BYTE *)a1 + 140) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140024810  mov     [rsp-8+arg_10], rbx
0x140024815  push    rbp
0x140024816  push    rsi
0x140024817  push    rdi
0x140024818  push    r12
0x14002481a  push    r13
0x14002481c  push    r14
0x14002481e  push    r15
0x140024820  lea     rbp, [rsp-27h]
0x140024825  sub     rsp, 0D0h
0x14002482c  mov     rax, cs:__security_cookie
0x140024833  xor     rax, rsp
0x140024836  mov     [rbp+57h+var_40], rax
0x14002483a  mov     eax, [rcx]
0x14002483c  xor     r13d, r13d
0x14002483f  mov     [rbp+57h+var_CC], r13d
0x140024843  mov     rdi, rdx
0x140024846  mov     [rbp+57h+var_C8], r13
0x14002484a  mov     rbx, rcx
0x14002484d  lea     esi, [r13+1]
0x140024851  lea     r14d, [r13+4]
0x140024855  bt      rax, 19h
0x14002485a  jb      short loc_140024891
0x14002485c  lea     r9, [rbp+57h+var_D0]
0x140024860  mov     [rbp+57h+var_CC], esi
0x140024863  lea     r8, [rbp+57h+var_CC]
0x140024867  mov     [rbp+57h+var_D0], r14d
0x14002486b  lea     rdx, aSendbufferingd; "SendBufferingDefault"
0x140024872  mov     rcx, rdi
0x140024875  call    CxPlatStorageReadValue
0x14002487a  cmp     [rbp+57h+var_CC], r13d
0x14002487e  mov     al, [rbx+8Bh]
0x140024884  setnz   cl
0x140024887  and     al, 0FEh
0x140024889  or      al, cl
0x14002488b  mov     [rbx+8Bh], al
0x140024891  mov     eax, [rbx]
0x140024893  bt      rax, 1Ah
0x140024898  jb      short loc_1400248D2
0x14002489a  lea     r9, [rbp+57h+var_D0]
0x14002489e  mov     [rbp+57h+var_CC], esi
0x1400248a1  lea     r8, [rbp+57h+var_CC]
0x1400248a5  mov     [rbp+57h+var_D0], r14d
0x1400248a9  lea     rdx, aSendpacingdefa; "SendPacingDefault"
0x1400248b0  mov     rcx, rdi
0x1400248b3  call    CxPlatStorageReadValue
0x1400248b8  mov     eax, [rbp+57h+var_CC]
0x1400248bb  neg     eax
0x1400248bd  mov     al, [rbx+8Bh]
0x1400248c3  sbb     cl, cl
0x1400248c5  and     al, 0FDh
0x1400248c7  and     cl, 2
0x1400248ca  or      al, cl
0x1400248cc  mov     [rbx+8Bh], al
0x1400248d2  mov     eax, [rbx]
0x1400248d4  bt      rax, 1Bh
0x1400248d9  jb      short loc_140024913
0x1400248db  lea     r9, [rbp+57h+var_D0]
0x1400248df  mov     [rbp+57h+var_CC], esi
0x1400248e2  lea     r8, [rbp+57h+var_CC]
0x1400248e6  mov     [rbp+57h+var_D0], r14d
0x1400248ea  lea     rdx, aMigrationenabl; "MigrationEnabled"
0x1400248f1  mov     rcx, rdi
0x1400248f4  call    CxPlatStorageReadValue
0x1400248f9  mov     eax, [rbp+57h+var_CC]
0x1400248fc  neg     eax
0x1400248fe  mov     al, [rbx+8Bh]
0x140024904  sbb     cl, cl
0x140024906  and     al, 0FBh
0x140024908  and     cl, r14b
0x14002490b  or      al, cl
0x14002490d  mov     [rbx+8Bh], al
0x140024913  mov     eax, [rbx]
0x140024915  bt      rax, 1Ch
0x14002491a  jb      short loc_140024955
0x14002491c  lea     r9, [rbp+57h+var_D0]
0x140024920  mov     [rbp+57h+var_CC], r13d
0x140024924  lea     r8, [rbp+57h+var_CC]
0x140024928  mov     [rbp+57h+var_D0], r14d
0x14002492c  lea     rdx, aDatagramreceiv; "DatagramReceiveEnabled"
0x140024933  mov     rcx, rdi
0x140024936  call    CxPlatStorageReadValue
0x14002493b  mov     eax, [rbp+57h+var_CC]
0x14002493e  neg     eax
0x140024940  mov     al, [rbx+8Bh]
0x140024946  sbb     cl, cl
0x140024948  and     al, 0F7h
0x14002494a  and     cl, 8
0x14002494d  or      al, cl
0x14002494f  mov     [rbx+8Bh], al
0x140024955  mov     eax, [rbx]
0x140024957  bt      rax, 18h
0x14002495c  jb      short loc_140024993
0x14002495e  lea     r9, [rbp+57h+var_D0]
0x140024962  mov     [rbp+57h+var_CC], 10h
0x140024969  lea     r8, [rbp+57h+var_CC]
0x14002496d  mov     [rbp+57h+var_D0], r14d
0x140024971  lea     rdx, aMaxoperationsp; "MaxOperationsPerDrain"
0x140024978  mov     rcx, rdi
0x14002497b  call    CxPlatStorageReadValue
0x140024980  mov     ecx, [rbp+57h+var_CC]
0x140024983  lea     eax, [rcx-1]
0x140024986  cmp     eax, 0FEh
0x14002498b  ja      short loc_140024993
0x14002498d  mov     [rbx+8Ah], cl
0x140024993  mov     eax, [rbx]
0x140024995  bt      rax, 15h
0x14002499a  jb      short loc_1400249CC
0x14002499c  lea     r9, [rbp+57h+var_D0]
0x1400249a0  mov     [rbp+57h+var_CC], 41h ; 'A'
0x1400249a7  lea     r8, [rbp+57h+var_CC]
0x1400249ab  mov     [rbp+57h+var_D0], r14d
0x1400249af  lea     rdx, aRetrymemoryfra; "RetryMemoryFraction"
0x1400249b6  mov     rcx, rdi
0x1400249b9  call    CxPlatStorageReadValue
0x1400249be  mov     eax, [rbp+57h+var_CC]
0x1400249c1  cmp     eax, 0FFFFh
0x1400249c6  ja      short loc_1400249CC
0x1400249c8  mov     [rbx+7Ch], ax
0x1400249cc  mov     eax, [rbx]
0x1400249ce  bt      rax, 16h
0x1400249d3  jb      short loc_140024A09
0x1400249d5  cmp     cs:byte_14005C491, r13b
0x1400249dc  jnz     short loc_140024A09
0x1400249de  lea     r9, [rbp+57h+var_D0]
0x1400249e2  mov     [rbp+57h+var_CC], r13d
0x1400249e6  lea     r8, [rbp+57h+var_CC]
0x1400249ea  mov     [rbp+57h+var_D0], r14d
0x1400249ee  lea     rdx, aLoadbalancingm; "LoadBalancingMode"
0x1400249f5  mov     rcx, rdi
0x1400249f8  call    CxPlatStorageReadValue
0x1400249fd  mov     eax, [rbp+57h+var_CC]
0x140024a00  cmp     eax, 3
0x140024a03  jnb     short loc_140024A09
0x140024a05  mov     [rbx+7Eh], ax
0x140024a09  mov     eax, [rbx]
0x140024a0b  bt      rax, 17h
0x140024a10  jb      short loc_140024A36
0x140024a12  cmp     cs:byte_14005C491, r13b
0x140024a19  jnz     short loc_140024A36
0x140024a1b  lea     r8, [rbx+74h]
0x140024a1f  mov     [rbp+57h+var_D0], r14d
0x140024a23  lea     r9, [rbp+57h+var_D0]
0x140024a27  mov     rcx, rdi
0x140024a2a  lea     rdx, aFixedserverid; "FixedServerID"
0x140024a31  call    CxPlatStorageReadValue
0x140024a36  mov     eax, [rbx]
0x140024a38  bt      rax, 0Bh
0x140024a3d  jb      short loc_140024A6B
0x140024a3f  lea     r9, [rbp+57h+var_D0]
0x140024a43  mov     [rbp+57h+var_CC], 0FAh
0x140024a4a  lea     r8, [rbp+57h+var_CC]
0x140024a4e  mov     [rbp+57h+var_D0], r14d
0x140024a52  lea     rdx, aMaxworkerqueue; "MaxWorkerQueueDelayMs"
0x140024a59  mov     rcx, rdi
0x140024a5c  call    CxPlatStorageReadValue
0x140024a61  imul    eax, [rbp+57h+var_CC], 3E8h
0x140024a68  mov     [rbx+50h], eax
0x140024a6b  mov     eax, [rbx]
0x140024a6d  mov     r12d, 1000h
0x140024a73  test    r12, rax
0x140024a76  jnz     short loc_140024A93
0x140024a78  lea     r8, [rbx+54h]
0x140024a7c  mov     [rbp+57h+var_D0], r14d
0x140024a80  lea     r9, [rbp+57h+var_D0]
0x140024a84  mov     rcx, rdi
0x140024a87  lea     rdx, aMaxstatelessop; "MaxStatelessOperations"
0x140024a8e  call    CxPlatStorageReadValue
0x140024a93  mov     eax, [rbx]
0x140024a95  bt      rax, 0Dh
0x140024a9a  jb      short loc_140024AB7
0x140024a9c  lea     r8, [rbx+58h]
0x140024aa0  mov     [rbp+57h+var_D0], r14d
0x140024aa4  lea     r9, [rbp+57h+var_D0]
0x140024aa8  mov     rcx, rdi
0x140024aab  lea     rdx, aInitialwindowp; "InitialWindowPackets"
0x140024ab2  call    CxPlatStorageReadValue
0x140024ab7  mov     eax, [rbx]
0x140024ab9  bt      rax, 0Eh
0x140024abe  jb      short loc_140024ADB
0x140024ac0  lea     r8, [rbx+5Ch]
0x140024ac4  mov     [rbp+57h+var_D0], r14d
0x140024ac8  lea     r9, [rbp+57h+var_D0]
0x140024acc  mov     rcx, rdi
0x140024acf  lea     rdx, aSendidletimeou; "SendIdleTimeoutMs"
0x140024ad6  call    CxPlatStorageReadValue
0x140024adb  mov     eax, [rbx]
0x140024add  bt      rax, 0Fh
0x140024ae2  jb      short loc_140024AFF
0x140024ae4  lea     r8, [rbx+60h]
0x140024ae8  mov     [rbp+57h+var_D0], r14d
0x140024aec  lea     r9, [rbp+57h+var_D0]
0x140024af0  mov     rcx, rdi
0x140024af3  lea     rdx, aInitialrttms; "InitialRttMs"
0x140024afa  call    CxPlatStorageReadValue
0x140024aff  mov     eax, [rbx]
0x140024b01  bt      rax, 10h
0x140024b06  jb      short loc_140024B34
0x140024b08  lea     rsi, [rbx+64h]
0x140024b0c  mov     [rbp+57h+var_D0], r14d
0x140024b10  mov     r8, rsi
0x140024b13  lea     r9, [rbp+57h+var_D0]
0x140024b17  lea     rdx, aMaxackdelayms; "MaxAckDelayMs"
0x140024b1e  mov     rcx, rdi
0x140024b21  call    CxPlatStorageReadValue
0x140024b26  cmp     dword ptr [rsi], 3FFFh
0x140024b2c  jbe     short loc_140024B34
0x140024b2e  mov     dword ptr [rsi], 19h
0x140024b34  mov     eax, [rbx]
0x140024b36  bt      rax, 11h
0x140024b3b  jb      short loc_140024B66
0x140024b3d  lea     rsi, [rbx+68h]
0x140024b41  mov     [rbp+57h+var_D0], r14d
0x140024b45  mov     r8, rsi
0x140024b48  lea     r9, [rbp+57h+var_D0]
0x140024b4c  lea     rdx, aDisconnecttime; "DisconnectTimeoutMs"
0x140024b53  mov     rcx, rdi
0x140024b56  call    CxPlatStorageReadValue
0x140024b5b  mov     eax, 927C0h
0x140024b60  cmp     [rsi], eax
0x140024b62  jbe     short loc_140024B66
0x140024b64  mov     [rsi], eax
0x140024b66  mov     eax, [rbx]
0x140024b68  bt      rax, 12h
0x140024b6d  jb      short loc_140024B8A
0x140024b6f  lea     r8, [rbx+6Ch]
0x140024b73  mov     [rbp+57h+var_D0], r14d
0x140024b77  lea     r9, [rbp+57h+var_D0]
0x140024b7b  mov     rcx, rdi
0x140024b7e  lea     rdx, aKeepaliveinter; "KeepAliveIntervalMs"
0x140024b85  call    CxPlatStorageReadValue
0x140024b8a  mov     esi, 7530h
0x140024b8f  mov     r15, 3FFFFFFFFFFFFFFFh
0x140024b99  test    [rbx], r14b
0x140024b9c  jnz     short loc_140024BDA
0x140024b9e  lea     r9, [rbp+57h+var_D0]
0x140024ba2  mov     [rbp+57h+var_D0], 8
0x140024ba9  lea     r8, [rbp+57h+var_C8]
0x140024bad  mov     rcx, rdi
0x140024bb0  lea     rdx, aIdletimeoutms; "IdleTimeoutMs"
0x140024bb7  call    CxPlatStorageReadValue
0x140024bbc  test    eax, eax
0x140024bbe  js      short loc_140024BDA
0x140024bc0  mov     eax, dword ptr [rbp+57h+var_C8]
0x140024bc3  cmp     [rbp+57h+var_D0], r14d
0x140024bc7  jz      short loc_140024BCD
0x140024bc9  mov     rax, [rbp+57h+var_C8]
0x140024bcd  mov     [rbx+20h], rax
0x140024bd1  cmp     rax, r15
0x140024bd4  jbe     short loc_140024BDA
0x140024bd6  mov     [rbx+20h], rsi
0x140024bda  test    byte ptr [rbx], 2
0x140024bdd  jnz     short loc_140024C1B
0x140024bdf  lea     r9, [rbp+57h+var_D0]
0x140024be3  mov     [rbp+57h+var_D0], 8
0x140024bea  lea     r8, [rbp+57h+var_C8]
0x140024bee  mov     rcx, rdi
0x140024bf1  lea     rdx, aHandshakeidlet; "HandshakeIdleTimeoutMs"
0x140024bf8  call    CxPlatStorageReadValue
0x140024bfd  test    eax, eax
0x140024bff  js      short loc_140024C1B
0x140024c01  mov     eax, dword ptr [rbp+57h+var_C8]
0x140024c04  cmp     [rbp+57h+var_D0], r14d
0x140024c08  jz      short loc_140024C0E
0x140024c0a  mov     rax, [rbp+57h+var_C8]
0x140024c0e  mov     [rbx+18h], rax
0x140024c12  cmp     rax, r15
0x140024c15  jbe     short loc_140024C1B
0x140024c17  mov     [rbx+18h], rsi
0x140024c1b  test    byte ptr [rbx], 8
0x140024c1e  jnz     short loc_140024C3B
0x140024c20  lea     r8, [rbx+30h]
0x140024c24  mov     [rbp+57h+var_D0], r14d
0x140024c28  lea     r9, [rbp+57h+var_D0]
0x140024c2c  mov     rcx, rdi
0x140024c2f  lea     rdx, aTlsclientmaxse; "TlsClientMaxSendBuffer"
0x140024c36  call    CxPlatStorageReadValue
0x140024c3b  test    byte ptr [rbx], 10h
0x140024c3e  jnz     short loc_140024C5B
0x140024c40  lea     r8, [rbx+34h]
0x140024c44  mov     [rbp+57h+var_D0], r14d
0x140024c48  lea     r9, [rbp+57h+var_D0]
0x140024c4c  mov     rcx, rdi
0x140024c4f  lea     rdx, aTlsservermaxse; "TlsServerMaxSendBuffer"
0x140024c56  call    CxPlatStorageReadValue
0x140024c5b  test    byte ptr [rbx], 20h
0x140024c5e  jnz     short loc_140024C7B
0x140024c60  lea     r8, [rbx+38h]
0x140024c64  mov     [rbp+57h+var_D0], r14d
0x140024c68  lea     r9, [rbp+57h+var_D0]
0x140024c6c  mov     rcx, rdi
0x140024c6f  lea     rdx, aStreamrecvwind_2; "StreamRecvWindowDefault"
0x140024c76  call    CxPlatStorageReadValue
0x140024c7b  test    byte ptr [rbx], 40h
0x140024c7e  jnz     short loc_140024C9B
0x140024c80  lea     r8, [rbx+3Ch]
0x140024c84  mov     [rbp+57h+var_D0], r14d
0x140024c88  lea     r9, [rbp+57h+var_D0]
0x140024c8c  mov     rcx, rdi
0x140024c8f  lea     rdx, aStreamrecvwind; "StreamRecvWindowBidiLocalDefault"
  ... truncated ...
```
