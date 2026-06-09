# QuicCryptoProcessTlsCompletion

- ea: `0x1400099b4`
- end: `0x14000a085`
- name: `QuicCryptoProcessTlsCompletion`
- size: `1745`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400098e8`

## callees

- `0x14000491c`
- `0x140008778`
- `0x140008944`
- `0x14000935c`
- `0x1400099b4`
- `0x14000d490`
- `0x14000d638`
- `0x140010820`
- `0x1400123b0`
- `0x14001bcf0`
- `0x14001c638`
- `0x14001dcd0`
- `0x14001df0c`
- `0x140025608`
- `0x1400291f0`
- `0x140029ef0`
- `0x14002bbbc`
- `0x14002fdc4`
- `0x140030bec`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ec10`
- `0x14003fdf8`
- `0x1400426e8`
- `0x1400427e0`
- `0x140042b1c`
- `0x1400492d4`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140009a7a`
- `ntoskrnl!_snprintf_s` at `0x140009adb`
- `ntoskrnl!_snprintf_s` at `0x140009e46`
- `ntoskrnl!_snprintf_s` at `0x140009f9f`
- `ntoskrnl!_snprintf_s` at `0x140009a7a`
- `ntoskrnl!_snprintf_s` at `0x140009adb`
- `ntoskrnl!_snprintf_s` at `0x140009e46`
- `ntoskrnl!_snprintf_s` at `0x140009f9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ec8`
- `HAL!KeQueryPerformanceCounter` at `0x140009cfa`
- `HAL!KeQueryPerformanceCounter` at `0x140009d1c`
- `HAL!KeQueryPerformanceCounter` at `0x140009cfa`
- `HAL!KeQueryPerformanceCounter` at `0x140009d1c`

## string_xrefs

- `0x140009b7a`: `Crypto->TlsState.WriteKeys[Crypto->TlsState.WriteKey] != ((void *)0)`
- `0x140009c73`: `Crypto->TlsState.WriteKey >= Crypto->TlsState.ReadKey`
- `0x140009c92`: `Crypto->TlsState.ReadKeys[Crypto->TlsState.ReadKey] != ((void *)0)`
- `0x140009de7`: `Crypto->TlsState.ReadKeys[QUIC_PACKET_KEY_1_RTT] != ((void *)0)`
- `0x140009e04`: `Crypto->TlsState.WriteKeys[QUIC_PACKET_KEY_1_RTT] != ((void *)0)`

## pseudocode

```c
__int64 __fastcall QuicCryptoProcessTlsCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 result; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // r9
  int v14; // edx
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int128 v19; // xmm1
  __int64 v20; // rcx
  _QWORD **v21; // rcx
  __int64 v22; // rsi
  unsigned __int8 *v23; // rax
  _BYTE *v24; // rcx
  char v25; // r9
  bool v26; // r9
  __int64 v27; // rcx
  __int128 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h]
  __int128 v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+60h] [rbp-A0h]
  char DstBuf[128]; // [rsp+70h] [rbp-90h] BYREF
  char v33[128]; // [rsp+F0h] [rbp-10h] BYREF
  char v34[128]; // [rsp+170h] [rbp+70h] BYREF
  char v35[128]; // [rsp+1F0h] [rbp+F0h] BYREF

  v4 = *(_DWORD *)(a1 + 200);
  v5 = a1 - 2784;
  v6 = a1;
  if ( (v4 & 0x8000) != 0 )
  {
    if ( (byte_14005C48B & 4) != 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        a1,
        (unsigned int)QuicConnErrorStatus,
        a1 - 2784,
        *(unsigned __int16 *)(a1 + 32),
        (__int64)"Received alert from TLS");
    v7 = (unsigned __int8)*(_WORD *)(v6 + 32) | 0x100LL;
    return QuicConnCloseLocally(v5, 2, v7);
  }
  if ( (v4 & 0x10) != 0 )
  {
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "0-RTT accepted");
      McTemplateU0ps_EtwWriteTransfer(v9, QuicConnLogInfo, v5, DstBuf);
    }
    if ( *(_DWORD *)(v6 + 20) != 3 )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1401,
        "Crypto->TlsState.EarlyDataState == CXPLAT_TLS_EARLY_DATA_ACCEPTED");
  }
  if ( (*(_DWORD *)(v6 + 200) & 0x20) != 0 )
  {
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(v33, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "0-RTT rejected");
      McTemplateU0ps_EtwWriteTransfer(v10, QuicConnLogInfo, v5, v33);
    }
    if ( *(_DWORD *)(v6 + 20) == 3 )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1409,
        "Crypto->TlsState.EarlyDataState != CXPLAT_TLS_EARLY_DATA_ACCEPTED");
    if ( (unsigned __int8)QuicConnIsClient(v5) )
    {
      QuicCryptoDiscardKeys(v6, 1);
      QuicLossDetectionOnZeroRttRejected(v5 + 2632);
    }
    else
    {
      QuicConnDiscardDeferred0Rtt();
    }
  }
  if ( (*(_DWORD *)(v6 + 200) & 8) != 0 )
  {
    if ( (byte_14005C48A & 4) != 0 )
    {
      LOBYTE(a4) = *(_BYTE *)(v6 + 28);
      McTemplateU0pu_EtwWriteTransfer(a1, QuicConnWriteKeyUpdated, v5, a4);
    }
    if ( !*(_QWORD *)(v6 + 8LL * *(int *)(v6 + 28) + 136) )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1426,
        "Crypto->TlsState.WriteKeys[Crypto->TlsState.WriteKey] != ((void *)0)");
    if ( *(_DWORD *)(v6 + 28) == 3 )
    {
      if ( (unsigned __int8)QuicConnIsClient(v5) )
        QuicCryptoDiscardKeys(v6, 1);
      QuicSendQueueFlush(v5 + 3416, 8);
    }
    if ( (unsigned __int8)QuicConnIsServer(v5) )
    {
      if ( v11 == 3 )
        *(_DWORD *)(v5 + 3700) = *(_DWORD *)(v6 + 48);
    }
    else
    {
      if ( v11 == 2 )
        *(_DWORD *)(v5 + 3696) = *(_DWORD *)(v6 + 44);
      if ( *(_DWORD *)(v6 + 28) == 3 )
      {
        a1 = (unsigned int)(*(_DWORD *)(v6 + 48) - *(_DWORD *)(v6 + 44));
        *(_DWORD *)(v5 + 3704) = a1;
      }
    }
  }
  if ( (*(_DWORD *)(v6 + 200) & 4) != 0 )
  {
    if ( (unsigned __int8)QuicRecvBufferHasUnreadData(v6 + 392) )
    {
      if ( (byte_14005C48B & 4) != 0 )
        McTemplateU0ps_EtwWriteTransfer(v12, QuicConnError, v5, "Leftover crypto data in previous encryption level.");
      v7 = 10;
      return QuicConnCloseLocally(v5, 2, v7);
    }
    *(_DWORD *)(v6 + 388) = *(_DWORD *)(v6 + 376);
    if ( (byte_14005C48A & 4) != 0 )
    {
      LOBYTE(v13) = *(_BYTE *)(v6 + 24);
      McTemplateU0pu_EtwWriteTransfer(v12, QuicConnReadKeyUpdated, v5, v13);
    }
    if ( *(_DWORD *)(v6 + 28) < *(_DWORD *)(v6 + 24) )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1493,
        "Crypto->TlsState.WriteKey >= Crypto->TlsState.ReadKey");
    if ( !*(_QWORD *)(v6 + 8LL * *(int *)(v6 + 24) + 88) )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1494,
        "Crypto->TlsState.ReadKeys[Crypto->TlsState.ReadKey] != ((void *)0)");
    if ( (unsigned __int8)QuicConnIsServer(v5) )
    {
      if ( v14 == 2 )
        *(_DWORD *)(v5 + 3696) = *(_DWORD *)(v6 + 376);
      if ( *(_DWORD *)(v6 + 24) == 3 )
      {
        a1 = (unsigned int)(*(_DWORD *)(v6 + 376) - *(_DWORD *)(v5 + 3696));
        *(_DWORD *)(v5 + 3704) = a1;
      }
    }
    else if ( v14 == 3 )
    {
      *(_DWORD *)(v5 + 3700) = *(_DWORD *)(v6 + 376);
    }
    if ( !*(_QWORD *)(v5 + 3648) )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      *(_QWORD *)(v5 + 3648) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
    }
    if ( *(_DWORD *)(v6 + 24) == 3 )
    {
      v16 = KeQueryPerformanceCounter(0);
      *(_QWORD *)(v5 + 3656) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)v16.QuadPart);
    }
  }
  if ( (*(_DWORD *)(v6 + 200) & 2) != 0 )
  {
    if ( *(_QWORD *)(v5 + 3872)
      && (unsigned __int8)QuicConnIsClient(v5)
      && *(_DWORD *)(v6 + 28) <= 1u
      && *(_WORD *)(v6 + 34) )
    {
      v18 = *(_QWORD *)(v6 + 56);
      *(_OWORD *)(v17 + 2) = *(_OWORD *)(v18 + 6);
      v19 = *(_OWORD *)(v18 + 22);
      *(_BYTE *)(v17 + 1) |= 1u;
      *(_OWORD *)(v17 + 18) = v19;
      *(_QWORD *)(v5 + 3872) = 0;
    }
    QuicSendSetSendFlag(v6 + 632, 2);
    QuicCryptoDumpSendState(v6);
  }
  if ( (*(_DWORD *)(v6 + 200) & 0x40) != 0 )
  {
    if ( (*(_BYTE *)(v5 + 248) & 8) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c", 1565, "!Connection->State.Connected");
    if ( (byte_14005C489 & 0x40) != 0 )
      McTemplateU0p_EtwWriteTransfer(a1, QuicConnHandshakeComplete);
    if ( !*(_QWORD *)(v6 + 112) )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1576,
        "Crypto->TlsState.ReadKeys[QUIC_PACKET_KEY_1_RTT] != ((void *)0)");
    if ( !*(_QWORD *)(v6 + 160) )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        1577,
        "Crypto->TlsState.WriteKeys[QUIC_PACKET_KEY_1_RTT] != ((void *)0)");
    if ( (unsigned __int8)QuicConnIsServer(v5) )
    {
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(v34, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Handshake confirmed (server)");
        McTemplateU0ps_EtwWriteTransfer(v20, QuicConnLogInfo, v5, v34);
      }
      QuicSendSetSendFlag(v5 + 3416, 0x2000);
      QuicCryptoHandshakeConfirmed(v6, 0);
      v21 = *(_QWORD ***)(v5 + 1280);
      v22 = (__int64)(*v21 - 3);
      *v21 = (_QWORD *)**v21;
      if ( (byte_14005C48A & 4) != 0 )
        McTemplateU0pxubr2_EtwWriteTransfer(
          (_DWORD)v21,
          (unsigned int)QuicConnSourceCidRemoved,
          v5,
          *(_QWORD *)(v22 + 48),
          *(_BYTE *)(v22 + 41),
          v22 + 56);
      ExFreePoolWithTag((PVOID)v22, 0x44306351u);
    }
    *(_BYTE *)(v5 + 248) |= 8u;
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v5 + 72) + 2248LL));
    QuicConnGenerateNewSourceCids(v5, 0);
    if ( (unsigned __int8)QuicConnIsClient(v5) )
    {
      v23 = CxPlatTlsAlpnFindInList(
              *(_WORD *)(*(_QWORD *)(v5 + 88) + 240LL),
              (unsigned __int8 *)(*(_QWORD *)(v5 + 88) + 242LL),
              **(_BYTE **)(v6 + 80),
              (const void *)(*(_QWORD *)(v6 + 80) + 1LL));
      *(_QWORD *)(v6 + 80) = v23;
      if ( !v23 )
        CxPlatLogAssert(
          "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
          1644,
          "Crypto->TlsState.NegotiatedAlpn != ((void *)0)");
    }
    v24 = *(_BYTE **)(v6 + 80);
    v25 = *(_BYTE *)(v6 + 16);
    v28 = 0;
    v26 = (v25 & 2) != 0;
    v31 = 0;
    v29 = 0;
    BYTE8(v28) = v26;
    v30 = 0;
    BYTE9(v28) = *v24;
    *(_QWORD *)&v29 = v24 + 1;
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(v35, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Indicating QUIC_CONNECTION_EVENT_CONNECTED (Resume=%hhu)", v26);
      McTemplateU0ps_EtwWriteTransfer(v27, QuicConnLogVerbose, v5, v35);
    }
    QuicConnIndicateEvent(v5, &v28);
    if ( (*(_BYTE *)(v6 + 16) & 2) != 0 )
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v5 + 72) + 2232LL));
    *(_DWORD *)(v5 + 3632) ^= ((unsigned __int8)*(_DWORD *)(v5 + 3632) ^ (unsigned __int8)(4 * *(_BYTE *)(v6 + 16))) & 8;
    if ( (*(_BYTE *)(v5 + 236) & 4) != 0 )
      QuicPathUpdateQeo(v5, v5 + 320, 0);
    QuicMtuDiscoveryPeerValidated(v5 + 344, v5);
    if ( (unsigned __int8)QuicConnIsServer(v5) && *(_DWORD *)(v6 + 48) && *(_DWORD *)(v6 + 208) == *(_DWORD *)(v6 + 40) )
      QuicConnCleanupServerResumptionState();
  }
  result = *(unsigned int *)(v6 + 200);
  if ( (result & 4) != 0 )
    return QuicConnFlushDeferred(v5);
  return result;
}

```

## disassembly

```asm
0x1400099b4  mov     [rsp-8+arg_8], rbx
0x1400099b9  mov     [rsp-8+arg_10], rsi
0x1400099be  push    rbp
0x1400099bf  push    rdi
0x1400099c0  push    r12
0x1400099c2  push    r13
0x1400099c4  push    r14
0x1400099c6  lea     rbp, [rsp-180h]
0x1400099ce  sub     rsp, 280h
0x1400099d5  mov     rax, cs:__security_cookie
0x1400099dc  xor     rax, rsp
0x1400099df  mov     [rbp+1A0h+var_30], rax
0x1400099e6  mov     eax, [rcx+0C8h]
0x1400099ec  lea     rdi, [rcx-0AE0h]
0x1400099f3  mov     rbx, rcx
0x1400099f6  bt      eax, 0Fh
0x1400099fa  jnb     short loc_140009A4A
0x1400099fc  mov     r14b, 4
0x1400099ff  test    cs:byte_14005C48B, r14b
0x140009a06  jz      short loc_140009A28
0x140009a08  movzx   r9d, word ptr [rcx+20h]
0x140009a0d  lea     rax, aReceivedAlertF; "Received alert from TLS"
0x140009a14  mov     r8, rdi
0x140009a17  mov     [rsp+2A0h+var_280], rax
0x140009a1c  lea     rdx, QuicConnErrorStatus
0x140009a23  call    McTemplateU0pqs_EtwWriteTransfer
0x140009a28  movzx   eax, word ptr [rbx+20h]
0x140009a2c  movzx   r8d, al
0x140009a30  bts     r8, 8
0x140009a35  mov     edx, 2
0x140009a3a  xor     r9d, r9d
0x140009a3d  mov     rcx, rdi
0x140009a40  call    QuicConnCloseLocally
0x140009a45  jmp     loc_14000A059
0x140009a4a  lea     r13, aCW1SMsquicSrcC_15; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x140009a51  mov     esi, 3
0x140009a56  lea     r14d, [rsi+7Dh]
0x140009a5a  test    al, 10h
0x140009a5c  jz      short loc_140009AB3
0x140009a5e  test    cs:byte_14005C48B, r14b
0x140009a65  jz      short loc_140009A9A
0x140009a67  lea     r9, a0RttAccepted; "0-RTT accepted"
0x140009a6e  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140009a72  mov     edx, r14d; SizeInBytes
0x140009a75  lea     rcx, [rsp+2A0h+DstBuf]; DstBuf
0x140009a7a  call    cs:__imp__snprintf_s
0x140009a81  nop     dword ptr [rax+rax+00h]
0x140009a86  lea     r9, [rsp+2A0h+DstBuf]
0x140009a8b  mov     r8, rdi
0x140009a8e  lea     rdx, QuicConnLogInfo
0x140009a95  call    McTemplateU0ps_EtwWriteTransfer
0x140009a9a  cmp     [rbx+14h], esi
0x140009a9d  jz      short loc_140009AB3
0x140009a9f  lea     r8, aCryptoTlsstate_4; "Crypto->TlsState.EarlyDataState == CXPL"...
0x140009aa6  mov     edx, 579h
0x140009aab  mov     rcx, r13
0x140009aae  call    CxPlatLogAssert
0x140009ab3  mov     eax, [rbx+0C8h]
0x140009ab9  xor     r12d, r12d
0x140009abc  test    al, 20h
0x140009abe  jz      short loc_140009B3F
0x140009ac0  test    cs:byte_14005C48B, r14b
0x140009ac7  jz      short loc_140009AFA
0x140009ac9  lea     r9, a0RttRejected; "0-RTT rejected"
0x140009ad0  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140009ad4  mov     rdx, r14; SizeInBytes
0x140009ad7  lea     rcx, [rbp+1A0h+var_1B0]; DstBuf
0x140009adb  call    cs:__imp__snprintf_s
0x140009ae2  nop     dword ptr [rax+rax+00h]
0x140009ae7  lea     r9, [rbp+1A0h+var_1B0]
0x140009aeb  mov     r8, rdi
0x140009aee  lea     rdx, QuicConnLogInfo
0x140009af5  call    McTemplateU0ps_EtwWriteTransfer
0x140009afa  cmp     [rbx+14h], esi
0x140009afd  jnz     short loc_140009B13
0x140009aff  lea     r8, aCryptoTlsstate_6; "Crypto->TlsState.EarlyDataState != CXPL"...
0x140009b06  mov     edx, 581h
0x140009b0b  mov     rcx, r13
0x140009b0e  call    CxPlatLogAssert
0x140009b13  mov     rcx, rdi
0x140009b16  call    QuicConnIsClient
0x140009b1b  test    al, al
0x140009b1d  jz      short loc_140009B3A
0x140009b1f  mov     edx, 1
0x140009b24  mov     rcx, rbx
0x140009b27  call    QuicCryptoDiscardKeys
0x140009b2c  lea     rcx, [rdi+0A48h]
0x140009b33  call    QuicLossDetectionOnZeroRttRejected
0x140009b38  jmp     short loc_140009B3F
0x140009b3a  call    QuicConnDiscardDeferred0Rtt
0x140009b3f  mov     eax, [rbx+0C8h]
0x140009b45  mov     r14b, 4
0x140009b48  test    al, 8
0x140009b4a  jz      loc_140009BFA
0x140009b50  test    cs:byte_14005C48A, r14b
0x140009b57  jz      short loc_140009B6C
0x140009b59  mov     r9b, [rbx+1Ch]
0x140009b5d  lea     rdx, QuicConnWriteKeyUpdated
0x140009b64  mov     r8, rdi
0x140009b67  call    McTemplateU0pu_EtwWriteTransfer
0x140009b6c  movsxd  rax, dword ptr [rbx+1Ch]
0x140009b70  cmp     [rbx+rax*8+88h], r12
0x140009b78  jnz     short loc_140009B8E
0x140009b7a  lea     r8, aCryptoTlsstate_2; "Crypto->TlsState.WriteKeys[Crypto->TlsS"...
0x140009b81  mov     edx, 592h
0x140009b86  mov     rcx, r13
0x140009b89  call    CxPlatLogAssert
0x140009b8e  cmp     [rbx+1Ch], esi
0x140009b91  jnz     short loc_140009BBD
0x140009b93  mov     rcx, rdi
0x140009b96  call    QuicConnIsClient
0x140009b9b  test    al, al
0x140009b9d  jz      short loc_140009BAC
0x140009b9f  mov     edx, 1
0x140009ba4  mov     rcx, rbx
0x140009ba7  call    QuicCryptoDiscardKeys
0x140009bac  lea     rcx, [rdi+0D58h]
0x140009bb3  mov     edx, 8
0x140009bb8  call    QuicSendQueueFlush
0x140009bbd  mov     edx, [rbx+1Ch]
0x140009bc0  mov     rcx, rdi
0x140009bc3  call    QuicConnIsServer
0x140009bc8  test    al, al
0x140009bca  jz      short loc_140009BDB
0x140009bcc  cmp     edx, esi
0x140009bce  jnz     short loc_140009BFA
0x140009bd0  mov     eax, [rbx+30h]
0x140009bd3  mov     [rdi+0E74h], eax
0x140009bd9  jmp     short loc_140009BFA
0x140009bdb  cmp     edx, 2
0x140009bde  jnz     short loc_140009BE9
0x140009be0  mov     eax, [rbx+2Ch]
0x140009be3  mov     [rdi+0E70h], eax
0x140009be9  cmp     [rbx+1Ch], esi
0x140009bec  jnz     short loc_140009BFA
0x140009bee  mov     ecx, [rbx+30h]
0x140009bf1  sub     ecx, [rbx+2Ch]
0x140009bf4  mov     [rdi+0E78h], ecx
0x140009bfa  mov     eax, [rbx+0C8h]
0x140009c00  test    r14b, al
0x140009c03  jz      loc_140009D37
0x140009c09  lea     rcx, [rbx+188h]
0x140009c10  call    QuicRecvBufferHasUnreadData
0x140009c15  test    al, al
0x140009c17  jz      short loc_140009C43
0x140009c19  test    cs:byte_14005C48B, r14b
0x140009c20  jz      short loc_140009C38
0x140009c22  lea     r9, aLeftoverCrypto; "Leftover crypto data in previous encryp"...
0x140009c29  mov     r8, rdi
0x140009c2c  lea     rdx, QuicConnError
0x140009c33  call    McTemplateU0ps_EtwWriteTransfer
0x140009c38  mov     r8d, 0Ah
0x140009c3e  jmp     loc_140009A35
0x140009c43  mov     eax, [rbx+178h]
0x140009c49  mov     [rbx+184h], eax
0x140009c4f  test    cs:byte_14005C48A, r14b
0x140009c56  jz      short loc_140009C6B
0x140009c58  mov     r9b, [rbx+18h]
0x140009c5c  lea     rdx, QuicConnReadKeyUpdated
0x140009c63  mov     r8, rdi
0x140009c66  call    McTemplateU0pu_EtwWriteTransfer
0x140009c6b  mov     eax, [rbx+18h]
0x140009c6e  cmp     [rbx+1Ch], eax
0x140009c71  jge     short loc_140009C87
0x140009c73  lea     r8, aCryptoTlsstate_5; "Crypto->TlsState.WriteKey >= Crypto->Tl"...
0x140009c7a  mov     edx, 5D5h
0x140009c7f  mov     rcx, r13
0x140009c82  call    CxPlatLogAssert
0x140009c87  movsxd  rax, dword ptr [rbx+18h]
0x140009c8b  cmp     [rbx+rax*8+58h], r12
0x140009c90  jnz     short loc_140009CA6
0x140009c92  lea     r8, aCryptoTlsstate; "Crypto->TlsState.ReadKeys[Crypto->TlsSt"...
0x140009c99  mov     edx, 5D6h
0x140009c9e  mov     rcx, r13
0x140009ca1  call    CxPlatLogAssert
0x140009ca6  mov     edx, [rbx+18h]
0x140009ca9  mov     rcx, rdi
0x140009cac  call    QuicConnIsServer
0x140009cb1  test    al, al
0x140009cb3  jz      short loc_140009CDF
0x140009cb5  cmp     edx, 2
0x140009cb8  jnz     short loc_140009CC6
0x140009cba  mov     eax, [rbx+178h]
0x140009cc0  mov     [rdi+0E70h], eax
0x140009cc6  cmp     [rbx+18h], esi
0x140009cc9  jnz     short loc_140009CEF
0x140009ccb  mov     ecx, [rbx+178h]
0x140009cd1  sub     ecx, [rdi+0E70h]
0x140009cd7  mov     [rdi+0E78h], ecx
0x140009cdd  jmp     short loc_140009CEF
0x140009cdf  cmp     edx, esi
0x140009ce1  jnz     short loc_140009CEF
0x140009ce3  mov     eax, [rbx+178h]
0x140009ce9  mov     [rdi+0E74h], eax
0x140009cef  cmp     [rdi+0E40h], r12
0x140009cf6  jnz     short loc_140009D15
0x140009cf8  xor     ecx, ecx; PerformanceFrequency
0x140009cfa  call    cs:__imp_KeQueryPerformanceCounter
0x140009d01  nop     dword ptr [rax+rax+00h]
0x140009d06  mov     rcx, rax
0x140009d09  call    QuicTimePlatToUs64
0x140009d0e  mov     [rdi+0E40h], rax
0x140009d15  cmp     [rbx+18h], esi
0x140009d18  jnz     short loc_140009D37
0x140009d1a  xor     ecx, ecx; PerformanceFrequency
0x140009d1c  call    cs:__imp_KeQueryPerformanceCounter
0x140009d23  nop     dword ptr [rax+rax+00h]
0x140009d28  mov     rcx, rax
0x140009d2b  call    QuicTimePlatToUs64
0x140009d30  mov     [rdi+0E48h], rax
0x140009d37  mov     eax, [rbx+0C8h]
0x140009d3d  test    al, 2
0x140009d3f  jz      short loc_140009D9E
0x140009d41  mov     rdx, [rdi+0F20h]
0x140009d48  test    rdx, rdx
0x140009d4b  jz      short loc_140009D85
0x140009d4d  mov     rcx, rdi
0x140009d50  call    QuicConnIsClient
0x140009d55  test    al, al
0x140009d57  jz      short loc_140009D85
0x140009d59  cmp     dword ptr [rbx+1Ch], 1
0x140009d5d  ja      short loc_140009D85
0x140009d5f  cmp     [rbx+22h], r12w
0x140009d64  jbe     short loc_140009D85
0x140009d66  mov     rax, [rbx+38h]
0x140009d6a  movups  xmm0, xmmword ptr [rax+6]
0x140009d6e  movups  xmmword ptr [rdx+2], xmm0
0x140009d72  movups  xmm1, xmmword ptr [rax+16h]
0x140009d76  or      byte ptr [rdx+1], 1
0x140009d7a  movups  xmmword ptr [rdx+12h], xmm1
0x140009d7e  mov     [rdi+0F20h], r12
0x140009d85  lea     rcx, [rbx+278h]
0x140009d8c  mov     edx, 2
0x140009d91  call    QuicSendSetSendFlag
0x140009d96  mov     rcx, rbx
0x140009d99  call    QuicCryptoDumpSendState
0x140009d9e  mov     eax, [rbx+0C8h]
0x140009da4  test    al, 40h
0x140009da6  jz      loc_14000A046
0x140009dac  test    byte ptr [rdi+0F8h], 8
0x140009db3  jz      short loc_140009DC9
0x140009db5  lea     r8, aConnectionStat; "!Connection->State.Connected"
0x140009dbc  mov     edx, 61Dh
0x140009dc1  mov     rcx, r13
0x140009dc4  call    CxPlatLogAssert
0x140009dc9  test    cs:byte_14005C489, 40h
0x140009dd0  jz      short loc_140009DE1
0x140009dd2  mov     r8, rdi
0x140009dd5  lea     rdx, QuicConnHandshakeComplete
0x140009ddc  call    McTemplateU0p_EtwWriteTransfer
0x140009de1  cmp     [rbx+70h], r12
0x140009de5  jnz     short loc_140009DFB
0x140009de7  lea     r8, aCryptoTlsstate_7; "Crypto->TlsState.ReadKeys[QUIC_PACKET_K"...
0x140009dee  mov     edx, 628h
0x140009df3  mov     rcx, r13
0x140009df6  call    CxPlatLogAssert
0x140009dfb  cmp     [rbx+0A0h], r12
0x140009e02  jnz     short loc_140009E18
0x140009e04  lea     r8, aCryptoTlsstate_1; "Crypto->TlsState.WriteKeys[QUIC_PACKET_"...
0x140009e0b  mov     edx, 629h
0x140009e10  mov     rcx, r13
0x140009e13  call    CxPlatLogAssert
0x140009e18  mov     rcx, rdi
0x140009e1b  call    QuicConnIsServer
0x140009e20  test    al, al
0x140009e22  jz      loc_140009ED4
0x140009e28  mov     al, cs:byte_14005C48B
0x140009e2e  test    al, al
0x140009e30  jns     short loc_140009E65
0x140009e32  lea     r9, aHandshakeConfi_1; "Handshake confirmed (server)"
0x140009e39  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140009e3d  mov     edx, 80h; SizeInBytes
0x140009e42  lea     rcx, [rbp+1A0h+var_130]; DstBuf
0x140009e46  call    cs:__imp__snprintf_s
0x140009e4d  nop     dword ptr [rax+rax+00h]
0x140009e52  lea     r9, [rbp+1A0h+var_130]
0x140009e56  mov     r8, rdi
0x140009e59  lea     rdx, QuicConnLogInfo
0x140009e60  call    McTemplateU0ps_EtwWriteTransfer
0x140009e65  lea     rcx, [rdi+0D58h]
0x140009e6c  mov     edx, 2000h
0x140009e71  call    QuicSendSetSendFlag
0x140009e76  xor     edx, edx
0x140009e78  mov     rcx, rbx
0x140009e7b  call    QuicCryptoHandshakeConfirmed
0x140009e80  mov     rcx, [rdi+500h]
0x140009e87  mov     rax, [rcx]
0x140009e8a  lea     rsi, [rax-18h]
0x140009e8e  mov     rax, [rax]
0x140009e91  mov     [rcx], rax
0x140009e94  test    cs:byte_14005C48A, r14b
0x140009e9b  jz      short loc_140009EC0
0x140009e9d  mov     r9, [rsi+30h]
0x140009ea1  lea     rax, [rsi+38h]
0x140009ea5  mov     [rsp+2A0h+var_278], rax
0x140009eaa  lea     rdx, QuicConnSourceCidRemoved
0x140009eb1  mov     al, [rsi+29h]
0x140009eb4  mov     r8, rdi
0x140009eb7  mov     byte ptr [rsp+2A0h+var_280], al
0x140009ebb  call    McTemplateU0pxubr2_EtwWriteTransfer
  ... truncated ...
```
