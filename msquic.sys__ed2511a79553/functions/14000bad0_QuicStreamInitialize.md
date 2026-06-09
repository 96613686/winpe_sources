# QuicStreamInitialize

- ea: `0x14000bad0`
- end: `0x14000bf27`
- name: `QuicStreamInitialize`
- size: `1111`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000af30`
- `0x140010440`

## callees

- `0x14000bad0`
- `0x1400290b4`
- `0x140029104`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003ed00`
- `0x140040de8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000bbcf`
- `ntoskrnl!_snprintf_s` at `0x14000bbcf`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000bc5d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000bc5d`
- `ntoskrnl!ExAllocatePool2` at `0x14000be01`
- `ntoskrnl!ExAllocatePool2` at `0x14000be01`
- `HAL!KeQueryPerformanceCounter` at `0x14000be8e`
- `HAL!KeQueryPerformanceCounter` at `0x14000be8e`

## string_xrefs

- `0x14000bbb7`: `Configured for delayed ID FC updates`

## pseudocode

```c
__int64 __fastcall QuicStreamInitialize(KSPIN_LOCK a1, char a2, char a3, KSPIN_LOCK **a4)
{
  _QWORD *p_Next; // rsi
  PSLIST_ENTRY v9; // rax
  __int64 v10; // rcx
  KSPIN_LOCK *v11; // rbx
  __int64 result; // rax
  char v13; // al
  __int64 v14; // rcx
  char v15; // al
  char v16; // di
  char v17; // al
  int v18; // r14d
  char v19; // cl
  char v20; // al
  char v21; // cl
  char v22; // al
  char v23; // al
  __int64 v24; // r15
  PSLIST_ENTRY v25; // rax
  int v26; // eax
  __int64 *v27; // rdi
  __int64 Pool2; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  char DstBuf[128]; // [rsp+20h] [rbp-C8h] BYREF

  p_Next = 0;
  v9 = CxPlatPoolAlloc(*(_QWORD *)(a1 + 72) + 384LL);
  v11 = (KSPIN_LOCK *)v9;
  if ( !v9 )
    return 3221225495LL;
  if ( (byte_14005C48D & 2) != 0 )
    McTemplateU0pp_EtwWriteTransfer(v10, QuicStreamAlloc, v9);
  memset(v11, 0, 0x3A0u);
  _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 72) + 2272LL));
  v13 = *((_BYTE *)v11 + 88);
  *(_DWORD *)v11 = 5;
  v11[9] = a1;
  *((_BYTE *)v11 + 88) = v13 & 0x9F | (32 * (a3 & 3));
  v11[10] = -1;
  *((_BYTE *)v11 + 93) = *((_BYTE *)v11 + 93) & 0xFD | ((a3 & 4) != 0 ? 2 : 0);
  if ( (a3 & 4) != 0 && (byte_14005C48D & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Configured for delayed ID FC updates");
    McTemplateU0ps_EtwWriteTransfer(v14, QuicStreamLogVerbose, v11, DstBuf);
  }
  v15 = *((_BYTE *)v11 + 91);
  *((_BYTE *)v11 + 88) |= 1u;
  v16 = v15 & 0xED | 2 | (2 * (a3 & 8 | 2));
  *((_BYTE *)v11 + 91) = v16;
  if ( (*(_BYTE *)(a1 + 236) & 0x40) == 0 || (v16 & 0x10) != 0 )
    v17 = 0;
  else
    v17 = 8;
  v11[85] = -1;
  *((_WORD *)v11 + 208) = 0x7FFF;
  *((_BYTE *)v11 + 91) = v17 | v16 & 0xF7;
  v18 = 1;
  v11[17] = (KSPIN_LOCK)(v11 + 16);
  v11[2] = 1;
  KeInitializeSpinLock(v11 + 13);
  *((_DWORD *)v11 + 69) = 8;
  *((_DWORD *)v11 + 70) = 0x100000;
  v11[2] = 1;
  v11[33] = (KSPIN_LOCK)(v11 + 36);
  *((_DWORD *)v11 + 68) = 0;
  v11[94] = (KSPIN_LOCK)(v11 + 98);
  v11[90] = (KSPIN_LOCK)(v11 + 91);
  *((_DWORD *)v11 + 186) = 0;
  *(_BYTE *)(v11[90] + 20) = 0;
  **(_DWORD **)(v11[90] + 24) = 9;
  *(_QWORD *)(*(_QWORD *)(v11[90] + 24) + 24LL) = v11;
  if ( (v11[11] & 0x20) != 0 )
  {
    v19 = *((_BYTE *)v11 + 90);
    v20 = *((_BYTE *)v11 + 91);
    if ( a2 )
    {
      *((_BYTE *)v11 + 89) |= 4u;
      v21 = v19 | 2;
      v22 = v20 & 0xFD;
      *((_BYTE *)v11 + 92) |= 2u;
    }
    else
    {
      v21 = v19 | 0x10;
      v22 = v20 & 0xFA | 1;
    }
    *((_BYTE *)v11 + 91) = v22;
    *((_BYTE *)v11 + 90) = v21;
  }
  v23 = *((_BYTE *)v11 + 91);
  v24 = *(unsigned int *)(a1 + 168);
  if ( (v23 & 0x10) != 0 )
  {
    v18 = 3;
  }
  else if ( (v23 & 8) != 0 )
  {
    v18 = 2;
  }
  if ( (_DWORD)v24 == 4096 && v18 != 3 )
  {
    v25 = CxPlatPoolAlloc(*(_QWORD *)(a1 + 72) + 480LL);
    p_Next = &v25->Next;
    if ( !v25 )
    {
LABEL_35:
      _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 72) + 2272LL));
      *((_BYTE *)v11 + 92) |= 0x40u;
      CxPlatPoolFree(v11);
      return 3221225495LL;
    }
    BYTE4(v25[1].Next) &= 0xFCu;
    LODWORD(v25[1].Next) = 4096;
    *((_QWORD *)&v25[1].Next + 1) = v25 + 2;
  }
  if ( (v11[11] & 0x20) != 0 )
  {
    v26 = *(_DWORD *)(a1 + 164);
  }
  else if ( a2 )
  {
    v26 = *(_DWORD *)(a1 + 160);
  }
  else
  {
    v26 = *(_DWORD *)(a1 + 156);
  }
  *((_DWORD *)v11 + 164) = v26;
  v27 = (__int64 *)(v11 + 56);
  v11[80] = 0;
  v11[81] = 0;
  v11[79] = 0;
  *((_DWORD *)v11 + 166) = v18;
  v11[59] = (KSPIN_LOCK)p_Next;
  v11[58] = 0;
  v11[60] = (KSPIN_LOCK)(v11 + 63);
  *((_DWORD *)v11 + 122) = 0;
  *((_DWORD *)v11 + 123) = 8;
  *((_DWORD *)v11 + 124) = 0x100000;
  v11[57] = (KSPIN_LOCK)(v11 + 56);
  v11[56] = (KSPIN_LOCK)(v11 + 56);
  if ( v18 == 3 )
  {
    LODWORD(v24) = 0;
  }
  else
  {
    if ( !p_Next )
    {
      Pool2 = ExAllocatePool2(66, v24 + 32, 858874705);
      p_Next = (_QWORD *)Pool2;
      if ( !Pool2 )
      {
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(v30, v29, "recv_buffer", v24 + 32);
        goto LABEL_35;
      }
      *(_DWORD *)(Pool2 + 16) = v24;
      *(_BYTE *)(Pool2 + 20) &= 0xFCu;
      *(_QWORD *)(Pool2 + 24) = Pool2 + 32;
    }
    v31 = *v27;
    *p_Next = *v27;
    p_Next[1] = v27;
    *(_QWORD *)(v31 + 8) = p_Next;
    *v27 = (__int64)p_Next;
  }
  *((_DWORD *)v11 + 165) = v24;
  v11[53] = *((unsigned int *)v11 + 164);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v11[55] = ((1000000 * HIDWORD(PerformanceCounter.QuadPart) / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
          + (((1000000 * HIDWORD(PerformanceCounter.QuadPart) % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
           + 1000000LL * PerformanceCounter.LowPart)
          / CxPlatPerfFreq.QuadPart;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 240));
  *((_BYTE *)v11 + 88) |= 2u;
  result = 0;
  *a4 = v11;
  return result;
}

```

## disassembly

```asm
0x14000bad0  push    rbx
0x14000bad2  push    rbp
0x14000bad3  push    rsi
0x14000bad4  push    rdi
0x14000bad5  push    r12
0x14000bad7  push    r13
0x14000bad9  sub     rsp, 0B8h
0x14000bae0  mov     rax, cs:__security_cookie
0x14000bae7  xor     rax, rsp
0x14000baea  mov     [rsp+0E8h+var_48], rax
0x14000baf2  mov     rbp, rcx
0x14000baf5  mov     r13, r9
0x14000baf8  mov     rcx, [rcx+48h]
0x14000bafc  mov     edi, r8d
0x14000baff  add     rcx, 180h
0x14000bb06  movzx   r12d, dl
0x14000bb0a  xor     esi, esi
0x14000bb0c  call    CxPlatPoolAlloc
0x14000bb11  mov     rbx, rax
0x14000bb14  test    rax, rax
0x14000bb17  jnz     short loc_14000BB23
0x14000bb19  mov     eax, 0C0000017h
0x14000bb1e  jmp     loc_14000BF06
0x14000bb23  test    cs:byte_14005C48D, 2
0x14000bb2a  mov     [rsp+0E8h+arg_8], r14
0x14000bb32  mov     [rsp+0E8h+var_38], r15
0x14000bb3a  jz      short loc_14000BB4E
0x14000bb3c  mov     r9, rbp
0x14000bb3f  lea     rdx, QuicStreamAlloc
0x14000bb46  mov     r8, rbx
0x14000bb49  call    McTemplateU0pp_EtwWriteTransfer
0x14000bb4e  xor     edx, edx; Val
0x14000bb50  mov     r8d, 3A0h; Size
0x14000bb56  mov     rcx, rbx; void *
0x14000bb59  call    memset
0x14000bb5e  mov     rax, [rbp+48h]
0x14000bb62  lock inc qword ptr [rax+8E0h]
0x14000bb6a  movzx   eax, byte ptr [rbx+58h]
0x14000bb6e  movzx   ecx, dil
0x14000bb72  and     cl, 3
0x14000bb75  mov     dword ptr [rbx], 5
0x14000bb7b  shl     cl, 5
0x14000bb7e  and     al, 9Fh
0x14000bb80  or      cl, al
0x14000bb82  mov     [rbx+48h], rbp
0x14000bb86  mov     [rbx+58h], cl
0x14000bb89  mov     edx, edi
0x14000bb8b  and     edx, 4
0x14000bb8e  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x14000bb96  mov     eax, edx
0x14000bb98  neg     eax
0x14000bb9a  movzx   eax, byte ptr [rbx+5Dh]
0x14000bb9e  sbb     cl, cl
0x14000bba0  and     al, 0FDh
0x14000bba2  and     cl, 2
0x14000bba5  or      cl, al
0x14000bba7  mov     [rbx+5Dh], cl
0x14000bbaa  test    edx, edx
0x14000bbac  jz      short loc_14000BBEF
0x14000bbae  test    cs:byte_14005C48D, 1
0x14000bbb5  jz      short loc_14000BBEF
0x14000bbb7  lea     r9, aConfiguredForD; "Configured for delayed ID FC updates"
0x14000bbbe  mov     edx, 80h; SizeInBytes
0x14000bbc3  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000bbca  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x14000bbcf  call    cs:__imp__snprintf_s
0x14000bbd6  nop     dword ptr [rax+rax+00h]
0x14000bbdb  lea     r9, [rsp+0E8h+DstBuf]
0x14000bbe0  mov     r8, rbx
0x14000bbe3  lea     rdx, QuicStreamLogVerbose
0x14000bbea  call    McTemplateU0ps_EtwWriteTransfer
0x14000bbef  movzx   eax, byte ptr [rbx+5Bh]
0x14000bbf3  and     dil, 8
0x14000bbf7  or      byte ptr [rbx+58h], 1
0x14000bbfb  or      dil, 2
0x14000bbff  or      al, 2
0x14000bc01  add     dil, dil
0x14000bc04  and     al, 0EFh
0x14000bc06  or      dil, al
0x14000bc09  mov     [rbx+5Bh], dil
0x14000bc0d  test    byte ptr [rbp+0ECh], 40h
0x14000bc14  jz      short loc_14000BC20
0x14000bc16  test    dil, 10h
0x14000bc1a  jnz     short loc_14000BC20
0x14000bc1c  mov     al, 8
0x14000bc1e  jmp     short loc_14000BC22
0x14000bc20  xor     al, al
0x14000bc22  and     dil, 0F7h
0x14000bc26  mov     qword ptr [rbx+2A8h], 0FFFFFFFFFFFFFFFFh
0x14000bc31  or      dil, al
0x14000bc34  mov     word ptr [rbx+1A0h], 7FFFh
0x14000bc3d  lea     rax, [rbx+80h]
0x14000bc44  mov     [rbx+5Bh], dil
0x14000bc48  mov     r14d, 1
0x14000bc4e  mov     [rbx+88h], rax
0x14000bc55  lea     rcx, [rbx+68h]; SpinLock
0x14000bc59  mov     [rbx+10h], r14
0x14000bc5d  call    cs:__imp_KeInitializeSpinLock
0x14000bc64  nop     dword ptr [rax+rax+00h]
0x14000bc69  mov     dword ptr [rbx+114h], 8
0x14000bc73  lea     rcx, [rbx+2D8h]
0x14000bc7a  mov     dword ptr [rbx+118h], 100000h
0x14000bc84  lea     rax, [rbx+120h]
0x14000bc8b  mov     [rbx+10h], r14
0x14000bc8f  xor     edx, edx
0x14000bc91  mov     [rbx+108h], rax
0x14000bc98  lea     rax, [rbx+310h]
0x14000bc9f  mov     [rbx+110h], edx
0x14000bca5  mov     [rbx+2F0h], rax
0x14000bcac  mov     [rbx+2D0h], rcx
0x14000bcb3  mov     [rcx+10h], edx
0x14000bcb6  mov     rax, [rbx+2D0h]
0x14000bcbd  mov     [rax+14h], dl
0x14000bcc0  mov     rax, [rbx+2D0h]
0x14000bcc7  mov     rcx, [rax+18h]
0x14000bccb  mov     dword ptr [rcx], 9
0x14000bcd1  mov     rax, [rbx+2D0h]
0x14000bcd8  mov     rcx, [rax+18h]
0x14000bcdc  mov     [rcx+18h], rbx
0x14000bce0  test    byte ptr [rbx+58h], 20h
0x14000bce4  jz      short loc_14000BD10
0x14000bce6  movzx   ecx, byte ptr [rbx+5Ah]
0x14000bcea  movzx   eax, byte ptr [rbx+5Bh]
0x14000bcee  test    r12b, r12b
0x14000bcf1  jnz     short loc_14000BCFD
0x14000bcf3  or      cl, 10h
0x14000bcf6  or      al, r14b
0x14000bcf9  and     al, 0FBh
0x14000bcfb  jmp     short loc_14000BD0A
0x14000bcfd  or      byte ptr [rbx+59h], 4
0x14000bd01  or      cl, 2
0x14000bd04  and     al, 0FDh
0x14000bd06  or      byte ptr [rbx+5Ch], 2
0x14000bd0a  mov     [rbx+5Bh], al
0x14000bd0d  mov     [rbx+5Ah], cl
0x14000bd10  movzx   eax, byte ptr [rbx+5Bh]
0x14000bd14  mov     r15d, [rbp+0A8h]
0x14000bd1b  test    al, 10h
0x14000bd1d  jz      short loc_14000BD27
0x14000bd1f  mov     r14d, 3
0x14000bd25  jmp     short loc_14000BD32
0x14000bd27  test    al, 8
0x14000bd29  mov     eax, 2
0x14000bd2e  cmovnz  r14d, eax
0x14000bd32  cmp     r15d, 1000h
0x14000bd39  jnz     short loc_14000BD6F
0x14000bd3b  cmp     r14d, 3
0x14000bd3f  jz      short loc_14000BD6F
0x14000bd41  mov     rcx, [rbp+48h]
0x14000bd45  add     rcx, 1E0h
0x14000bd4c  call    CxPlatPoolAlloc
0x14000bd51  mov     rsi, rax
0x14000bd54  test    rax, rax
0x14000bd57  jz      loc_14000BE2E
0x14000bd5d  and     byte ptr [rsi+14h], 0FCh
0x14000bd61  mov     [rax+10h], r15d
0x14000bd65  add     rax, 20h ; ' '
0x14000bd69  mov     [rsi+18h], rax
0x14000bd6d  xor     edx, edx
0x14000bd6f  test    byte ptr [rbx+58h], 20h
0x14000bd73  jz      short loc_14000BD7D
0x14000bd75  mov     eax, [rbp+0A4h]
0x14000bd7b  jmp     short loc_14000BD90
0x14000bd7d  test    r12b, r12b
0x14000bd80  jz      short loc_14000BD8A
0x14000bd82  mov     eax, [rbp+0A0h]
0x14000bd88  jmp     short loc_14000BD90
0x14000bd8a  mov     eax, [rbp+9Ch]
0x14000bd90  mov     [rbx+290h], eax
0x14000bd96  lea     rdi, [rbx+1C0h]
0x14000bd9d  mov     [rdi+0C0h], rdx
0x14000bda4  lea     rax, [rdi+38h]
0x14000bda8  mov     qword ptr [rdi+0C8h], 0
0x14000bdb3  mov     [rdi+0B8h], rdx
0x14000bdba  mov     [rdi+0D8h], r14d
0x14000bdc1  mov     [rdi+18h], rsi
0x14000bdc5  mov     [rdi+10h], rdx
0x14000bdc9  mov     [rdi+20h], rax
0x14000bdcd  mov     [rdi+28h], edx
0x14000bdd0  mov     dword ptr [rdi+2Ch], 8
0x14000bdd7  mov     dword ptr [rdi+30h], 100000h
0x14000bdde  mov     [rdi+8], rdi
0x14000bde2  mov     [rdi], rdi
0x14000bde5  cmp     r14d, 3
0x14000bde9  jz      loc_14000BE75
0x14000bdef  test    rsi, rsi
0x14000bdf2  jnz     short loc_14000BE62
0x14000bdf4  mov     r8d, 33316351h
0x14000bdfa  lea     rdx, [r15+20h]
0x14000bdfe  lea     ecx, [rsi+42h]
0x14000be01  call    cs:__imp_ExAllocatePool2
0x14000be08  nop     dword ptr [rax+rax+00h]
0x14000be0d  mov     rsi, rax
0x14000be10  test    rax, rax
0x14000be13  jnz     short loc_14000BE52
0x14000be15  test    cs:Microsoft_QuicEnableBits, 2
0x14000be1c  jz      short loc_14000BE2E
0x14000be1e  lea     r9, [r15+20h]
0x14000be22  lea     r8, aRecvBuffer; "recv_buffer"
0x14000be29  call    McTemplateU0sx_EtwWriteTransfer
0x14000be2e  mov     edi, 0C0000017h
0x14000be33  mov     rax, [rbp+48h]
0x14000be37  mov     rcx, rbx
0x14000be3a  lock dec qword ptr [rax+8E0h]
0x14000be42  or      byte ptr [rbx+5Ch], 40h
0x14000be46  call    CxPlatPoolFree
0x14000be4b  mov     eax, edi
0x14000be4d  jmp     loc_14000BEF6
0x14000be52  mov     [rax+10h], r15d
0x14000be56  add     rax, 20h ; ' '
0x14000be5a  and     byte ptr [rsi+14h], 0FCh
0x14000be5e  mov     [rsi+18h], rax
0x14000be62  mov     rax, [rdi]
0x14000be65  mov     [rsi], rax
0x14000be68  mov     [rsi+8], rdi
0x14000be6c  mov     [rax+8], rsi
0x14000be70  mov     [rdi], rsi
0x14000be73  jmp     short loc_14000BE78
0x14000be75  mov     r15d, edx
0x14000be78  mov     [rdi+0D4h], r15d
0x14000be7f  xor     ecx, ecx; PerformanceFrequency
0x14000be81  mov     eax, [rbx+290h]
0x14000be87  mov     [rbx+1A8h], rax
0x14000be8e  call    cs:__imp_KeQueryPerformanceCounter
0x14000be95  nop     dword ptr [rax+rax+00h]
0x14000be9a  mov     r9, qword ptr cs:CxPlatPerfFreq
0x14000bea1  xor     edx, edx
0x14000bea3  mov     rcx, rax
0x14000bea6  shr     rax, 20h
0x14000beaa  imul    r10, rax, 0F4240h
0x14000beb1  mov     rax, r10
0x14000beb4  div     r9
0x14000beb7  mov     eax, ecx
0x14000beb9  imul    rax, 0F4240h
0x14000bec0  shl     rdx, 20h
0x14000bec4  add     rax, rdx
0x14000bec7  xor     edx, edx
0x14000bec9  div     r9
0x14000becc  xor     edx, edx
0x14000bece  mov     rcx, rax
0x14000bed1  mov     rax, r10
0x14000bed4  div     r9
0x14000bed7  shl     rax, 20h
0x14000bedb  add     rcx, rax
0x14000bede  mov     [rbx+1B8h], rcx
0x14000bee5  lock inc dword ptr [rbp+0F0h]
0x14000beec  or      byte ptr [rbx+58h], 2
0x14000bef0  xor     eax, eax
0x14000bef2  mov     [r13+0], rbx
0x14000bef6  mov     r14, [rsp+0E8h+arg_8]
0x14000befe  mov     r15, [rsp+0E8h+var_38]
0x14000bf06  mov     rcx, [rsp+0E8h+var_48]
0x14000bf0e  xor     rcx, rsp; StackCookie
0x14000bf11  call    __security_check_cookie
0x14000bf16  add     rsp, 0B8h
0x14000bf1d  pop     r13
0x14000bf1f  pop     r12
0x14000bf21  pop     rdi
0x14000bf22  pop     rsi
0x14000bf23  pop     rbp
0x14000bf24  pop     rbx
0x14000bf25  retn
```
