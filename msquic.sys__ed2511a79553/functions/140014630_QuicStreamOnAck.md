# QuicStreamOnAck

- ea: `0x140014630`
- end: `0x140014d71`
- name: `QuicStreamOnAck`
- size: `1857`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013550`

## callees

- `0x14000a08c`
- `0x14000b1f8`
- `0x14000b32c`
- `0x14000b710`
- `0x1400123c0`
- `0x140014630`
- `0x14001c638`
- `0x140021898`
- `0x140026cb4`
- `0x140029104`
- `0x14002e82c`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ec10`
- `0x1400426e8`
- `0x140045214`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400146a8`
- `ntoskrnl!_snprintf_s` at `0x140014703`
- `ntoskrnl!_snprintf_s` at `0x14001491f`
- `ntoskrnl!_snprintf_s` at `0x14001497d`
- `ntoskrnl!_snprintf_s` at `0x140014a30`
- `ntoskrnl!_snprintf_s` at `0x140014c56`
- `ntoskrnl!_snprintf_s` at `0x140014ccc`
- `ntoskrnl!_snprintf_s` at `0x140014d2a`
- `ntoskrnl!_snprintf_s` at `0x1400146a8`
- `ntoskrnl!_snprintf_s` at `0x140014703`
- `ntoskrnl!_snprintf_s` at `0x14001491f`
- `ntoskrnl!_snprintf_s` at `0x14001497d`
- `ntoskrnl!_snprintf_s` at `0x140014a30`
- `ntoskrnl!_snprintf_s` at `0x140014c56`
- `ntoskrnl!_snprintf_s` at `0x140014ccc`
- `ntoskrnl!_snprintf_s` at `0x140014d2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400149ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400149ae`

## string_xrefs

- `0x140014903`: `Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p]`
- `0x1400146e7`: `Updated sent 0RTT length to %llu`
- `0x140014a19`: `Send queue completely drained`

## pseudocode

```c
__int64 __fastcall QuicStreamOnAck(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // r15
  unsigned __int8 *v4; // r14
  __int64 v5; // r12
  unsigned int v6; // r13d
  char v7; // bl
  unsigned __int64 v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rcx
  char v12; // al
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned int v15; // r8d
  unsigned int v16; // r10d
  __int64 v17; // r9
  unsigned __int64 *v18; // rax
  unsigned __int64 v19; // rax
  __int64 *v20; // r15
  __int64 *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // r14
  __int64 v24; // rcx
  void (__fastcall *v25)(__int64, _QWORD, _OWORD *); // rax
  __int64 v26; // rcx
  __int64 v27; // rsi
  __int64 v28; // rcx
  char v29; // al
  unsigned int State; // eax
  __int64 v31; // rcx
  unsigned __int64 *v32; // rax
  unsigned __int64 v33; // r8
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rdx
  unsigned int v36; // eax
  __int64 v37; // rcx
  __int64 result; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rcx
  unsigned __int64 i; // rcx
  __int64 v43; // rbx
  _QWORD *v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rcx
  char v47[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v48; // [rsp+74h] [rbp-8Ch]
  _OWORD v49[2]; // [rsp+78h] [rbp-88h] BYREF
  int v50; // [rsp+98h] [rbp-68h]
  char DstBuf[128]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  v4 = (unsigned __int8 *)(a3 + 20);
  v5 = *(unsigned __int16 *)(a3 + 16);
  v6 = 0;
  v7 = a2;
  v48 = 0;
  v9 = v3 + v5;
  if ( (byte_14005C48D & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Received ack for %d bytes, offset=%llu, FF=0x%hx", v5, v3, *v4);
    McTemplateU0ps_EtwWriteTransfer(v10, QuicStreamLogVerbose, a1, DstBuf);
  }
  if ( (v7 & 3) == 1 && *(_QWORD *)(a1 + 176) < v9 )
  {
    *(_QWORD *)(a1 + 176) = v9;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Updated sent 0RTT length to %llu", v3 + v5);
      McTemplateU0ps_EtwWriteTransfer(v11, QuicStreamLogVerbose, a1, DstBuf);
    }
  }
  v12 = *(_BYTE *)(a1 + 89);
  if ( (v12 & 2) != 0 )
  {
    v13 = 0;
  }
  else
  {
    v13 = 32;
    *(_BYTE *)(a1 + 89) = v12 | 2;
    v48 = 32;
  }
  if ( (*v4 & 2) != 0 )
  {
    *(_BYTE *)(a1 + 90) |= 4u;
    v13 = (unsigned int)v13 | 0x40;
    v48 = v13;
  }
  v14 = *(_QWORD *)(a1 + 216);
  if ( v3 > v14 )
  {
    v47[0] = 0;
    v32 = (unsigned __int64 *)QuicRangeAddRange((char **)(a1 + 264), v3, v5, v47);
    if ( v32 )
    {
      if ( v47[0] )
      {
        v33 = *(_QWORD *)(a1 + 224);
        if ( v33 >= *v32 )
        {
          v34 = v32[1] + *v32;
          if ( v33 < v34 )
            *(_QWORD *)(a1 + 224) = v34;
        }
        v35 = *(_QWORD *)(a1 + 232);
        if ( v35 >= *v32 )
        {
          v13 = *v32 + v32[1];
          if ( v35 < v13 )
            *(_QWORD *)(a1 + 232) = v13;
        }
      }
    }
    else
    {
      QuicConnCloseLocally(*(_QWORD *)(a1 + 72), 2, 1);
    }
  }
  else
  {
    if ( v14 < v9 )
    {
      *(_QWORD *)(a1 + 216) = v9;
      v15 = 0;
      v16 = *(_DWORD *)(a1 + 272);
      if ( v16 )
      {
        do
        {
          v13 = *(_QWORD *)(a1 + 264) + 16LL * v15;
          a2 = *(_QWORD *)v13;
          if ( *(_QWORD *)v13 >= v9 )
            break;
          v17 = *(_QWORD *)(v13 + 8);
          if ( a2 + v17 - 1 >= v9 )
          {
            *(_QWORD *)v13 = v9;
            *(_QWORD *)(v13 + 8) = a2 + v17 - v9;
            break;
          }
          ++v15;
        }
        while ( v15 < v16 );
        if ( v15 )
          QuicRangeRemoveSubranges(a1 + 264, 0);
      }
      if ( *(_DWORD *)(a1 + 272) )
      {
        v18 = *(unsigned __int64 **)(a1 + 264);
        if ( v18 )
        {
          v13 = *v18;
          if ( *v18 == *(_QWORD *)(a1 + 216) )
          {
            *(_QWORD *)(a1 + 216) = v18[1] + v13;
            QuicRangeRemoveSubranges(a1 + 264, 0);
          }
        }
      }
      v19 = *(_QWORD *)(a1 + 216);
      if ( *(_QWORD *)(a1 + 224) < v19 )
        *(_QWORD *)(a1 + 224) = v19;
      if ( *(_QWORD *)(a1 + 232) < v19 )
        *(_QWORD *)(a1 + 232) = v19;
      if ( *(_QWORD *)(a1 + 240) < v19 )
        *(_BYTE *)(a1 + 90) &= ~8u;
    }
    v20 = (__int64 *)(a1 + 128);
    v21 = *(__int64 **)(a1 + 128);
    if ( v21 )
    {
      do
      {
        if ( (unsigned __int64)(v21[3] + v21[4]) > *(_QWORD *)(a1 + 216) )
          break;
        v22 = *v21;
        *v20 = *v21;
        if ( !v22 )
          *(_QWORD *)(a1 + 136) = v20;
        v23 = *(_QWORD *)(a1 + 72);
        if ( *(__int64 **)(a1 + 144) == v21 )
          *(_QWORD *)(a1 + 144) = *v21;
        if ( *(__int64 **)(a1 + 152) == v21 )
          *(_QWORD *)(a1 + 152) = *v21;
        if ( (*((_DWORD *)v21 + 5) & 2) != 0 && (*(_BYTE *)(a1 + 88) & 4) == 0 )
          QuicStreamIndicateStartComplete(a1, 3221225760LL);
        if ( *((int *)v21 + 5) < 0 )
        {
          v27 = *((unsigned int *)v21 + 10);
          if ( (_DWORD)v27 )
          {
            ExFreePoolWithTag((PVOID)v21[6], 0x32316351u);
            *(_QWORD *)(v23 + 3536) -= v27;
          }
        }
        else
        {
          v49[0] = 0;
          BYTE8(v49[0]) = 0;
          v50 = 0;
          v49[1] = (unsigned __int64)v21[7];
          LODWORD(v49[0]) = 2;
          if ( (byte_14005C48D & 1) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p]", v21);
            McTemplateU0ps_EtwWriteTransfer(v24, QuicStreamLogVerbose, a1, DstBuf);
          }
          v25 = *(void (__fastcall **)(__int64, _QWORD, _OWORD *))(a1 + 712);
          if ( v25 )
          {
            v25(a1, *(_QWORD *)(a1 + 8), v49);
          }
          else if ( (byte_14005C48C & 0x40) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Event silently discarded");
            McTemplateU0ps_EtwWriteTransfer(v26, QuicStreamLogWarning, a1, DstBuf);
          }
        }
        *(_QWORD *)(v23 + 3528) -= v21[4];
        if ( (*(_BYTE *)(v23 + 235) & 1) != 0 )
          QuicSendBufferFill(v23);
        CxPlatPoolFree(v21);
        v21 = (__int64 *)*v20;
      }
      while ( *v20 );
    }
    if ( *(_QWORD *)(a1 + 216) == *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 90) & 4) != 0 )
    {
      if ( (byte_14005C48D & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Send queue completely drained");
        McTemplateU0ps_EtwWriteTransfer(v28, QuicStreamLogVerbose, a1, DstBuf);
      }
      v29 = *(_BYTE *)(a1 + 90);
      if ( (v29 & 2) == 0 )
      {
        *(_BYTE *)(a1 + 90) = v29 | 2;
        if ( (byte_14005C48C & 2) != 0 )
        {
          State = QuicStreamSendGetState(a1);
          McTemplateU0pu_EtwWriteTransfer(v31, QuicStreamSendState, a1, State);
        }
        LOBYTE(a2) = 1;
        QuicStreamIndicateSendShutdownComplete(a1, a2);
        QuicStreamTryCompleteShutdown(a1);
      }
    }
  }
  if ( (*(_BYTE *)(a1 + 90) & 2) == 0
    && (*(_BYTE *)(a1 + 89) & 0x40) != 0
    && *(_QWORD *)(a1 + 216) >= *(_QWORD *)(a1 + 248) )
  {
    if ( (byte_14005C48C & 2) != 0 )
    {
      v36 = QuicStreamSendGetState(a1);
      McTemplateU0pu_EtwWriteTransfer(v37, QuicStreamSendState, a1, v36);
    }
    *(_BYTE *)(a1 + 90) |= 2u;
    QuicSendClearStreamSendFlag(v13, a1, 241);
    QuicStreamCancelRequests(a1);
    QuicStreamIndicateSendShutdownComplete(a1, 0);
    QuicStreamTryCompleteShutdown(a1);
  }
  if ( *(_QWORD *)(a1 + 232) < *(_QWORD *)(a1 + 240) )
  {
    result = v48;
  }
  else
  {
    result = v48;
    if ( *(_QWORD *)(a1 + 224) >= *(_QWORD *)(a1 + 160) )
      result = v48 | 0x10;
  }
  if ( (_DWORD)result )
    result = QuicSendClearStreamSendFlag(v13, a1, (unsigned int)result);
  if ( (byte_14005C48D & 1) != 0 )
  {
    if ( (*(_BYTE *)(a1 + 90) & 8) != 0 )
    {
      v39 = *(_QWORD *)(a1 + 232);
      v40 = *(_QWORD *)(a1 + 240);
    }
    else
    {
      v39 = 0;
      v40 = 0;
    }
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "SF:%hX FC:%llu QS:%llu MAX:%llu UNA:%llu NXT:%llu RECOV:%llu-%llu REL: %llu",
      *(unsigned __int16 *)(a1 + 96),
      *(_QWORD *)(a1 + 184),
      *(_QWORD *)(a1 + 160),
      *(_QWORD *)(a1 + 208),
      *(_QWORD *)(a1 + 216),
      *(_QWORD *)(a1 + 224),
      v39,
      v40,
      *(_QWORD *)(a1 + 248));
    result = McTemplateU0ps_EtwWriteTransfer(v41, QuicStreamLogVerbose, a1, DstBuf);
    for ( i = *(_QWORD *)(a1 + 216); v6 < *(_DWORD *)(a1 + 272); i = *v44 + v44[1] )
    {
      v43 = v6++;
      v44 = (_QWORD *)(*(_QWORD *)(a1 + 264) + 16 * v43);
      if ( !v44 )
        break;
      if ( (byte_14005C48D & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "  unACKed: [%llu, %llu]", i, *v44);
        result = McTemplateU0ps_EtwWriteTransfer(v45, QuicStreamLogVerbose, a1, DstBuf);
      }
    }
    if ( i < *(_QWORD *)(a1 + 208) && (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "  unACKed: [%llu, %llu]", i, *(_QWORD *)(a1 + 208));
      return McTemplateU0ps_EtwWriteTransfer(v46, QuicStreamLogVerbose, a1, DstBuf);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014630  mov     [rsp-8+arg_18], rbx
0x140014635  push    rbp
0x140014636  push    rsi
0x140014637  push    rdi
0x140014638  push    r12
0x14001463a  push    r13
0x14001463c  push    r14
0x14001463e  push    r15
0x140014640  lea     rbp, [rsp-30h]
0x140014645  sub     rsp, 130h
0x14001464c  mov     rax, cs:__security_cookie
0x140014653  xor     rax, rsp
0x140014656  mov     [rbp+60h+var_40], rax
0x14001465a  mov     r15, [r8+8]
0x14001465e  lea     r14, [r8+14h]
0x140014662  movzx   r12d, word ptr [r8+10h]
0x140014667  xor     r13d, r13d
0x14001466a  test    cs:byte_14005C48D, 1
0x140014671  movzx   ebx, dx
0x140014674  mov     rdi, rcx
0x140014677  mov     [rsp+160h+var_EC], r13d
0x14001467c  lea     rsi, [r15+r12]
0x140014680  jz      short loc_1400146C7
0x140014682  movzx   eax, byte ptr [r14]
0x140014686  lea     r9, aReceivedAckFor_0; "Received ack for %d bytes, offset=%llu,"...
0x14001468d  mov     dword ptr [rsp+160h+var_130], eax
0x140014691  lea     r8, [r13-1]; MaxCount
0x140014695  mov     [rsp+160h+var_138], r15
0x14001469a  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x14001469e  mov     edx, 80h; SizeInBytes
0x1400146a3  mov     dword ptr [rsp+160h+var_140], r12d
0x1400146a8  call    cs:__imp__snprintf_s
0x1400146af  nop     dword ptr [rax+rax+00h]
0x1400146b4  lea     r9, [rbp+60h+DstBuf]
0x1400146b8  mov     r8, rdi
0x1400146bb  lea     rdx, QuicStreamLogVerbose
0x1400146c2  call    McTemplateU0ps_EtwWriteTransfer
0x1400146c7  and     bl, 3
0x1400146ca  cmp     bl, 1
0x1400146cd  jnz     short loc_140014722
0x1400146cf  cmp     [rdi+0B0h], rsi
0x1400146d6  jnb     short loc_140014722
0x1400146d8  mov     [rdi+0B0h], rsi
0x1400146df  test    cs:byte_14005C48D, bl
0x1400146e5  jz      short loc_140014722
0x1400146e7  lea     r9, aUpdatedSent0rt; "Updated sent 0RTT length to %llu"
0x1400146ee  mov     [rsp+160h+var_140], rsi
0x1400146f3  mov     edx, 80h; SizeInBytes
0x1400146f8  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x1400146fc  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140014703  call    cs:__imp__snprintf_s
0x14001470a  nop     dword ptr [rax+rax+00h]
0x14001470f  lea     r9, [rbp+60h+DstBuf]
0x140014713  mov     r8, rdi
0x140014716  lea     rdx, QuicStreamLogVerbose
0x14001471d  call    McTemplateU0ps_EtwWriteTransfer
0x140014722  movzx   eax, byte ptr [rdi+59h]
0x140014726  test    al, 2
0x140014728  jnz     short loc_14001473A
0x14001472a  or      al, 2
0x14001472c  mov     ecx, 20h ; ' '
0x140014731  mov     [rdi+59h], al
0x140014734  mov     [rsp+160h+var_EC], ecx
0x140014738  jmp     short loc_14001473D
0x14001473a  mov     ecx, r13d
0x14001473d  test    byte ptr [r14], 2
0x140014741  jz      short loc_14001474E
0x140014743  or      byte ptr [rdi+5Ah], 4
0x140014747  or      ecx, 40h
0x14001474a  mov     [rsp+160h+var_EC], ecx
0x14001474e  mov     rax, [rdi+0D8h]
0x140014755  cmp     r15, rax
0x140014758  ja      loc_140014A97
0x14001475e  cmp     rax, rsi
0x140014761  jnb     loc_14001484E
0x140014767  mov     [rdi+0D8h], rsi
0x14001476e  mov     r8d, r13d
0x140014771  mov     r10d, [rdi+110h]
0x140014778  test    r10d, r10d
0x14001477b  jz      short loc_1400147DC
0x14001477d  mov     r11, [rdi+108h]
0x140014784  nop     dword ptr [rax+00h]
0x140014788  nop     dword ptr [rax+rax+00000000h]
0x140014790  mov     ecx, r8d
0x140014793  shl     rcx, 4
0x140014797  add     rcx, r11
0x14001479a  mov     rdx, [rcx]
0x14001479d  cmp     rdx, rsi
0x1400147a0  jnb     short loc_1400147C9
0x1400147a2  mov     r9, [rcx+8]
0x1400147a6  lea     rax, [r9-1]
0x1400147aa  add     rax, rdx
0x1400147ad  cmp     rax, rsi
0x1400147b0  jnb     short loc_1400147BC
0x1400147b2  inc     r8d
0x1400147b5  cmp     r8d, r10d
0x1400147b8  jb      short loc_140014790
0x1400147ba  jmp     short loc_1400147C9
0x1400147bc  sub     r9, rsi
0x1400147bf  mov     [rcx], rsi
0x1400147c2  add     r9, rdx
0x1400147c5  mov     [rcx+8], r9
0x1400147c9  test    r8d, r8d
0x1400147cc  jz      short loc_1400147DC
0x1400147ce  xor     edx, edx
0x1400147d0  lea     rcx, [rdi+108h]
0x1400147d7  call    QuicRangeRemoveSubranges
0x1400147dc  cmp     [rdi+110h], r13d
0x1400147e3  jbe     short loc_14001481A
0x1400147e5  mov     rax, [rdi+108h]
0x1400147ec  test    rax, rax
0x1400147ef  jz      short loc_14001481A
0x1400147f1  mov     rcx, [rax]
0x1400147f4  cmp     rcx, [rdi+0D8h]
0x1400147fb  jnz     short loc_14001481A
0x1400147fd  add     rcx, [rax+8]
0x140014801  xor     edx, edx
0x140014803  mov     [rdi+0D8h], rcx
0x14001480a  lea     rcx, [rdi+108h]
0x140014811  lea     r8d, [rdx+1]
0x140014815  call    QuicRangeRemoveSubranges
0x14001481a  mov     rax, [rdi+0D8h]
0x140014821  cmp     [rdi+0E0h], rax
0x140014828  jnb     short loc_140014831
0x14001482a  mov     [rdi+0E0h], rax
0x140014831  cmp     [rdi+0E8h], rax
0x140014838  jnb     short loc_140014841
0x14001483a  mov     [rdi+0E8h], rax
0x140014841  cmp     [rdi+0F0h], rax
0x140014848  jnb     short loc_14001484E
0x14001484a  and     byte ptr [rdi+5Ah], 0F7h
0x14001484e  lea     r15, [rdi+80h]
0x140014855  mov     rbx, [r15]
0x140014858  test    rbx, rbx
0x14001485b  jz      loc_1400149F2
0x140014861  mov     rax, [rbx+20h]
0x140014865  add     rax, [rbx+18h]
0x140014869  cmp     rax, [rdi+0D8h]
0x140014870  ja      loc_1400149F2
0x140014876  mov     rax, [rbx]
0x140014879  mov     [r15], rax
0x14001487c  test    rax, rax
0x14001487f  jnz     short loc_140014888
0x140014881  mov     [rdi+88h], r15
0x140014888  mov     r14, [rdi+48h]
0x14001488c  cmp     [rdi+90h], rbx
0x140014893  jnz     short loc_14001489F
0x140014895  mov     rax, [rbx]
0x140014898  mov     [rdi+90h], rax
0x14001489f  cmp     [rdi+98h], rbx
0x1400148a6  jnz     short loc_1400148B2
0x1400148a8  mov     rax, [rbx]
0x1400148ab  mov     [rdi+98h], rax
0x1400148b2  mov     eax, [rbx+14h]
0x1400148b5  test    al, 2
0x1400148b7  jz      short loc_1400148CC
0x1400148b9  test    byte ptr [rdi+58h], 4
0x1400148bd  jnz     short loc_1400148CC
0x1400148bf  mov     edx, 0C0000120h
0x1400148c4  mov     rcx, rdi
0x1400148c7  call    QuicStreamIndicateStartComplete
0x1400148cc  cmp     [rbx+14h], r13d
0x1400148d0  jl      loc_14001499E
0x1400148d6  xor     eax, eax
0x1400148d8  xorps   xmm0, xmm0
0x1400148db  test    cs:byte_14005C48D, 1
0x1400148e2  movups  [rsp+160h+var_E8], xmm0
0x1400148e7  mov     byte ptr [rbp+60h+var_E8+8], al
0x1400148ea  mov     [rbp+60h+var_C8], eax
0x1400148ed  mov     rax, [rbx+38h]
0x1400148f1  movups  [rbp+60h+var_D8], xmm0
0x1400148f5  mov     qword ptr [rbp+60h+var_D8], rax
0x1400148f9  mov     dword ptr [rsp+160h+var_E8], 2
0x140014901  jz      short loc_14001493E
0x140014903  lea     r9, aIndicatingQuic_23; "Indicating QUIC_STREAM_EVENT_SEND_COMPL"...
0x14001490a  mov     [rsp+160h+var_140], rbx
0x14001490f  mov     edx, 80h; SizeInBytes
0x140014914  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x140014918  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001491f  call    cs:__imp__snprintf_s
0x140014926  nop     dword ptr [rax+rax+00h]
0x14001492b  lea     r9, [rbp+60h+DstBuf]
0x14001492f  mov     r8, rdi
0x140014932  lea     rdx, QuicStreamLogVerbose
0x140014939  call    McTemplateU0ps_EtwWriteTransfer
0x14001493e  mov     rax, [rdi+2C8h]
0x140014945  test    rax, rax
0x140014948  jz      short loc_14001495D
0x14001494a  mov     rdx, [rdi+8]
0x14001494e  lea     r8, [rsp+160h+var_E8]
0x140014953  mov     rcx, rdi
0x140014956  call    _guard_dispatch_icall
0x14001495b  jmp     short loc_1400149C1
0x14001495d  test    cs:byte_14005C48C, 40h
0x140014964  jz      short loc_1400149C1
0x140014966  lea     r9, aEventSilentlyD_0; "Event silently discarded"
0x14001496d  mov     edx, 80h; SizeInBytes
0x140014972  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140014979  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x14001497d  call    cs:__imp__snprintf_s
0x140014984  nop     dword ptr [rax+rax+00h]
0x140014989  lea     r9, [rbp+60h+DstBuf]
0x14001498d  mov     r8, rdi
0x140014990  lea     rdx, QuicStreamLogWarning
0x140014997  call    McTemplateU0ps_EtwWriteTransfer
0x14001499c  jmp     short loc_1400149C1
0x14001499e  mov     esi, [rbx+28h]
0x1400149a1  test    esi, esi
0x1400149a3  jz      short loc_1400149C1
0x1400149a5  mov     rcx, [rbx+30h]; P
0x1400149a9  mov     edx, 32316351h; Tag
0x1400149ae  call    cs:__imp_ExFreePoolWithTag
0x1400149b5  nop     dword ptr [rax+rax+00h]
0x1400149ba  sub     [r14+0DD0h], rsi
0x1400149c1  mov     rax, [rbx+20h]
0x1400149c5  sub     [r14+0DC8h], rax
0x1400149cc  test    byte ptr [r14+0EBh], 1
0x1400149d4  jz      short loc_1400149DE
0x1400149d6  mov     rcx, r14
0x1400149d9  call    QuicSendBufferFill
0x1400149de  mov     rcx, rbx
0x1400149e1  call    CxPlatPoolFree
0x1400149e6  mov     rbx, [r15]
0x1400149e9  test    rbx, rbx
0x1400149ec  jnz     loc_140014861
0x1400149f2  mov     rax, [rdi+0A0h]
0x1400149f9  cmp     [rdi+0D8h], rax
0x140014a00  jnz     loc_140014B15
0x140014a06  test    byte ptr [rdi+5Ah], 4
0x140014a0a  jz      loc_140014B15
0x140014a10  test    cs:byte_14005C48D, 1
0x140014a17  jz      short loc_140014A4F
0x140014a19  lea     r9, aSendQueueCompl; "Send queue completely drained"
0x140014a20  mov     edx, 80h; SizeInBytes
0x140014a25  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140014a2c  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x140014a30  call    cs:__imp__snprintf_s
0x140014a37  nop     dword ptr [rax+rax+00h]
0x140014a3c  lea     r9, [rbp+60h+DstBuf]
0x140014a40  mov     r8, rdi
0x140014a43  lea     rdx, QuicStreamLogVerbose
0x140014a4a  call    McTemplateU0ps_EtwWriteTransfer
0x140014a4f  movzx   eax, byte ptr [rdi+5Ah]
0x140014a53  test    al, 2
0x140014a55  jnz     loc_140014B15
0x140014a5b  or      al, 2
0x140014a5d  mov     [rdi+5Ah], al
0x140014a60  test    cs:byte_14005C48C, 2
0x140014a67  jz      short loc_140014A83
0x140014a69  mov     rcx, rdi
0x140014a6c  call    QuicStreamSendGetState
0x140014a71  mov     r9d, eax
0x140014a74  lea     rdx, QuicStreamSendState
0x140014a7b  mov     r8, rdi
0x140014a7e  call    McTemplateU0pu_EtwWriteTransfer
0x140014a83  mov     dl, 1
0x140014a85  mov     rcx, rdi
0x140014a88  call    QuicStreamIndicateSendShutdownComplete
0x140014a8d  mov     rcx, rdi
0x140014a90  call    QuicStreamTryCompleteShutdown
0x140014a95  jmp     short loc_140014B15
0x140014a97  mov     r8, r12
0x140014a9a  mov     [rsp+160h+var_F0], r13b
0x140014a9f  lea     rcx, [rdi+108h]
0x140014aa6  mov     rdx, r15
0x140014aa9  lea     r9, [rsp+160h+var_F0]
0x140014aae  call    QuicRangeAddRange
0x140014ab3  test    rax, rax
0x140014ab6  jnz     short loc_140014ACD
0x140014ab8  mov     rcx, [rdi+48h]
0x140014abc  lea     edx, [rax+2]
0x140014abf  xor     r9d, r9d
0x140014ac2  lea     r8d, [rax+1]
0x140014ac6  call    QuicConnCloseLocally
0x140014acb  jmp     short loc_140014B15
0x140014acd  cmp     [rsp+160h+var_F0], r13b
0x140014ad2  jz      short loc_140014B15
0x140014ad4  mov     r8, [rdi+0E0h]
0x140014adb  mov     rdx, [rax]
0x140014ade  cmp     r8, rdx
0x140014ae1  jb      short loc_140014AF3
0x140014ae3  add     rdx, [rax+8]
0x140014ae7  cmp     r8, rdx
0x140014aea  jnb     short loc_140014AF3
0x140014aec  mov     [rdi+0E0h], rdx
0x140014af3  mov     rdx, [rdi+0E8h]
0x140014afa  mov     r8, [rax]
0x140014afd  cmp     rdx, r8
0x140014b00  jb      short loc_140014B15
0x140014b02  mov     rcx, [rax+8]
0x140014b06  add     rcx, r8
0x140014b09  cmp     rdx, rcx
0x140014b0c  jnb     short loc_140014B15
0x140014b0e  mov     [rdi+0E8h], rcx
0x140014b15  test    byte ptr [rdi+5Ah], 2
0x140014b19  jnz     short loc_140014B80
0x140014b1b  test    byte ptr [rdi+59h], 40h
0x140014b1f  jz      short loc_140014B80
0x140014b21  mov     rax, [rdi+0F8h]
0x140014b28  cmp     [rdi+0D8h], rax
  ... truncated ...
```
