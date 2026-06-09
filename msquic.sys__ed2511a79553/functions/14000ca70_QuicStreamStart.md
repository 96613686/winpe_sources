# QuicStreamStart

- ea: `0x14000ca70`
- end: `0x14000d09f`
- name: `QuicStreamStart`
- size: `1583`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14000c774`
- `0x14000d0b0`
- `0x140010440`

## callees

- `0x14000b2e8`
- `0x14000b60c`
- `0x14000c500`
- `0x14000c5b0`
- `0x14000c718`
- `0x14000ca70`
- `0x14000d230`
- `0x14000d490`
- `0x140010820`
- `0x140022dfc`
- `0x1400290b4`
- `0x14002974c`
- `0x14002f644`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003e884`
- `0x14003ec10`
- `0x14003fd84`
- `0x1400426e8`
- `0x140044c28`
- `0x1400451c4`
- `0x140045214`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000cfd6`
- `ntoskrnl!_snprintf_s` at `0x14000d036`
- `ntoskrnl!_snprintf_s` at `0x14000cfd6`
- `ntoskrnl!_snprintf_s` at `0x14000d036`

## string_xrefs

- `0x14000cfb1`: `Indicating QUIC_STREAM_EVENT_START_COMPLETE [Status=0x%x ID=%llu Accepted=%hhu]`

## pseudocode

```c
__int64 __fastcall QuicStreamStart(__int64 a1, char a2, char a3)
{
  __int64 v3; // r9
  char v7; // al
  char v8; // r8
  __int64 v9; // rsi
  unsigned __int8 v10; // cl
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdi
  bool v17; // zf
  __int64 v18; // rdx
  int v19; // edi
  __int64 *i; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  _QWORD *v28; // r9
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // rcx
  unsigned int State; // eax
  __int64 v42; // rcx
  unsigned int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  _BYTE *v46; // rsi
  __int64 *v47; // rdx
  __int64 *v48; // rax
  __int64 v49; // rax
  _BYTE *v50; // rbp
  PSLIST_ENTRY v51; // rax
  __int64 v52; // rcx
  PSLIST_ENTRY v53; // r14
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  char v58; // al
  __int64 v59; // rdx
  bool v60; // al
  char v61; // cl
  __int64 v62; // rcx
  void (__fastcall *v63)(__int64, _QWORD, __int64 *); // rax
  __int64 v64; // rcx
  __int64 v66; // [rsp+40h] [rbp-E8h] BYREF
  int v67; // [rsp+48h] [rbp-E0h]
  int v68; // [rsp+4Ch] [rbp-DCh]
  __int64 v69; // [rsp+50h] [rbp-D8h]
  __int64 v70; // [rsp+58h] [rbp-D0h]
  int v71; // [rsp+60h] [rbp-C8h]
  char DstBuf[128]; // [rsp+70h] [rbp-B8h] BYREF

  v3 = *(_QWORD *)(a1 + 72);
  v7 = *(_BYTE *)(v3 + 248);
  if ( (v7 & 0x10) != 0 )
  {
LABEL_78:
    v19 = -1073741436;
    goto LABEL_79;
  }
  if ( (v7 & 0x20) != 0 || (v8 = *(_BYTE *)(a1 + 88), (v8 & 4) != 0) )
  {
    v19 = -1073741536;
    if ( (*(_BYTE *)(a1 + 88) & 4) == 0 )
      goto LABEL_79;
    goto LABEL_78;
  }
  if ( a3 )
    goto LABEL_28;
  v9 = v3 + 2032;
  v10 = (*(_DWORD *)v3 == 4) | 2;
  if ( (v8 & 0x20) == 0 )
    v10 = *(_DWORD *)v3 == 4;
  v11 = v10;
  v12 = 3LL * v10;
  v13 = *(_QWORD *)(v9 + 24LL * v10);
  v14 = v9 + 8 * v12;
  v15 = *(_QWORD *)(v14 + 8);
  v16 = v11 + 4 * v15;
  if ( (a2 & 2) != 0 )
  {
    if ( v15 >= v13 )
    {
      if ( (*(_BYTE *)(v3 + 250) & 0x20) != 0 )
      {
        v17 = (v11 & 2) == 0;
        v18 = 0x20000;
        if ( v17 )
          v18 = 0x10000;
        QuicSendSetSendFlag(v3 + 3416, v18);
      }
      v19 = -1071382520;
      goto LABEL_80;
    }
    *(_QWORD *)(a1 + 80) = v16;
  }
  else
  {
    *(_QWORD *)(a1 + 80) = v16;
    if ( v15 >= v13 )
    {
      if ( !(unsigned __int8)QuicStreamSetLazyInitStreamTable(v3 + 2032) )
      {
        *(_QWORD *)(a1 + 80) = -1;
        v19 = -1073741801;
        goto LABEL_80;
      }
      for ( i = *(__int64 **)(v9 + 112); i != (__int64 *)(v9 + 104); i = (__int64 *)i[1] )
      {
        if ( i[6] < v16 )
          break;
      }
      v21 = *i;
      *i = a1 + 32;
      *(_QWORD *)(a1 + 32) = v21;
      *(_QWORD *)(a1 + 40) = i;
      *(_QWORD *)(v21 + 8) = a1 + 32;
      *(_BYTE *)(a1 + 93) |= 1u;
      *(_BYTE *)(a1 + 98) |= 0x20u;
      v22 = QuicTimePlat();
      v23 = QuicTimePlatToUs64(v22);
      v24 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 848) = v23;
      if ( (*(_BYTE *)(v24 + 250) & 0x20) != 0 )
      {
        v25 = 0x20000;
        if ( (*(_BYTE *)(a1 + 80) & 2) == 0 )
          v25 = 0x10000;
        QuicSendSetSendFlag(v24 + 3416, v25);
      }
      goto LABEL_27;
    }
  }
  if ( (unsigned __int8)QuicStreamSetInsertStream(v3 + 2032, a1) )
  {
LABEL_27:
    ++*(_WORD *)(v14 + 18);
    ++*(_QWORD *)(v14 + 8);
    CxPlatRefIncrement(a1 + 16);
LABEL_28:
    v19 = 0;
    *(_BYTE *)(a1 + 88) = *(_BYTE *)(a1 + 88) & 0x7B | (16 * (a2 & 0xF8)) | 4;
    v26 = QuicTimePlat();
    v27 = QuicTimePlatToUs64(v26);
    v28 = *(_QWORD **)(a1 + 72);
    v29 = v27;
    v30 = v28[488];
    v31 = v27 - v30;
    if ( !v30 )
      v31 = 0;
    *(_QWORD *)(a1 + 888) = v28[487] + v31;
    v32 = v28[490];
    if ( v32 )
      v33 = v29 - v32;
    else
      v33 = 0;
    *(_QWORD *)(a1 + 896) = v28[489] + v33;
    v34 = v28[492];
    if ( v34 )
      v35 = v29 - v34;
    else
      v35 = 0;
    *(_QWORD *)(a1 + 904) = v28[491] + v35;
    v36 = v28[494];
    if ( v36 )
      v37 = v29 - v36;
    else
      v37 = 0;
    *(_QWORD *)(a1 + 912) = v28[493] + v37;
    v38 = v28[496];
    if ( v38 )
      v39 = v29 - v38;
    else
      v39 = 0;
    v40 = v39 + v28[495];
    *(_QWORD *)(a1 + 920) = v40;
    if ( (byte_14005C48C & 2) != 0 )
    {
      McTemplateU0ppxu_EtwWriteTransfer(
        v40,
        (unsigned int)QuicStreamCreated,
        a1,
        (_DWORD)v28,
        *(_QWORD *)(a1 + 80),
        a3 == 0);
      if ( (byte_14005C48C & 2) != 0 )
      {
        State = QuicStreamSendGetState(a1);
        McTemplateU0pu_EtwWriteTransfer(v42, QuicStreamSendState, a1, State);
        if ( (byte_14005C48C & 2) != 0 )
        {
          v43 = QuicStreamRecvGetState(a1);
          McTemplateU0pu_EtwWriteTransfer(v44, QuicStreamRecvState, a1, v43);
        }
      }
    }
    if ( (*(_BYTE *)(a1 + 91) & 2) != 0 )
      QuicStreamAddOutFlowBlockedReason(a1, 128);
    if ( *(_WORD *)(a1 + 96) )
    {
      v45 = *(_QWORD *)(a1 + 72);
      v46 = (_BYTE *)(v45 + 3416);
      if ( !*(_QWORD *)(a1 + 56) )
      {
        v47 = *(__int64 **)(v45 + 3504);
        v48 = (__int64 *)(v45 + 3496);
        if ( v47 != (__int64 *)(v46 + 80) )
        {
          do
          {
            if ( *(_WORD *)(a1 + 416) <= *((_WORD *)v47 + 180) )
              break;
            v47 = (__int64 *)v47[1];
          }
          while ( v47 != v48 );
        }
        v49 = *v47;
        *(_QWORD *)(a1 + 56) = *v47;
        *(_QWORD *)(a1 + 64) = v47;
        *(_QWORD *)(v49 + 8) = a1 + 56;
        *v47 = a1 + 56;
        CxPlatRefIncrement(a1 + 16);
        v45 = *(_QWORD *)(a1 + 72);
      }
      if ( (*(_BYTE *)(v45 + 248) & 4) != 0 )
      {
        *(_BYTE *)(a1 + 91) &= ~0x80u;
        v50 = v46 - 3416;
        if ( (*v46 & 1) == 0 )
        {
          if ( (unsigned __int8)QuicSendCanSendFlagsNow(v46) )
          {
            v51 = CxPlatPoolAlloc(*((_QWORD *)v50 + 9) + 2016LL);
            v53 = v51;
            if ( v51 )
            {
              LODWORD(v51[1].Next) = 4;
              BYTE4(v51[1].Next) = 1;
              *v46 |= 1u;
              if ( (byte_14005C48A & 1) != 0 )
                McTemplateU0pq_EtwWriteTransfer(v52, QuicConnQueueSendFlush, v46 - 3416, 1);
              if ( (unsigned __int8)QuicOperationEnqueue(v50 + 1424, *((_QWORD *)v50 + 9), v53) )
                QuicWorkerQueueConnection(*((_QWORD *)v50 + 8), v46 - 3416);
            }
          }
        }
      }
    }
    *(_BYTE *)(a1 + 89) = a2 & 1 | *(_BYTE *)(a1 + 89) & 0xFE;
    if ( (a2 & 1) != 0 )
      QuicSendSetStreamSendFlag(*(_QWORD *)(a1 + 72) + 3416LL, a1, 32);
    v54 = *(_QWORD *)(a1 + 72);
    if ( (*(_QWORD *)(a1 + 80) & 2) != 0 )
    {
      v55 = *(_QWORD *)(v54 + 1656);
LABEL_72:
      *(_QWORD *)(a1 + 184) = v55;
      if ( !v55 )
        QuicStreamAddOutFlowBlockedReason(a1, 64);
      LODWORD(v57) = -1;
      if ( *(_QWORD *)(a1 + 184) < 0xFFFFFFFF )
        v57 = *(_QWORD *)(a1 + 184);
      *(_DWORD *)(a1 + 192) = v57;
LABEL_79:
      if ( a3 )
        return (unsigned int)v19;
      goto LABEL_80;
    }
    v56 = *(_QWORD *)(a1 + 80) & 1LL;
    if ( *(_DWORD *)v54 == 4 )
    {
      if ( v56 )
      {
        v55 = *(_QWORD *)(v54 + 1648);
        goto LABEL_72;
      }
    }
    else if ( !v56 )
    {
      v55 = *(_QWORD *)(v54 + 1648);
      goto LABEL_72;
    }
    v55 = *(_QWORD *)(v54 + 1640);
    goto LABEL_72;
  }
  *(_QWORD *)(a1 + 80) = -1;
  v19 = -1073741801;
LABEL_80:
  v58 = *(_BYTE *)(a1 + 88);
  if ( (v58 & 8) == 0 )
  {
    v59 = *(_QWORD *)(a1 + 80);
    *(_BYTE *)(a1 + 88) = v58 | 8;
    v60 = 0;
    v66 = 0;
    v68 = 0;
    v70 = 0;
    v71 = 0;
    v67 = v19;
    v69 = v59;
    if ( v19 >= 0 )
      v60 = (*(_BYTE *)(a1 + 98) & 0x20) == 0;
    v61 = v60 | v70 & 0xFE;
    LOBYTE(v70) = v61;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Indicating QUIC_STREAM_EVENT_START_COMPLETE [Status=0x%x ID=%llu Accepted=%hhu]",
        v19,
        v59,
        v61 & 1);
      McTemplateU0ps_EtwWriteTransfer(v62, QuicStreamLogVerbose, a1, DstBuf);
    }
    v63 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(a1 + 712);
    if ( v63 )
    {
      v63(a1, *(_QWORD *)(a1 + 8), &v66);
    }
    else if ( (byte_14005C48C & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Event silently discarded");
      McTemplateU0ps_EtwWriteTransfer(v64, QuicStreamLogWarning, a1, DstBuf);
    }
  }
  if ( v19 < 0 && (a2 & 4) != 0 )
    QuicStreamShutdown(a1, 14);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000ca70  mov     [rsp+arg_10], rbx
0x14000ca75  mov     [rsp+arg_18], rsi
0x14000ca7a  push    rdi
0x14000ca7b  push    r12
0x14000ca7d  push    r13
0x14000ca7f  push    r14
0x14000ca81  push    r15
0x14000ca83  sub     rsp, 100h
0x14000ca8a  mov     rax, cs:__security_cookie
0x14000ca91  xor     rax, rsp
0x14000ca94  mov     [rsp+128h+var_38], rax
0x14000ca9c  mov     r9, [rcx+48h]
0x14000caa0  xor     r13d, r13d
0x14000caa3  movzx   r15d, r8b
0x14000caa7  mov     r12d, edx
0x14000caaa  mov     rbx, rcx
0x14000caad  movzx   eax, byte ptr [r9+0F8h]
0x14000cab5  test    al, 10h
0x14000cab7  jnz     loc_14000CF49
0x14000cabd  test    al, 20h
0x14000cabf  jnz     loc_14000CF3E
0x14000cac5  movzx   r8d, byte ptr [rcx+58h]
0x14000caca  test    r8b, 4
0x14000cace  jnz     loc_14000CF3E
0x14000cad4  test    r15b, r15b
0x14000cad7  jnz     loc_14000CC2C
0x14000cadd  cmp     dword ptr [r9], 4
0x14000cae1  lea     rsi, [r9+7F0h]
0x14000cae8  setz    dl
0x14000caeb  movzx   eax, dl
0x14000caee  or      al, 2
0x14000caf0  movzx   ecx, al
0x14000caf3  test    r8b, 20h
0x14000caf7  movzx   eax, dl
0x14000cafa  cmovz   ecx, eax
0x14000cafd  movzx   edx, cl
0x14000cb00  lea     rax, [rdx+rdx*2]
0x14000cb04  mov     rcx, [rsi+rax*8]
0x14000cb08  lea     r14, [rsi+rax*8]
0x14000cb0c  mov     rax, [rsi+rax*8+8]
0x14000cb11  lea     rdi, [rdx+rax*4]
0x14000cb15  test    r12b, 2
0x14000cb19  jz      short loc_14000CB56
0x14000cb1b  cmp     rax, rcx
0x14000cb1e  jb      short loc_14000CB50
0x14000cb20  test    byte ptr [r9+0FAh], 20h
0x14000cb28  jz      short loc_14000CB46
0x14000cb2a  test    dl, 2
0x14000cb2d  lea     rcx, [r9+0D58h]
0x14000cb34  mov     edx, 20000h
0x14000cb39  mov     eax, 10000h
0x14000cb3e  cmovz   edx, eax
0x14000cb41  call    QuicSendSetSendFlag
0x14000cb46  mov     edi, 0C0240008h
0x14000cb4b  jmp     loc_14000CF57
0x14000cb50  mov     [rbx+50h], rdi
0x14000cb54  jmp     short loc_14000CB5F
0x14000cb56  mov     [rbx+50h], rdi
0x14000cb5a  cmp     rax, rcx
0x14000cb5d  jnb     short loc_14000CB84
0x14000cb5f  mov     rdx, rbx
0x14000cb62  mov     rcx, rsi
0x14000cb65  call    QuicStreamSetInsertStream
0x14000cb6a  test    al, al
0x14000cb6c  jnz     loc_14000CC1A
0x14000cb72  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x14000cb7a  mov     edi, 0C0000017h
0x14000cb7f  jmp     loc_14000CF57
0x14000cb84  mov     rcx, rsi
0x14000cb87  call    QuicStreamSetLazyInitStreamTable
0x14000cb8c  test    al, al
0x14000cb8e  jnz     short loc_14000CBA2
0x14000cb90  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x14000cb98  mov     edi, 0C0000017h
0x14000cb9d  jmp     loc_14000CF57
0x14000cba2  mov     rdx, [rsi+70h]
0x14000cba6  lea     rax, [rsi+68h]
0x14000cbaa  cmp     rdx, rax
0x14000cbad  jz      short loc_14000CBBF
0x14000cbaf  nop
0x14000cbb0  cmp     [rdx+30h], rdi
0x14000cbb4  jb      short loc_14000CBBF
0x14000cbb6  mov     rdx, [rdx+8]
0x14000cbba  cmp     rdx, rax
0x14000cbbd  jnz     short loc_14000CBB0
0x14000cbbf  mov     rax, [rdx]
0x14000cbc2  lea     rcx, [rbx+20h]
0x14000cbc6  mov     [rdx], rcx
0x14000cbc9  mov     [rcx], rax
0x14000cbcc  mov     [rcx+8], rdx
0x14000cbd0  mov     [rax+8], rcx
0x14000cbd4  or      byte ptr [rbx+5Dh], 1
0x14000cbd8  or      byte ptr [rbx+62h], 20h
0x14000cbdc  call    QuicTimePlat
0x14000cbe1  mov     rcx, rax
0x14000cbe4  call    QuicTimePlatToUs64
0x14000cbe9  mov     rcx, [rbx+48h]
0x14000cbed  mov     [rbx+350h], rax
0x14000cbf4  test    byte ptr [rcx+0FAh], 20h
0x14000cbfb  jz      short loc_14000CC1A
0x14000cbfd  test    byte ptr [rbx+50h], 2
0x14000cc01  mov     edx, 20000h
0x14000cc06  mov     eax, 10000h
0x14000cc0b  cmovz   edx, eax
0x14000cc0e  add     rcx, 0D58h
0x14000cc15  call    QuicSendSetSendFlag
0x14000cc1a  inc     word ptr [r14+12h]
0x14000cc1f  lea     rcx, [rbx+10h]
0x14000cc23  inc     qword ptr [r14+8]
0x14000cc27  call    CxPlatRefIncrement
0x14000cc2c  movzx   eax, byte ptr [rbx+58h]
0x14000cc30  movzx   ecx, r12b
0x14000cc34  and     cl, 0F8h
0x14000cc37  and     al, 7Bh
0x14000cc39  shl     cl, 4
0x14000cc3c  mov     edi, r13d
0x14000cc3f  or      cl, al
0x14000cc41  or      cl, 4
0x14000cc44  mov     [rbx+58h], cl
0x14000cc47  call    QuicTimePlat
0x14000cc4c  mov     rcx, rax
0x14000cc4f  call    QuicTimePlatToUs64
0x14000cc54  mov     r9, [rbx+48h]
0x14000cc58  mov     rdx, rax
0x14000cc5b  mov     r8, rax
0x14000cc5e  mov     rcx, [r9+0F40h]
0x14000cc65  sub     rdx, rcx
0x14000cc68  test    rcx, rcx
0x14000cc6b  cmovz   rdx, r13
0x14000cc6f  add     rdx, [r9+0F38h]
0x14000cc76  mov     [rbx+378h], rdx
0x14000cc7d  mov     rax, [r9+0F50h]
0x14000cc84  test    rax, rax
0x14000cc87  jz      short loc_14000CC91
0x14000cc89  mov     rcx, r8
0x14000cc8c  sub     rcx, rax
0x14000cc8f  jmp     short loc_14000CC94
0x14000cc91  mov     rcx, r13
0x14000cc94  add     rcx, [r9+0F48h]
0x14000cc9b  mov     [rbx+380h], rcx
0x14000cca2  mov     rax, [r9+0F60h]
0x14000cca9  test    rax, rax
0x14000ccac  jz      short loc_14000CCB6
0x14000ccae  mov     rcx, r8
0x14000ccb1  sub     rcx, rax
0x14000ccb4  jmp     short loc_14000CCB9
0x14000ccb6  mov     rcx, r13
0x14000ccb9  add     rcx, [r9+0F58h]
0x14000ccc0  mov     [rbx+388h], rcx
0x14000ccc7  mov     rax, [r9+0F70h]
0x14000ccce  test    rax, rax
0x14000ccd1  jz      short loc_14000CCDB
0x14000ccd3  mov     rcx, r8
0x14000ccd6  sub     rcx, rax
0x14000ccd9  jmp     short loc_14000CCDE
0x14000ccdb  mov     rcx, r13
0x14000ccde  add     rcx, [r9+0F68h]
0x14000cce5  mov     [rbx+390h], rcx
0x14000ccec  mov     rax, [r9+0F80h]
0x14000ccf3  test    rax, rax
0x14000ccf6  jz      short loc_14000CCFD
0x14000ccf8  sub     r8, rax
0x14000ccfb  jmp     short loc_14000CD00
0x14000ccfd  mov     r8, r13
0x14000cd00  mov     rcx, [r9+0F78h]
0x14000cd07  add     rcx, r8
0x14000cd0a  mov     [rbx+398h], rcx
0x14000cd11  test    cs:byte_14005C48C, 2
0x14000cd18  jz      short loc_14000CD82
0x14000cd1a  test    r15b, r15b
0x14000cd1d  lea     rdx, QuicStreamCreated
0x14000cd24  mov     r8, rbx
0x14000cd27  setz    al
0x14000cd2a  mov     byte ptr [rsp+128h+var_100], al
0x14000cd2e  mov     rax, [rbx+50h]
0x14000cd32  mov     [rsp+128h+var_108], rax
0x14000cd37  call    McTemplateU0ppxu_EtwWriteTransfer
0x14000cd3c  test    cs:byte_14005C48C, 2
0x14000cd43  jz      short loc_14000CD82
0x14000cd45  mov     rcx, rbx
0x14000cd48  call    QuicStreamSendGetState
0x14000cd4d  mov     r9d, eax
0x14000cd50  lea     rdx, QuicStreamSendState
0x14000cd57  mov     r8, rbx
0x14000cd5a  call    McTemplateU0pu_EtwWriteTransfer
0x14000cd5f  test    cs:byte_14005C48C, 2
0x14000cd66  jz      short loc_14000CD82
0x14000cd68  mov     rcx, rbx
0x14000cd6b  call    QuicStreamRecvGetState
0x14000cd70  mov     r9d, eax
0x14000cd73  lea     rdx, QuicStreamRecvState
0x14000cd7a  mov     r8, rbx
0x14000cd7d  call    McTemplateU0pu_EtwWriteTransfer
0x14000cd82  test    byte ptr [rbx+5Bh], 2
0x14000cd86  jz      short loc_14000CD95
0x14000cd88  mov     edx, 80h
0x14000cd8d  mov     rcx, rbx
0x14000cd90  call    QuicStreamAddOutFlowBlockedReason
0x14000cd95  cmp     [rbx+60h], r13w
0x14000cd9a  jz      loc_14000CE99
0x14000cda0  mov     rax, [rbx+48h]
0x14000cda4  lea     rsi, [rax+0D58h]
0x14000cdab  cmp     [rbx+38h], r13
0x14000cdaf  jnz     short loc_14000CDF9
0x14000cdb1  mov     rdx, [rsi+58h]
0x14000cdb5  lea     rax, [rsi+50h]
0x14000cdb9  cmp     rdx, rax
0x14000cdbc  jz      short loc_14000CDD7
0x14000cdbe  movzx   ecx, word ptr [rbx+1A0h]
0x14000cdc5  cmp     cx, [rdx+168h]
0x14000cdcc  jbe     short loc_14000CDD7
0x14000cdce  mov     rdx, [rdx+8]
0x14000cdd2  cmp     rdx, rax
0x14000cdd5  jnz     short loc_14000CDC5
0x14000cdd7  mov     rax, [rdx]
0x14000cdda  lea     rcx, [rbx+38h]
0x14000cdde  mov     [rcx], rax
0x14000cde1  mov     [rcx+8], rdx
0x14000cde5  mov     [rax+8], rcx
0x14000cde9  mov     [rdx], rcx
0x14000cdec  lea     rcx, [rbx+10h]
0x14000cdf0  call    CxPlatRefIncrement
0x14000cdf5  mov     rax, [rbx+48h]
0x14000cdf9  test    byte ptr [rax+0F8h], 4
0x14000ce00  jz      loc_14000CE99
0x14000ce06  and     byte ptr [rbx+5Bh], 7Fh
0x14000ce0a  test    byte ptr [rsi], 1
0x14000ce0d  mov     [rsp+128h+arg_8], rbp
0x14000ce15  lea     rbp, [rsi-0D58h]
0x14000ce1c  jnz     short loc_14000CE91
0x14000ce1e  mov     rcx, rsi
0x14000ce21  call    QuicSendCanSendFlagsNow
0x14000ce26  test    al, al
0x14000ce28  jz      short loc_14000CE91
0x14000ce2a  mov     rcx, [rbp+48h]
0x14000ce2e  add     rcx, 7E0h
0x14000ce35  call    CxPlatPoolAlloc
0x14000ce3a  mov     r14, rax
0x14000ce3d  test    rax, rax
0x14000ce40  jz      short loc_14000CE91
0x14000ce42  mov     dword ptr [rax+10h], 4
0x14000ce49  mov     byte ptr [rax+14h], 1
0x14000ce4d  or      byte ptr [rsi], 1
0x14000ce50  test    cs:byte_14005C48A, 1
0x14000ce57  jz      short loc_14000CE6E
0x14000ce59  mov     r9d, 1
0x14000ce5f  lea     rdx, QuicConnQueueSendFlush
0x14000ce66  mov     r8, rbp
0x14000ce69  call    McTemplateU0pq_EtwWriteTransfer
0x14000ce6e  mov     rdx, [rbp+48h]
0x14000ce72  lea     rcx, [rbp+590h]
0x14000ce79  mov     r8, r14
0x14000ce7c  call    QuicOperationEnqueue
0x14000ce81  test    al, al
0x14000ce83  jz      short loc_14000CE91
0x14000ce85  mov     rcx, [rbp+40h]
0x14000ce89  mov     rdx, rbp
0x14000ce8c  call    QuicWorkerQueueConnection
0x14000ce91  mov     rbp, [rsp+128h+arg_8]
0x14000ce99  movzx   eax, byte ptr [rbx+59h]
0x14000ce9d  movzx   ecx, r12b
0x14000cea1  and     cl, 1
0x14000cea4  and     al, 0FEh
0x14000cea6  or      al, cl
0x14000cea8  mov     [rbx+59h], al
0x14000ceab  test    cl, cl
0x14000cead  jz      short loc_14000CEC9
0x14000ceaf  mov     rcx, [rbx+48h]
0x14000ceb3  xor     r9d, r9d
0x14000ceb6  add     rcx, 0D58h
0x14000cebd  mov     rdx, rbx
0x14000cec0  lea     r8d, [r9+20h]
0x14000cec4  call    QuicSendSetStreamSendFlag
0x14000cec9  mov     rax, [rbx+48h]
0x14000cecd  mov     rcx, [rbx+50h]
0x14000ced1  mov     edx, [rax]
0x14000ced3  test    cl, 2
0x14000ced6  jz      short loc_14000CEE1
0x14000ced8  mov     rax, [rax+678h]
0x14000cedf  jmp     short loc_14000CF0C
0x14000cee1  and     ecx, 1
0x14000cee4  cmp     edx, 4
0x14000cee7  jnz     short loc_14000CEF7
0x14000cee9  test    rcx, rcx
0x14000ceec  jz      short loc_14000CF05
0x14000ceee  mov     rax, [rax+670h]
0x14000cef5  jmp     short loc_14000CF0C
0x14000cef7  test    rcx, rcx
0x14000cefa  jnz     short loc_14000CF05
0x14000cefc  mov     rax, [rax+670h]
0x14000cf03  jmp     short loc_14000CF0C
0x14000cf05  mov     rax, [rax+668h]
0x14000cf0c  mov     [rbx+0B8h], rax
0x14000cf13  test    rax, rax
0x14000cf16  jnz     short loc_14000CF23
0x14000cf18  lea     edx, [rax+40h]
0x14000cf1b  mov     rcx, rbx
0x14000cf1e  call    QuicStreamAddOutFlowBlockedReason
0x14000cf23  mov     rax, [rbx+0B8h]
0x14000cf2a  mov     ecx, 0FFFFFFFFh
  ... truncated ...
```
