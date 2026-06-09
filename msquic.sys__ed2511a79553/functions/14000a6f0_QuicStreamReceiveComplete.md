# QuicStreamReceiveComplete

- ea: `0x14000a6f0`
- end: `0x14000ac48`
- name: `QuicStreamReceiveComplete`
- size: `1368`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14000a2b0`
- `0x14000c774`

## callees

- `0x14000a6f0`
- `0x14000ac50`
- `0x14000acfc`
- `0x14000b780`
- `0x1400145c0`
- `0x140026530`
- `0x140030570`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ec10`
- `0x140040de8`
- `0x1400426e8`
- `0x1400451c4`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000a89d`
- `ntoskrnl!_snprintf_s` at `0x14000a8fb`
- `ntoskrnl!_snprintf_s` at `0x14000a974`
- `ntoskrnl!_snprintf_s` at `0x14000aaae`
- `ntoskrnl!_snprintf_s` at `0x14000ab0c`
- `ntoskrnl!_snprintf_s` at `0x14000ab85`
- `ntoskrnl!_snprintf_s` at `0x14000a89d`
- `ntoskrnl!_snprintf_s` at `0x14000a8fb`
- `ntoskrnl!_snprintf_s` at `0x14000a974`
- `ntoskrnl!_snprintf_s` at `0x14000aaae`
- `ntoskrnl!_snprintf_s` at `0x14000ab0c`
- `ntoskrnl!_snprintf_s` at `0x14000ab85`

## string_xrefs

- `0x14000aa97`: `Indicating QUIC_STREAM_EVENT_SHUTDOWN_COMPLETE [Shutdown=%hhu, ShutdownByApp=%hhu, ClosedRemotely=%hhu, ErrorCode=0x%llx, CloseStatus=0x%x]`

## pseudocode

```c
bool __fastcall QuicStreamReceiveComplete(__int64 a1, unsigned __int64 a2)
{
  char v2; // al
  __int64 v5; // rcx
  char v6; // al
  __int64 v7; // rax
  char v8; // al
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned int State; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, _QWORD, _DWORD *); // rax
  __int64 v18; // rcx
  char v19; // cl
  unsigned __int16 v20; // cx
  __int64 v21; // rcx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  char v24; // dl
  __int64 v25; // rcx
  char v26; // dl
  char v27; // r9
  unsigned __int8 v28; // r8
  __int64 v29; // r10
  int v30; // r11d
  __int64 v31; // rcx
  void (__fastcall *v32)(__int64, _QWORD, __int128 *); // rax
  __int64 v33; // rcx
  __int16 v34; // cx
  __int64 v35; // rcx
  bool v36; // zf
  __int64 v37; // rcx
  _QWORD *v38; // rax
  unsigned int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int128 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v43; // [rsp+60h] [rbp-A0h]
  int v44; // [rsp+70h] [rbp-90h]
  _DWORD v45[5]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v46; // [rsp+8Ch] [rbp-74h]
  char DstBuf[128]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = *(_BYTE *)(a1 + 90);
  if ( v2 >= 0 && (v2 & 0x20) == 0 )
  {
    if ( (byte_14005C48D & 2) != 0 )
      McTemplateU0pp_EtwWriteTransfer(a1, QuicStreamAppReceiveComplete, a1);
    if ( a2 > *(_QWORD *)(a1 + 688) )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\stream_recv.c",
        1114,
        "BufferLength <= Stream->RecvPendingLength");
    v5 = *(_QWORD *)(a1 + 688);
    if ( !v5 || (v6 = QuicRecvBufferDrain(a1 + 448, a2), v5 = *(_QWORD *)(a1 + 688), v6) )
      *(_BYTE *)(a1 + 91) &= ~0x40u;
    if ( a2 )
    {
      v7 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 688) = v5 - a2;
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v7 + 72) + 2360LL), a2);
      QuicStreamOnBytesDelivered(a1, a2);
    }
    v8 = *(_BYTE *)(a1 + 91);
    if ( *(_QWORD *)(a1 + 688) )
    {
      if ( (v8 & 8) == 0 )
        *(_QWORD *)(a1 + 688) = 0;
    }
    else
    {
      v8 |= 4u;
      *(_BYTE *)(a1 + 91) = v8;
    }
    if ( (v8 & 4) != 0 )
    {
      if ( (v8 & 0x40) != 0 )
        return (v8 & 8) == 0;
      v12 = *(_QWORD *)(a1 + 640);
      v13 = *(_QWORD *)(a1 + 680);
      if ( v12 == v13 )
      {
        *(_BYTE *)(a1 + 90) |= 0x20u;
        *(_BYTE *)(a1 + 91) = v8 | 1;
        if ( (byte_14005C48C & 2) != 0 )
        {
          State = QuicStreamRecvGetState(a1);
          McTemplateU0pu_EtwWriteTransfer(v15, QuicStreamRecvState, a1, State);
        }
        v45[0] = 3;
        *(_OWORD *)&v45[1] = 0;
        v46 = 0;
        if ( (byte_14005C48D & 1) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Indicating QUIC_STREAM_EVENT_PEER_SEND_SHUTDOWN");
          McTemplateU0ps_EtwWriteTransfer(v16, QuicStreamLogVerbose, a1, DstBuf);
        }
        v17 = *(void (__fastcall **)(__int64, _QWORD, _DWORD *))(a1 + 712);
        if ( v17 )
        {
          v17(a1, *(_QWORD *)(a1 + 8), v45);
        }
        else if ( (byte_14005C48C & 0x40) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Event silently discarded");
          McTemplateU0ps_EtwWriteTransfer(v18, QuicStreamLogWarning, a1, DstBuf);
        }
        if ( (*(_BYTE *)(a1 + 92) & 0x10) == 0 )
        {
          v19 = *(_BYTE *)(a1 + 91);
          if ( (v19 & 0x40) == 0 && (*(_BYTE *)(a1 + 90) & 2) != 0 && (v19 & 1) != 0 )
          {
            v20 = *(_WORD *)(a1 + 96);
            if ( v20 )
            {
              if ( (byte_14005C48D & 1) != 0 )
              {
                _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Removing flags %x", v20);
                McTemplateU0ps_EtwWriteTransfer(v21, QuicStreamLogVerbose, a1, DstBuf);
              }
              v22 = *(_QWORD *)(a1 + 56);
              *(_WORD *)(a1 + 96) = 0;
              if ( v22 )
              {
                v23 = *(_QWORD **)(a1 + 64);
                *v23 = v22;
                *(_QWORD *)(v22 + 8) = v23;
                *(_QWORD *)(a1 + 56) = 0;
                QuicStreamRelease(a1);
              }
            }
            v24 = *(_BYTE *)(a1 + 92);
            *(_BYTE *)(a1 + 92) = v24 | 0x10;
            if ( (v24 & 4) == 0 )
            {
              v25 = *(_QWORD *)(a1 + 72);
              v44 = 0;
              v26 = v24 | 0x14;
              *(_BYTE *)(a1 + 92) = v26;
              v42 = 0;
              v43 = 0;
              LODWORD(v42) = 7;
              v27 = *(_BYTE *)(v25 + 248) & 0x30;
              BYTE8(v42) = v27 != 0;
              BYTE9(v42) = ((v26 & 8) != 0) ^ (((v26 & 8) != 0) ^ (*(_BYTE *)(v25 + 248) >> 6)) & 2;
              v28 = BYTE9(v42) ^ (BYTE9(v42) ^ (*(_BYTE *)(v25 + 248) >> 3)) & 4;
              BYTE9(v42) = v28;
              v29 = *(_QWORD *)(v25 + 1592);
              *(_QWORD *)&v43 = v29;
              v30 = *(_DWORD *)(v25 + 1588);
              DWORD2(v43) = v30;
              if ( (byte_14005C48D & 1) != 0 )
              {
                _snprintf_s(
                  DstBuf,
                  0x80u,
                  0xFFFFFFFFFFFFFFFFuLL,
                  "Indicating QUIC_STREAM_EVENT_SHUTDOWN_COMPLETE [Shutdown=%hhu, ShutdownByApp=%hhu, ClosedRemotely=%hhu"
                  ", ErrorCode=0x%llx, CloseStatus=0x%x]",
                  v27 != 0,
                  (v28 >> 1) & 1,
                  (v28 >> 2) & 1,
                  v29,
                  v30);
                McTemplateU0ps_EtwWriteTransfer(v31, QuicStreamLogVerbose, a1, DstBuf);
              }
              v32 = *(void (__fastcall **)(__int64, _QWORD, __int128 *))(a1 + 712);
              if ( v32 )
              {
                v32(a1, *(_QWORD *)(a1 + 8), &v42);
              }
              else if ( (byte_14005C48C & 0x40) != 0 )
              {
                _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Event silently discarded");
                McTemplateU0ps_EtwWriteTransfer(v33, QuicStreamLogWarning, a1, DstBuf);
              }
              *(_QWORD *)(a1 + 712) = 0;
            }
            if ( (*(_BYTE *)(a1 + 93) & 2) == 0 || (*(_BYTE *)(a1 + 92) & 8) != 0 )
              QuicStreamSetReleaseStream(*(_QWORD *)(a1 + 72) + 2032LL, a1);
          }
        }
        v34 = *(_WORD *)(a1 + 96);
        if ( (v34 & 0xA) != 0 )
        {
          if ( (byte_14005C48D & 1) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Removing flags %x", v34 & 0xA);
            McTemplateU0ps_EtwWriteTransfer(v35, QuicStreamLogVerbose, a1, DstBuf);
          }
          v36 = (*(_WORD *)(a1 + 96) & 0xFFF5) == 0;
          *(_WORD *)(a1 + 96) &= 0xFFF5u;
          if ( v36 )
          {
            v37 = *(_QWORD *)(a1 + 56);
            if ( v37 )
            {
              v38 = *(_QWORD **)(a1 + 64);
              *v38 = v37;
              *(_QWORD *)(v37 + 8) = v38;
              *(_QWORD *)(a1 + 56) = 0;
              QuicStreamRelease(a1);
            }
          }
        }
      }
      else if ( *(char *)(a1 + 89) < 0 && v12 >= v13 )
      {
        if ( (byte_14005C48C & 2) != 0 )
        {
          v39 = QuicStreamRecvGetState(a1);
          McTemplateU0pu_EtwWriteTransfer(v40, QuicStreamRecvState, a1, v39);
        }
        QuicStreamIndicatePeerSendAbortedEvent(a1, *(_QWORD *)(a1 + 704));
        LOBYTE(v41) = 1;
        QuicStreamRecvShutdown(a1, v41, *(_QWORD *)(a1 + 704));
      }
    }
    else if ( (byte_14005C48C & 2) != 0 )
    {
      v9 = QuicStreamRecvGetState(a1);
      McTemplateU0pu_EtwWriteTransfer(v10, QuicStreamRecvState, a1, v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000a6f0  mov     [rsp-8+arg_10], rbx
0x14000a6f5  mov     [rsp-8+arg_18], rdi
0x14000a6fa  push    rbp
0x14000a6fb  lea     rbp, [rsp-30h]
0x14000a700  sub     rsp, 130h
0x14000a707  mov     rax, cs:__security_cookie
0x14000a70e  xor     rax, rsp
0x14000a711  mov     [rbp+30h+var_10], rax
0x14000a715  movzx   eax, byte ptr [rcx+5Ah]
0x14000a719  mov     rdi, rdx
0x14000a71c  mov     rbx, rcx
0x14000a71f  test    al, al
0x14000a721  js      loc_14000AC24
0x14000a727  test    al, 20h
0x14000a729  jnz     loc_14000AC24
0x14000a72f  test    cs:byte_14005C48D, 2
0x14000a736  jz      short loc_14000A74A
0x14000a738  mov     r9, rdx
0x14000a73b  mov     r8, rcx
0x14000a73e  lea     rdx, QuicStreamAppReceiveComplete
0x14000a745  call    McTemplateU0pp_EtwWriteTransfer
0x14000a74a  cmp     rdi, [rbx+2B0h]
0x14000a751  jbe     short loc_14000A76B
0x14000a753  lea     r8, aBufferlengthSt; "BufferLength <= Stream->RecvPendingLeng"...
0x14000a75a  mov     edx, 45Ah
0x14000a75f  lea     rcx, aCW1SMsquicSrcC_4; "C:\\__w\\1\\s\\msquic\\src\\core\\strea"...
0x14000a766  call    CxPlatLogAssert
0x14000a76b  mov     rcx, [rbx+2B0h]
0x14000a772  test    rcx, rcx
0x14000a775  jz      short loc_14000A791
0x14000a777  lea     rcx, [rbx+1C0h]
0x14000a77e  mov     rdx, rdi
0x14000a781  call    QuicRecvBufferDrain
0x14000a786  mov     rcx, [rbx+2B0h]
0x14000a78d  test    al, al
0x14000a78f  jz      short loc_14000A795
0x14000a791  and     byte ptr [rbx+5Bh], 0BFh
0x14000a795  test    rdi, rdi
0x14000a798  jz      short loc_14000A7BF
0x14000a79a  mov     rax, [rbx+48h]
0x14000a79e  sub     rcx, rdi
0x14000a7a1  mov     [rbx+2B0h], rcx
0x14000a7a8  mov     rcx, [rax+48h]
0x14000a7ac  lock add [rcx+938h], rdi
0x14000a7b4  mov     rdx, rdi
0x14000a7b7  mov     rcx, rbx
0x14000a7ba  call    QuicStreamOnBytesDelivered
0x14000a7bf  movzx   eax, byte ptr [rbx+5Bh]
0x14000a7c3  xor     edi, edi
0x14000a7c5  cmp     [rbx+2B0h], rdi
0x14000a7cc  jnz     short loc_14000A7D5
0x14000a7ce  or      al, 4
0x14000a7d0  mov     [rbx+5Bh], al
0x14000a7d3  jmp     short loc_14000A7E0
0x14000a7d5  test    al, 8
0x14000a7d7  jnz     short loc_14000A7E0
0x14000a7d9  mov     [rbx+2B0h], rdi
0x14000a7e0  test    al, 4
0x14000a7e2  jnz     short loc_14000A810
0x14000a7e4  test    cs:byte_14005C48C, 2
0x14000a7eb  jz      loc_14000AC24
0x14000a7f1  mov     rcx, rbx
0x14000a7f4  call    QuicStreamRecvGetState
0x14000a7f9  mov     r9d, eax
0x14000a7fc  lea     rdx, QuicStreamRecvState
0x14000a803  mov     r8, rbx
0x14000a806  call    McTemplateU0pu_EtwWriteTransfer
0x14000a80b  jmp     loc_14000AC24
0x14000a810  test    al, 40h
0x14000a812  jz      short loc_14000A820
0x14000a814  shr     al, 3
0x14000a817  not     al
0x14000a819  and     al, 1
0x14000a81b  jmp     loc_14000AC26
0x14000a820  mov     rcx, [rbx+280h]
0x14000a827  mov     rdx, [rbx+2A8h]
0x14000a82e  cmp     rcx, rdx
0x14000a831  jnz     loc_14000ABD6
0x14000a837  or      byte ptr [rbx+5Ah], 20h
0x14000a83b  or      al, 1
0x14000a83d  mov     [rbx+5Bh], al
0x14000a840  test    cs:byte_14005C48C, 2
0x14000a847  jz      short loc_14000A863
0x14000a849  mov     rcx, rbx
0x14000a84c  call    QuicStreamRecvGetState
0x14000a851  mov     r9d, eax
0x14000a854  lea     rdx, QuicStreamRecvState
0x14000a85b  mov     r8, rbx
0x14000a85e  call    McTemplateU0pu_EtwWriteTransfer
0x14000a863  test    cs:byte_14005C48D, 1
0x14000a86a  xorps   xmm0, xmm0
0x14000a86d  xorps   xmm1, xmm1
0x14000a870  mov     qword ptr [rsp+130h+var_B8], 3
0x14000a879  movdqu  xmmword ptr [rsp+130h+var_B8+4], xmm0
0x14000a87f  movdqu  [rbp+30h+var_A4], xmm1
0x14000a884  jz      short loc_14000A8BC
0x14000a886  lea     r9, aIndicatingQuic_11; "Indicating QUIC_STREAM_EVENT_PEER_SEND_"...
0x14000a88d  mov     edx, 80h; SizeInBytes
0x14000a892  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000a899  lea     rcx, [rbp+30h+DstBuf]; DstBuf
0x14000a89d  call    cs:__imp__snprintf_s
0x14000a8a4  nop     dword ptr [rax+rax+00h]
0x14000a8a9  lea     r9, [rbp+30h+DstBuf]
0x14000a8ad  mov     r8, rbx
0x14000a8b0  lea     rdx, QuicStreamLogVerbose
0x14000a8b7  call    McTemplateU0ps_EtwWriteTransfer
0x14000a8bc  mov     rax, [rbx+2C8h]
0x14000a8c3  test    rax, rax
0x14000a8c6  jz      short loc_14000A8DB
0x14000a8c8  mov     rdx, [rbx+8]
0x14000a8cc  lea     r8, [rsp+130h+var_B8]
0x14000a8d1  mov     rcx, rbx
0x14000a8d4  call    _guard_dispatch_icall
0x14000a8d9  jmp     short loc_14000A91A
0x14000a8db  test    cs:byte_14005C48C, 40h
0x14000a8e2  jz      short loc_14000A91A
0x14000a8e4  lea     r9, aEventSilentlyD_0; "Event silently discarded"
0x14000a8eb  mov     edx, 80h; SizeInBytes
0x14000a8f0  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000a8f7  lea     rcx, [rbp+30h+DstBuf]; DstBuf
0x14000a8fb  call    cs:__imp__snprintf_s
0x14000a902  nop     dword ptr [rax+rax+00h]
0x14000a907  lea     r9, [rbp+30h+DstBuf]
0x14000a90b  mov     r8, rbx
0x14000a90e  lea     rdx, QuicStreamLogWarning
0x14000a915  call    McTemplateU0ps_EtwWriteTransfer
0x14000a91a  test    byte ptr [rbx+5Ch], 10h
0x14000a91e  jnz     loc_14000AB51
0x14000a924  movzx   ecx, byte ptr [rbx+5Bh]
0x14000a928  test    cl, 40h
0x14000a92b  jnz     loc_14000AB51
0x14000a931  test    byte ptr [rbx+5Ah], 2
0x14000a935  jz      loc_14000AB51
0x14000a93b  test    cl, 1
0x14000a93e  jz      loc_14000AB51
0x14000a944  movzx   ecx, word ptr [rbx+60h]
0x14000a948  test    cx, cx
0x14000a94b  jz      short loc_14000A9BC
0x14000a94d  test    cs:byte_14005C48D, 1
0x14000a954  jz      short loc_14000A993
0x14000a956  movzx   eax, cx
0x14000a959  lea     r9, aRemovingFlagsX; "Removing flags %x"
0x14000a960  lea     rcx, [rbp+30h+DstBuf]; DstBuf
0x14000a964  mov     [rsp+130h+var_110], eax
0x14000a968  mov     edx, 80h; SizeInBytes
0x14000a96d  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000a974  call    cs:__imp__snprintf_s
0x14000a97b  nop     dword ptr [rax+rax+00h]
0x14000a980  lea     r9, [rbp+30h+DstBuf]
0x14000a984  mov     r8, rbx
0x14000a987  lea     rdx, QuicStreamLogVerbose
0x14000a98e  call    McTemplateU0ps_EtwWriteTransfer
0x14000a993  mov     rcx, [rbx+38h]
0x14000a997  mov     [rbx+60h], di
0x14000a99b  test    rcx, rcx
0x14000a99e  jz      short loc_14000A9BC
0x14000a9a0  mov     rax, [rbx+40h]
0x14000a9a4  mov     edx, 2
0x14000a9a9  mov     [rax], rcx
0x14000a9ac  mov     [rcx+8], rax
0x14000a9b0  mov     rcx, rbx
0x14000a9b3  mov     [rbx+38h], rdi
0x14000a9b7  call    QuicStreamRelease
0x14000a9bc  movzx   edx, byte ptr [rbx+5Ch]
0x14000a9c0  movzx   eax, dl
0x14000a9c3  or      al, 10h
0x14000a9c5  mov     [rbx+5Ch], al
0x14000a9c8  test    dl, 4
0x14000a9cb  jnz     loc_14000AB32
0x14000a9d1  mov     rcx, [rbx+48h]
0x14000a9d5  xor     eax, eax
0x14000a9d7  mov     [rsp+130h+var_C0], eax
0x14000a9db  or      dl, 14h
0x14000a9de  mov     [rbx+5Ch], dl
0x14000a9e1  xorps   xmm0, xmm0
0x14000a9e4  movups  [rsp+130h+var_E0], xmm0
0x14000a9e9  movzx   eax, byte ptr [rsp+130h+var_E0+9]
0x14000a9ee  movups  [rsp+130h+var_D0], xmm0
0x14000a9f3  mov     dword ptr [rsp+130h+var_E0], 7
0x14000a9fb  movzx   r9d, byte ptr [rcx+0F8h]
0x14000aa03  and     r9b, 30h
0x14000aa07  setnz   byte ptr [rsp+130h+var_E0+8]
0x14000aa0c  and     al, 0FEh
0x14000aa0e  shr     dl, 3
0x14000aa11  and     dl, 1
0x14000aa14  or      dl, al
0x14000aa16  movzx   eax, byte ptr [rcx+0F8h]
0x14000aa1d  shr     al, 6
0x14000aa20  xor     al, dl
0x14000aa22  and     al, 2
0x14000aa24  xor     al, dl
0x14000aa26  mov     byte ptr [rsp+130h+var_E0+9], al
0x14000aa2a  movzx   r8d, byte ptr [rcx+0F8h]
0x14000aa32  shr     r8b, 3
0x14000aa36  xor     r8b, al
0x14000aa39  and     r8b, 4
0x14000aa3d  xor     r8b, al
0x14000aa40  test    cs:byte_14005C48D, 1
0x14000aa47  mov     byte ptr [rsp+130h+var_E0+9], r8b
0x14000aa4c  mov     r10, [rcx+638h]
0x14000aa53  mov     qword ptr [rsp+130h+var_D0], r10
0x14000aa58  mov     r11d, [rcx+634h]
0x14000aa5f  mov     dword ptr [rsp+130h+var_D0+8], r11d
0x14000aa64  jz      short loc_14000AACD
0x14000aa66  mov     [rsp+130h+var_F0], r11d
0x14000aa6b  mov     eax, edi
0x14000aa6d  movzx   edx, r8b
0x14000aa71  movzx   ecx, r8b
0x14000aa75  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000aa7c  shr     edx, 2
0x14000aa7f  shr     ecx, 1
0x14000aa81  and     edx, 1
0x14000aa84  and     ecx, 1
0x14000aa87  mov     [rsp+130h+var_F8], r10
0x14000aa8c  mov     [rsp+130h+var_100], edx
0x14000aa90  test    r9b, r9b
0x14000aa93  mov     [rsp+130h+var_108], ecx
0x14000aa97  lea     r9, aIndicatingQuic_3; "Indicating QUIC_STREAM_EVENT_SHUTDOWN_C"...
0x14000aa9e  setnz   al
0x14000aaa1  lea     rcx, [rbp+30h+DstBuf]; DstBuf
0x14000aaa5  mov     edx, 80h; SizeInBytes
0x14000aaaa  mov     [rsp+130h+var_110], eax
0x14000aaae  call    cs:__imp__snprintf_s
0x14000aab5  nop     dword ptr [rax+rax+00h]
0x14000aaba  lea     r9, [rbp+30h+DstBuf]
0x14000aabe  mov     r8, rbx
0x14000aac1  lea     rdx, QuicStreamLogVerbose
0x14000aac8  call    McTemplateU0ps_EtwWriteTransfer
0x14000aacd  mov     rax, [rbx+2C8h]
0x14000aad4  test    rax, rax
0x14000aad7  jz      short loc_14000AAEC
0x14000aad9  mov     rdx, [rbx+8]
0x14000aadd  lea     r8, [rsp+130h+var_E0]
0x14000aae2  mov     rcx, rbx
0x14000aae5  call    _guard_dispatch_icall
0x14000aaea  jmp     short loc_14000AB2B
0x14000aaec  test    cs:byte_14005C48C, 40h
0x14000aaf3  jz      short loc_14000AB2B
0x14000aaf5  lea     r9, aEventSilentlyD_0; "Event silently discarded"
0x14000aafc  mov     edx, 80h; SizeInBytes
0x14000ab01  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000ab08  lea     rcx, [rbp+30h+DstBuf]; DstBuf
0x14000ab0c  call    cs:__imp__snprintf_s
0x14000ab13  nop     dword ptr [rax+rax+00h]
0x14000ab18  lea     r9, [rbp+30h+DstBuf]
0x14000ab1c  mov     r8, rbx
0x14000ab1f  lea     rdx, QuicStreamLogWarning
0x14000ab26  call    McTemplateU0ps_EtwWriteTransfer
0x14000ab2b  mov     [rbx+2C8h], rdi
0x14000ab32  test    byte ptr [rbx+5Dh], 2
0x14000ab36  jz      short loc_14000AB3E
0x14000ab38  test    byte ptr [rbx+5Ch], 8
0x14000ab3c  jz      short loc_14000AB51
0x14000ab3e  mov     rcx, [rbx+48h]
0x14000ab42  mov     rdx, rbx
0x14000ab45  add     rcx, 7F0h
0x14000ab4c  call    QuicStreamSetReleaseStream
0x14000ab51  movzx   ecx, word ptr [rbx+60h]
0x14000ab55  test    cl, 0Ah
0x14000ab58  jz      loc_14000AC24
0x14000ab5e  test    cs:byte_14005C48D, 1
0x14000ab65  jz      short loc_14000ABA4
0x14000ab67  and     ecx, 0Ah
0x14000ab6a  lea     r9, aRemovingFlagsX; "Removing flags %x"
0x14000ab71  mov     [rsp+130h+var_110], ecx
0x14000ab75  mov     edx, 80h; SizeInBytes
0x14000ab7a  lea     rcx, [rbp+30h+DstBuf]; DstBuf
0x14000ab7e  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000ab85  call    cs:__imp__snprintf_s
0x14000ab8c  nop     dword ptr [rax+rax+00h]
0x14000ab91  lea     r9, [rbp+30h+DstBuf]
0x14000ab95  mov     r8, rbx
0x14000ab98  lea     rdx, QuicStreamLogVerbose
0x14000ab9f  call    McTemplateU0ps_EtwWriteTransfer
0x14000aba4  mov     eax, 0FFF5h
0x14000aba9  and     [rbx+60h], ax
0x14000abad  jnz     short loc_14000AC24
0x14000abaf  mov     rcx, [rbx+38h]
0x14000abb3  test    rcx, rcx
0x14000abb6  jz      short loc_14000AC24
0x14000abb8  mov     rax, [rbx+40h]
0x14000abbc  mov     edx, 2
0x14000abc1  mov     [rax], rcx
0x14000abc4  mov     [rcx+8], rax
0x14000abc8  mov     rcx, rbx
0x14000abcb  mov     [rbx+38h], rdi
0x14000abcf  call    QuicStreamRelease
0x14000abd4  jmp     short loc_14000AC24
0x14000abd6  cmp     [rbx+59h], dil
0x14000abda  jge     short loc_14000AC24
0x14000abdc  cmp     rcx, rdx
0x14000abdf  jb      short loc_14000AC24
0x14000abe1  test    cs:byte_14005C48C, 2
0x14000abe8  jz      short loc_14000AC04
0x14000abea  mov     rcx, rbx
0x14000abed  call    QuicStreamRecvGetState
0x14000abf2  mov     r9d, eax
0x14000abf5  lea     rdx, QuicStreamRecvState
0x14000abfc  mov     r8, rbx
0x14000abff  call    McTemplateU0pu_EtwWriteTransfer
  ... truncated ...
```
