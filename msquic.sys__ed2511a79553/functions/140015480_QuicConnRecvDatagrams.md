# QuicConnRecvDatagrams

- ea: `0x140015480`
- end: `0x140015b62`
- name: `QuicConnRecvDatagrams`
- size: `1762`
- prototype: `char __fastcall(__int64, _QWORD *, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x14000935c`
- `0x140014d80`

## callees

- `0x14000491c`
- `0x14000d7a0`
- `0x14000f370`
- `0x140012c80`
- `0x140015480`
- `0x140015b70`
- `0x14001c638`
- `0x14001c664`
- `0x140021664`
- `0x140026a88`
- `0x14002a8dc`
- `0x14002b8e8`
- `0x14002fbf8`
- `0x140033810`
- `0x140034e44`
- `0x1400390c4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`
- `0x140040de8`
- `0x140048c78`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140015520`
- `ntoskrnl!_snprintf_s` at `0x140015a1b`
- `ntoskrnl!_snprintf_s` at `0x140015a9f`
- `ntoskrnl!_snprintf_s` at `0x140015520`
- `ntoskrnl!_snprintf_s` at `0x140015a1b`
- `ntoskrnl!_snprintf_s` at `0x140015a9f`
- `HAL!KeQueryPerformanceCounter` at `0x140015942`
- `HAL!KeQueryPerformanceCounter` at `0x140015942`

## string_xrefs

- `0x1400155b2`: `Max paths already tracked`
- `0x140015a84`: `Removing invalid path[%hhu]`

## pseudocode

```c
char __fastcall QuicConnRecvDatagrams(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v7; // r12
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int8 v12; // si
  __int64 v13; // r13
  int v14; // r15d
  __int64 v15; // rbx
  _QWORD *v16; // r14
  __int64 PathForPacket; // rax
  __int64 v18; // r14
  __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // rdx
  char v22; // cl
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v27; // rcx
  unsigned __int8 v28; // bl
  unsigned __int8 *v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int16 v33; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v34; // [rsp+32h] [rbp-CEh]
  int v35; // [rsp+34h] [rbp-CCh]
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v37; // [rsp+40h] [rbp-C0h]
  _QWORD *v38; // [rsp+48h] [rbp-B8h]
  _OWORD v39[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD Src[8]; // [rsp+90h] [rbp-70h] BYREF
  char DstBuf[128]; // [rsp+110h] [rbp+10h] BYREF

  v37 = &v36;
  v7 = 0;
  v8 = (unsigned __int16)(word_14005C55E & *(_WORD *)(a1 + 270));
  v36 = 0;
  v10 = v8 % (unsigned __int16)word_14005C55C;
  LODWORD(v9) = v8 / (unsigned __int16)word_14005C55C;
  v35 = 0;
  v34 = v10;
  v33 = 0;
  if ( a5 )
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Recv %u deferred UDP datagrams", a3);
      LOBYTE(v9) = McTemplateU0ps_EtwWriteTransfer(v11, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  else if ( (byte_14005C48A & 0x10) != 0 )
  {
    LOBYTE(v9) = McTemplateU0pqq_EtwWriteTransfer((unsigned __int16)word_14005C55C, v10, a1, a3, a4);
  }
  v12 = 0;
  v13 = 0;
  v14 = 6;
  v15 = (__int64)a2;
  memset(v39, 0, sizeof(v39));
  if ( a2 )
  {
    while ( 1 )
    {
      v16 = (_QWORD *)*a2;
      *(_BYTE *)(v15 + 93) &= ~1u;
      v38 = v16;
      *(_QWORD *)v15 = 0;
      PathForPacket = QuicConnGetPathForPacket(a1, v15);
      v18 = PathForPacket;
      if ( !PathForPacket )
      {
        LOBYTE(v9) = QuicPacketLogDrop(a1, v15, "Max paths already tracked");
        goto LABEL_38;
      }
      CxPlatUpdateRoute(PathForPacket + 48, *(_QWORD *)(v15 + 8));
      if ( v18 != v13 )
      {
        if ( v12 )
        {
          QuicConnRecvDatagramBatch(a1, v13, v12, (unsigned int)v39, (__int64)Src, (__int64)&v33);
          v12 = 0;
        }
        v13 = v18;
      }
      if ( !a5 )
      {
        v20 = *(_BYTE *)(a1 + 3708) == 0;
        *(_QWORD *)(a1 + 3832) += *(unsigned __int16 *)(v15 + 24);
        if ( v20 )
          *(_BYTE *)(a1 + 3708) = *(_BYTE *)(v15 + 29);
        if ( (byte_14005C48A & 8) != 0 )
          McTemplateU0pp_EtwWriteTransfer(v19, QuicConnInFlowStats, a1);
        if ( (*(_BYTE *)(v13 + 1) & 0x20) == 0 )
          QuicPathSetAllowance(a1, v13, *(_DWORD *)(v13 + 208) + 3 * (unsigned int)*(unsigned __int16 *)(v15 + 24));
      }
      while ( 1 )
      {
        ++*(_QWORD *)(a1 + 3776);
        if ( (*(_BYTE *)(v15 + 92) & 2) == 0 )
          *(_WORD *)(v15 + 80) = *(_WORD *)(v15 + 24) + *(_WORD *)(v15 + 16) - *(_WORD *)(v15 + 56);
        LOBYTE(v9) = QuicConnRecvHeader(a1, v15, &Src[v12]);
        if ( !(_BYTE)v9 )
          break;
        if ( v12 && ((*(_BYTE *)(v15 + 92) & 4) == 0 || v14 != 6 && v14 != *(_DWORD *)(v15 + 88)) )
        {
          QuicConnRecvDatagramBatch(a1, v13, v12, (unsigned int)v39, (__int64)Src, (__int64)&v33);
          memmove(&Src[v12], Src, 0x10u);
          v12 = 0;
        }
        v14 = *(_DWORD *)(v15 + 88);
        v9 = v12++;
        v20 = (*(_BYTE *)(v15 + 92) & 4) == 0;
        *((_QWORD *)v39 + v9) = v15;
        if ( !v20 && v12 < 8u )
          goto LABEL_38;
        LOBYTE(v9) = QuicConnRecvDatagramBatch(a1, v13, v12, (unsigned int)v39, (__int64)Src, (__int64)&v33);
        a3 = *(unsigned __int8 *)(v15 + 92);
        v12 = 0;
        if ( (a3 & 4) != 0 )
          goto LABEL_38;
LABEL_35:
        LOBYTE(a3) = a3 & 0x45;
        v21 = *(_QWORD *)(v15 + 56) + *(unsigned __int16 *)(v15 + 80);
        *(_BYTE *)(v15 + 93) &= 0xF0u;
        v9 = *(unsigned __int16 *)(v15 + 24);
        *(_QWORD *)(v15 + 56) = v21;
        v10 = v21 - *(_QWORD *)(v15 + 16);
        *(_BYTE *)(v15 + 92) = a3;
        if ( v10 >= v9 )
          goto LABEL_38;
      }
      if ( (*(_BYTE *)(v15 + 93) & 1) == 0 )
        break;
      --*(_QWORD *)(a1 + 3776);
LABEL_38:
      if ( (*(_BYTE *)(v15 + 93) & 1) == 0 )
      {
        v9 = (__int64)v37;
        v37 = (__int64 *)v15;
        *(_QWORD *)v9 = v15;
        *(_WORD *)(v15 + 30) &= ~2u;
        LODWORD(v9) = v35 + 1;
        v35 = v9;
        if ( (_DWORD)v9 == 32 )
        {
          if ( v12 )
          {
            QuicConnRecvDatagramBatch(a1, v13, v12, (unsigned int)v39, (__int64)Src, (__int64)&v33);
            v12 = 0;
          }
          CxPlatRecvDataReturn(v36, v10, a3, a4);
          v9 = (__int64)&v36;
          v7 = 0;
          v36 = 0;
          v37 = &v36;
          v35 = 0;
        }
        else
        {
          v7 = v36;
        }
      }
      a2 = v38;
      v15 = (__int64)v38;
      if ( !v38 )
      {
        if ( v12 )
          LOBYTE(v9) = QuicConnRecvDatagramBatch(a1, v13, v12, (unsigned int)v39, (__int64)Src, (__int64)&v33);
        goto LABEL_47;
      }
    }
    a3 = *(unsigned __int8 *)(v15 + 92);
    if ( (a3 & 4) != 0 || (a3 & 8) == 0 )
      goto LABEL_38;
    goto LABEL_35;
  }
LABEL_47:
  if ( (*(_BYTE *)(a1 + 252) & 0x20) != 0 && !*(_DWORD *)(a1 + 1588) )
    LOBYTE(v9) = QuicConnTryClose(a1, 10, 11, 0, 0);
  if ( (_BYTE)v33 )
  {
    v22 = *(_BYTE *)(a1 + 248);
    if ( (v22 & 8) != 0 )
    {
      v23 = *(_QWORD *)(a1 + 1632);
      if ( v23 )
      {
        v24 = *(_QWORD *)(a1 + 128);
        if ( !v24 || v24 >= v23 )
          goto LABEL_59;
      }
      v23 = *(_QWORD *)(a1 + 128);
    }
    else
    {
      v23 = *(_QWORD *)(a1 + 120);
    }
    if ( !v23 )
    {
      QuicConnTimerCancel(a1, 4);
LABEL_63:
      LODWORD(v9) = *(_DWORD *)(a1 + 204);
      if ( (_DWORD)v9 )
        LOBYTE(v9) = QuicConnTimerSet(a1, 3, (unsigned int)(1000 * v9));
      goto LABEL_65;
    }
    if ( (v22 & 8) == 0 )
    {
LABEL_61:
      PerformanceCounter = KeQueryPerformanceCounter(0);
      QuicConnTimerSetEx(
        a1,
        4,
        1000 * v23,
        ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
      + (1000000LL * PerformanceCounter.LowPart
       + ((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
      / CxPlatPerfFreq.QuadPart);
      goto LABEL_63;
    }
LABEL_59:
    v25 = *(_QWORD *)(a1 + 472) + 4 * (*(_QWORD *)(a1 + 504) + 250LL * *(_QWORD *)(a1 + 1704));
    if ( v23 < 3 * v25 / 0x3E8uLL )
      v23 = 3 * v25 / 0x3E8uLL;
    goto LABEL_61;
  }
LABEL_65:
  if ( v7 )
    LOBYTE(v9) = CxPlatRecvDataReturn(v7, v10, a3, a4);
  if ( *(_DWORD *)a1 == 4 && !*(_QWORD *)(a1 + 3816) && (*(_BYTE *)(a1 + 248) & 0x10) == 0 )
  {
    if ( (byte_14005C48B & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Aborting connection with invalid initial packets");
      McTemplateU0ps_EtwWriteTransfer(v27, QuicConnLogWarning, a1, DstBuf);
    }
    LOBYTE(v9) = QuicConnCloseLocally(a1, 19, -1073741536);
  }
  v28 = *(_BYTE *)(a1 + 275) - 1;
  if ( *(_BYTE *)(a1 + 275) != 1 )
  {
    LOBYTE(v9) = *(_BYTE *)(a1 + 275) - 1;
    v29 = (unsigned __int8 *)(a1 + 240LL * v28 + 320);
    do
    {
      if ( (v29[1] & 0x10) == 0 )
      {
        if ( byte_14005C48B < 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Removing invalid path[%hhu]", *v29);
          McTemplateU0ps_EtwWriteTransfer(v30, QuicConnLogInfo, a1, DstBuf);
        }
        LOBYTE(v9) = QuicPathRemove(a1, v28);
      }
      v29 -= 240;
      --v28;
    }
    while ( v28 );
  }
  if ( (*(_BYTE *)(a1 + 250) & 0x40) == 0
    && (*(_BYTE *)(a1 + 248) & 8) != 0
    && (*(_BYTE *)(a1 + 249) & 1) == 0
    && HIBYTE(v33) )
  {
    LOWORD(v35) = 0;
    CxPlatRandom(2u);
    LOBYTE(v31) = 1;
    *(_WORD *)(a1 + 270) = v34 | v35 & ~word_14005C55E;
    LOBYTE(v9) = QuicConnGenerateNewSourceCids(a1, v31);
    *(_BYTE *)(a1 + 250) |= 0x40u;
  }
  return v9;
}

```

## disassembly

```asm
0x140015480  mov     [rsp-8+arg_18], rbx
0x140015485  push    rbp
0x140015486  push    rsi
0x140015487  push    rdi
0x140015488  push    r12
0x14001548a  push    r13
0x14001548c  push    r14
0x14001548e  push    r15
0x140015490  lea     rbp, [rsp-0A0h]
0x140015498  sub     rsp, 1A0h
0x14001549f  mov     rax, cs:__security_cookie
0x1400154a6  xor     rax, rsp
0x1400154a9  mov     [rbp+0D0h+var_40], rax
0x1400154b0  xor     r10d, r10d
0x1400154b3  lea     rax, [rsp+1D0h+var_198]
0x1400154b8  mov     [rsp+1D0h+var_190], rax
0x1400154bd  mov     rdi, rcx
0x1400154c0  movzx   eax, word ptr [rcx+10Eh]
0x1400154c7  mov     r14, rdx
0x1400154ca  movzx   ecx, cs:word_14005C55E
0x1400154d1  mov     r12d, r10d
0x1400154d4  and     eax, ecx
0x1400154d6  mov     [rsp+1D0h+var_198], r10
0x1400154db  movzx   ecx, cs:word_14005C55C
0x1400154e2  cdq
0x1400154e3  idiv    ecx
0x1400154e5  mov     [rsp+1D0h+var_19C], r10d
0x1400154ea  mov     [rsp+1D0h+var_19E], dx
0x1400154ef  mov     [rsp+1D0h+var_1A0], r10w
0x1400154f5  cmp     [rbp+0D0h+arg_20], r10b
0x1400154fc  jz      short loc_140015541
0x1400154fe  test    cs:byte_14005C48C, 1
0x140015505  jz      short loc_14001555D
0x140015507  mov     dword ptr [rsp+1D0h+var_1B0], r8d
0x14001550c  lea     r9, aRecvUDeferredU; "Recv %u deferred UDP datagrams"
0x140015513  lea     r8, [r10-1]; MaxCount
0x140015517  mov     edx, 80h; SizeInBytes
0x14001551c  lea     rcx, [rbp+0D0h+DstBuf]; DstBuf
0x140015520  call    cs:__imp__snprintf_s
0x140015527  nop     dword ptr [rax+rax+00h]
0x14001552c  lea     r9, [rbp+0D0h+DstBuf]
0x140015530  mov     r8, rdi
0x140015533  lea     rdx, QuicConnLogVerbose
0x14001553a  call    McTemplateU0ps_EtwWriteTransfer
0x14001553f  jmp     short loc_14001555A
0x140015541  test    cs:byte_14005C48A, 10h
0x140015548  jz      short loc_14001555D
0x14001554a  mov     dword ptr [rsp+1D0h+var_1B0], r9d
0x14001554f  mov     r9d, r8d
0x140015552  mov     r8, rdi
0x140015555  call    McTemplateU0pqq_EtwWriteTransfer
0x14001555a  xor     r10d, r10d
0x14001555d  xorps   xmm0, xmm0
0x140015560  xor     sil, sil
0x140015563  mov     r13, r10
0x140015566  mov     r15d, 6
0x14001556c  mov     rbx, r14
0x14001556f  movups  [rsp+1D0h+var_180], xmm0
0x140015574  movups  [rsp+1D0h+var_170], xmm0
0x140015579  movups  [rsp+1D0h+var_160], xmm0
0x14001557e  movups  [rbp+0D0h+var_150], xmm0
0x140015582  test    r14, r14
0x140015585  jz      loc_140015884
0x14001558b  nop     dword ptr [rax+rax+00h]
0x140015590  mov     r14, [r14]
0x140015593  mov     rdx, rbx
0x140015596  and     byte ptr [rbx+5Dh], 0FEh
0x14001559a  mov     rcx, rdi
0x14001559d  mov     [rsp+1D0h+var_188], r14
0x1400155a2  mov     [rbx], r10
0x1400155a5  call    QuicConnGetPathForPacket
0x1400155aa  mov     r14, rax
0x1400155ad  test    rax, rax
0x1400155b0  jnz     short loc_1400155C9
0x1400155b2  lea     r8, aMaxPathsAlread; "Max paths already tracked"
0x1400155b9  mov     rdx, rbx
0x1400155bc  mov     rcx, rdi
0x1400155bf  call    QuicPacketLogDrop
0x1400155c4  jmp     loc_1400157BC
0x1400155c9  mov     rdx, [rbx+8]
0x1400155cd  lea     rcx, [rax+30h]
0x1400155d1  call    CxPlatUpdateRoute
0x1400155d6  cmp     r14, r13
0x1400155d9  jz      short loc_14001560D
0x1400155db  test    sil, sil
0x1400155de  jz      short loc_14001560A
0x1400155e0  lea     rax, [rsp+1D0h+var_1A0]
0x1400155e5  movzx   r8d, sil
0x1400155e9  mov     [rsp+1D0h+var_1A8], rax
0x1400155ee  lea     r9, [rsp+1D0h+var_180]
0x1400155f3  lea     rax, [rbp+0D0h+Src]
0x1400155f7  mov     rdx, r13
0x1400155fa  mov     rcx, rdi
0x1400155fd  mov     [rsp+1D0h+var_1B0], rax
0x140015602  call    QuicConnRecvDatagramBatch
0x140015607  xor     sil, sil
0x14001560a  mov     r13, r14
0x14001560d  cmp     [rbp+0D0h+arg_20], 0
0x140015614  jnz     short loc_140015680
0x140015616  movzx   r9d, word ptr [rbx+18h]
0x14001561b  add     r9, [rdi+0EF8h]
0x140015622  cmp     byte ptr [rdi+0E7Ch], 0
0x140015629  mov     [rdi+0EF8h], r9
0x140015630  jnz     short loc_14001563C
0x140015632  movzx   eax, byte ptr [rbx+1Dh]
0x140015636  mov     [rdi+0E7Ch], al
0x14001563c  test    cs:byte_14005C48A, 8
0x140015643  jz      short loc_140015654
0x140015645  mov     r8, rdi
0x140015648  lea     rdx, QuicConnInFlowStats
0x14001564f  call    McTemplateU0pp_EtwWriteTransfer
0x140015654  test    byte ptr [r13+1], 20h
0x140015659  jnz     short loc_140015680
0x14001565b  movzx   eax, word ptr [rbx+18h]
0x14001565f  mov     rdx, r13
0x140015662  mov     rcx, rdi
0x140015665  lea     r8d, [rax+rax*2]
0x140015669  add     r8d, [r13+0D0h]
0x140015670  call    QuicPathSetAllowance
0x140015675  nop     word ptr [rax+rax+00000000h]
0x140015680  inc     qword ptr [rdi+0EC0h]
0x140015687  test    byte ptr [rbx+5Ch], 2
0x14001568b  jnz     short loc_14001569D
0x14001568d  movzx   ecx, word ptr [rbx+10h]
0x140015691  sub     cx, [rbx+38h]
0x140015695  add     cx, [rbx+18h]
0x140015699  mov     [rbx+50h], cx
0x14001569d  movzx   eax, sil
0x1400156a1  lea     r14, [rbp+0D0h+Src]
0x1400156a5  shl     rax, 4
0x1400156a9  mov     rdx, rbx
0x1400156ac  add     r14, rax
0x1400156af  mov     rcx, rdi
0x1400156b2  mov     r8, r14
0x1400156b5  call    QuicConnRecvHeader
0x1400156ba  test    al, al
0x1400156bc  jnz     short loc_1400156E6
0x1400156be  test    byte ptr [rbx+5Dh], 1
0x1400156c2  jnz     loc_1400157B5
0x1400156c8  movzx   r8d, byte ptr [rbx+5Ch]
0x1400156cd  test    r8b, 4
0x1400156d1  jnz     loc_1400157BC
0x1400156d7  test    r8b, 8
0x1400156db  jz      loc_1400157BC
0x1400156e1  jmp     loc_14001578A
0x1400156e6  test    sil, sil
0x1400156e9  jz      short loc_140015739
0x1400156eb  test    byte ptr [rbx+5Ch], 4
0x1400156ef  jz      short loc_1400156FD
0x1400156f1  cmp     r15d, 6
0x1400156f5  jz      short loc_140015739
0x1400156f7  cmp     r15d, [rbx+58h]
0x1400156fb  jz      short loc_140015739
0x1400156fd  lea     rax, [rsp+1D0h+var_1A0]
0x140015702  movzx   r8d, sil
0x140015706  mov     [rsp+1D0h+var_1A8], rax
0x14001570b  lea     r9, [rsp+1D0h+var_180]
0x140015710  lea     rax, [rbp+0D0h+Src]
0x140015714  mov     rdx, r13
0x140015717  mov     rcx, rdi
0x14001571a  mov     [rsp+1D0h+var_1B0], rax
0x14001571f  call    QuicConnRecvDatagramBatch
0x140015724  mov     r8d, 10h; Size
0x14001572a  lea     rdx, [rbp+0D0h+Src]; Src
0x14001572e  mov     rcx, r14; void *
0x140015731  call    memmove
0x140015736  xor     sil, sil
0x140015739  mov     r15d, [rbx+58h]
0x14001573d  movzx   eax, sil
0x140015741  inc     sil
0x140015744  test    byte ptr [rbx+5Ch], 4
0x140015748  mov     qword ptr [rsp+rax*8+1D0h+var_180], rbx
0x14001574d  jz      short loc_140015755
0x14001574f  cmp     sil, 8
0x140015753  jb      short loc_1400157BC
0x140015755  lea     rax, [rsp+1D0h+var_1A0]
0x14001575a  movzx   r8d, sil
0x14001575e  mov     [rsp+1D0h+var_1A8], rax
0x140015763  lea     r9, [rsp+1D0h+var_180]
0x140015768  lea     rax, [rbp+0D0h+Src]
0x14001576c  mov     rdx, r13
0x14001576f  mov     rcx, rdi
0x140015772  mov     [rsp+1D0h+var_1B0], rax
0x140015777  call    QuicConnRecvDatagramBatch
0x14001577c  movzx   r8d, byte ptr [rbx+5Ch]
0x140015781  xor     sil, sil
0x140015784  test    r8b, 4
0x140015788  jnz     short loc_1400157BC
0x14001578a  movzx   edx, word ptr [rbx+50h]
0x14001578e  and     r8b, 45h
0x140015792  add     rdx, [rbx+38h]
0x140015796  and     byte ptr [rbx+5Dh], 0F0h
0x14001579a  movzx   eax, word ptr [rbx+18h]
0x14001579e  mov     [rbx+38h], rdx
0x1400157a2  sub     rdx, [rbx+10h]
0x1400157a6  mov     [rbx+5Ch], r8b
0x1400157aa  cmp     rdx, rax
0x1400157ad  jl      loc_140015680
0x1400157b3  jmp     short loc_1400157BC
0x1400157b5  dec     qword ptr [rdi+0EC0h]
0x1400157bc  test    byte ptr [rbx+5Dh], 1
0x1400157c0  jnz     short loc_140015841
0x1400157c2  mov     rax, [rsp+1D0h+var_190]
0x1400157c7  mov     [rsp+1D0h+var_190], rbx
0x1400157cc  mov     [rax], rbx
0x1400157cf  mov     eax, 0FFFDh
0x1400157d4  and     [rbx+1Eh], ax
0x1400157d8  mov     eax, [rsp+1D0h+var_19C]
0x1400157dc  inc     eax
0x1400157de  mov     [rsp+1D0h+var_19C], eax
0x1400157e2  cmp     eax, 20h ; ' '
0x1400157e5  jnz     short loc_14001583C
0x1400157e7  test    sil, sil
0x1400157ea  jz      short loc_140015816
0x1400157ec  lea     rax, [rsp+1D0h+var_1A0]
0x1400157f1  movzx   r8d, sil
0x1400157f5  mov     [rsp+1D0h+var_1A8], rax
0x1400157fa  lea     r9, [rsp+1D0h+var_180]
0x1400157ff  lea     rax, [rbp+0D0h+Src]
0x140015803  mov     rdx, r13
0x140015806  mov     rcx, rdi
0x140015809  mov     [rsp+1D0h+var_1B0], rax
0x14001580e  call    QuicConnRecvDatagramBatch
0x140015813  xor     sil, sil
0x140015816  mov     rcx, [rsp+1D0h+var_198]
0x14001581b  call    CxPlatRecvDataReturn
0x140015820  xor     r10d, r10d
0x140015823  lea     rax, [rsp+1D0h+var_198]
0x140015828  mov     r12d, r10d
0x14001582b  mov     [rsp+1D0h+var_198], r10
0x140015830  mov     [rsp+1D0h+var_190], rax
0x140015835  mov     [rsp+1D0h+var_19C], r10d
0x14001583a  jmp     short loc_140015844
0x14001583c  mov     r12, [rsp+1D0h+var_198]
0x140015841  xor     r10d, r10d
0x140015844  mov     r14, [rsp+1D0h+var_188]
0x140015849  mov     rbx, r14
0x14001584c  test    r14, r14
0x14001584f  jnz     loc_140015590
0x140015855  test    sil, sil
0x140015858  jz      short loc_140015884
0x14001585a  lea     rax, [rsp+1D0h+var_1A0]
0x14001585f  movzx   r8d, sil
0x140015863  mov     [rsp+1D0h+var_1A8], rax
0x140015868  lea     r9, [rsp+1D0h+var_180]
0x14001586d  lea     rax, [rbp+0D0h+Src]
0x140015871  mov     rdx, r13
0x140015874  mov     rcx, rdi
0x140015877  mov     [rsp+1D0h+var_1B0], rax
0x14001587c  call    QuicConnRecvDatagramBatch
0x140015881  xor     r10d, r10d
0x140015884  test    byte ptr [rdi+0FCh], 20h
0x14001588b  jz      short loc_1400158AF
0x14001588d  cmp     dword ptr [rdi+634h], 0
0x140015894  jnz     short loc_1400158AF
0x140015896  xor     r9d, r9d
0x140015899  mov     word ptr [rsp+1D0h+var_1B0], r10w
0x14001589f  mov     rcx, rdi
0x1400158a2  lea     edx, [r9+0Ah]
0x1400158a6  lea     r8d, [r9+0Bh]
0x1400158aa  call    QuicConnTryClose
0x1400158af  cmp     byte ptr [rsp+1D0h+var_1A0], 0
0x1400158b4  jz      loc_1400159D6
0x1400158ba  movzx   ecx, byte ptr [rdi+0F8h]
0x1400158c1  test    cl, 8
0x1400158c4  jz      short loc_1400158EC
0x1400158c6  mov     rbx, [rdi+660h]
0x1400158cd  test    rbx, rbx
0x1400158d0  jz      short loc_1400158E3
0x1400158d2  mov     rax, [rdi+80h]
0x1400158d9  test    rax, rax
0x1400158dc  jz      short loc_1400158FE
0x1400158de  cmp     rax, rbx
0x1400158e1  jnb     short loc_1400158FE
0x1400158e3  mov     rbx, [rdi+80h]
0x1400158ea  jmp     short loc_1400158F0
0x1400158ec  mov     rbx, [rdi+78h]
0x1400158f0  test    rbx, rbx
0x1400158f3  jz      loc_1400159AB
0x1400158f9  test    cl, 8
0x1400158fc  jz      short loc_140015940
0x1400158fe  imul    rcx, [rdi+6A8h], 0FAh
0x140015909  mov     rax, [rdi+1D8h]
0x140015910  add     rcx, [rdi+1F8h]
0x140015917  lea     rcx, [rax+rcx*4]
0x14001591b  mov     rax, 624DD2F1A9FBE77h
0x140015925  lea     r8, [rcx+rcx*2]
0x140015929  mul     r8
0x14001592c  sub     r8, rdx
0x14001592f  shr     r8, 1
0x140015932  add     r8, rdx
0x140015935  shr     r8, 9
0x140015939  cmp     rbx, r8
0x14001593c  cmovb   rbx, r8
0x140015940  xor     ecx, ecx; PerformanceFrequency
0x140015942  call    cs:__imp_KeQueryPerformanceCounter
0x140015949  nop     dword ptr [rax+rax+00h]
0x14001594e  mov     r8, qword ptr cs:CxPlatPerfFreq
0x140015955  xor     edx, edx
0x140015957  mov     rcx, rax
  ... truncated ...
```
