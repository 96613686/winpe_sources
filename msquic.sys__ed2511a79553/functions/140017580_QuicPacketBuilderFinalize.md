# QuicPacketBuilderFinalize

- ea: `0x140017580`
- end: `0x14001803f`
- name: `QuicPacketBuilderFinalize`
- size: `2751`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140016210`
- `0x140016e30`
- `0x140049050`

## callees

- `0x140017580`
- `0x14001c638`
- `0x14001c664`
- `0x1400217f0`
- `0x140026f1c`
- `0x1400291f0`
- `0x1400337e4`
- `0x14003462c`
- `0x140034838`
- `0x140034e08`
- `0x140034f88`
- `0x140034fa4`
- `0x140034ff0`
- `0x1400351fc`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003fdf8`
- `0x140041de0`
- `0x140042878`
- `0x1400465f4`
- `0x140046774`
- `0x140048854`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140017ef3`
- `ntoskrnl!_snprintf_s` at `0x140017ef3`
- `HAL!KeQueryPerformanceCounter` at `0x140017bc1`
- `HAL!KeQueryPerformanceCounter` at `0x140017bc1`

## string_xrefs

- `0x140017b56`: `Send-triggered key update`

## pseudocode

```c
char __fastcall QuicPacketBuilderFinalize(unsigned __int64 a1, char a2)
{
  unsigned __int16 *v2; // r9
  __int64 v3; // r14
  char v4; // si
  unsigned __int64 v6; // rbx
  __int64 v7; // r11
  __int64 v8; // rbp
  _BYTE *v9; // rsi
  unsigned __int16 v10; // r10
  unsigned __int16 v11; // di
  unsigned __int16 v12; // di
  __int64 v13; // rdx
  __int64 v14; // r10
  __int16 v15; // cx
  UCHAR *pbInput; // rdi
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  char result; // al
  UCHAR *v21; // rdi
  _OWORD *v22; // r8
  char v23; // cl
  int v24; // edi
  unsigned __int8 v25; // cl
  unsigned __int8 v26; // r11
  unsigned __int8 v27; // r8
  _BYTE *v28; // rdx
  _BYTE *v29; // r10
  __int64 v30; // rax
  int v31; // r13d
  unsigned __int8 v32; // dl
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  int NewKeys; // eax
  __int64 v37; // rdx
  int v38; // ecx
  int v39; // edi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v41; // r9
  int v42; // ecx
  __int64 v43; // rcx
  unsigned int v44; // ecx
  unsigned int v45; // eax
  unsigned __int16 v46; // ax
  bool v47; // zf
  int v48; // eax
  __int64 v49; // rdx
  int v50; // edi
  unsigned __int8 v51; // cl
  unsigned __int8 v52; // r10
  unsigned __int8 v53; // r8
  _BYTE *v54; // rdx
  _BYTE *v55; // r11
  __int64 v56; // rax
  __int64 v57; // rcx
  unsigned int v58; // edi
  unsigned int v59; // esi
  volatile signed __int64 *v60; // rbp
  __int64 v61; // rcx
  __int64 v62; // rax
  char v63; // al
  char v64; // [rsp+40h] [rbp-F8h]
  char v65; // [rsp+41h] [rbp-F7h]
  char DstBuf[128]; // [rsp+80h] [rbp-B8h] BYREF

  v2 = *(unsigned __int16 **)(a1 + 32);
  v3 = *(_QWORD *)a1;
  v65 = 0;
  v4 = 1;
  v64 = 1;
  v6 = a1;
  if ( v2 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 408) + 90LL) )
    {
      v7 = *(unsigned __int16 *)(a1 + 378);
      LODWORD(v8) = (unsigned __int16)v7;
      LOWORD(v8) = v7 - *(_WORD *)(a1 + 386) - *(_WORD *)(a1 + 388);
      v9 = (_BYTE *)(*((_QWORD *)v2 + 1) + *(unsigned __int16 *)(a1 + 386));
      v10 = v7 + *(unsigned __int8 *)(a1 + 370);
      if ( !a2 && *(_BYTE *)(a1 + 376) != 0xFF )
      {
        a1 = *v2 - (unsigned int)v10;
        if ( (int)a1 >= 64 )
          goto LABEL_11;
      }
      v65 = 1;
      if ( !a2 && (unsigned __int8)CxPlatDataPathIsPaddingPreferred(qword_14005C590, *(_QWORD *)(v6 + 24)) )
        *(_WORD *)(v6 + 384) = *v2;
      v11 = *(_WORD *)(v6 + 384);
      if ( v10 < v11 )
      {
        v12 = v11 - v10;
      }
      else
      {
LABEL_11:
        v13 = *(unsigned __int8 *)(v6 + 377);
        a1 = v13 + (unsigned __int16)v8;
        if ( a1 >= 4 )
          goto LABEL_15;
        v12 = 4 - v13 - v8;
      }
      if ( v12 )
      {
        memset((void *)(*((_QWORD *)v2 + 1) + v7), 0, v12);
        LOWORD(v8) = v12 + v8;
        *(_WORD *)(v6 + 378) += v12;
      }
LABEL_15:
      if ( *(_BYTE *)(v6 + 376) != 0xFF )
      {
        a1 = *(unsigned __int8 *)(v6 + 377);
        LOWORD(a1) = __ROR2__((v8 + *(unsigned __int8 *)(v6 + 370) + (_WORD)a1) | 0x4000, 8);
        *(_WORD *)&v9[*(unsigned __int16 *)(v6 + 390)] = a1;
      }
      if ( byte_14005C48E < 0 )
      {
        QuicPacketLogHeader(
          (_DWORD *)v3,
          0,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 144LL) + 33LL),
          *(_QWORD *)(*(_QWORD *)(v6 + 408) + 16LL),
          *(_WORD *)(v6 + 388) + v8,
          (__int64)v9,
          *(_DWORD *)(v3 + 3636));
        QuicFrameLogAll(
          v3,
          0,
          *(_QWORD *)(*(_QWORD *)(v6 + 408) + 16LL),
          *(unsigned __int16 *)(v6 + 388) + (_DWORD)v8,
          (__int64)v9,
          *(_WORD *)(v6 + 388));
      }
      if ( !*(_BYTE *)(v6 + 370) || **(_DWORD **)(v6 + 40) == 3 && (*(_BYTE *)(v3 + 322) & 0x20) != 0 )
      {
        if ( (byte_14005C48F & 1) != 0 )
          McTemplateU0p_EtwWriteTransfer(a1, QuicPacketFinalize);
      }
      else
      {
        if ( (byte_14005C48F & 1) != 0 )
          McTemplateU0p_EtwWriteTransfer(a1, QuicPacketEncrypt);
        v14 = *(_QWORD *)(v6 + 40);
        v15 = *(unsigned __int8 *)(v6 + 370);
        *(_WORD *)(v6 + 378) += v15;
        v8 = (unsigned __int16)(v15 + v8);
        pbInput = &v9[*(unsigned __int16 *)(v6 + 388)];
        v17 = CxPlatEncrypt(*(BCRYPT_KEY_HANDLE *)(v14 + 8), v8, pbInput);
        if ( v17 < 0 )
        {
          QuicConnTryClose(v3, 18, v17, (unsigned int)"Encryption failure", 18);
          goto LABEL_26;
        }
        if ( (byte_14005C48F & 1) != 0 )
          McTemplateU0p_EtwWriteTransfer(v19, QuicPacketFinalize);
        if ( (*(_BYTE *)(v3 + 249) & 8) != 0 )
        {
          v21 = &pbInput[-*(unsigned __int8 *)(v6 + 377)];
          v22 = v21 + 4;
          if ( *(_BYTE *)(v6 + 376) == 0xFF )
          {
            *(_OWORD *)(16 * ((*(unsigned __int8 *)(v6 + 368) >> 2) & 0xFu) + v6 + 48) = *v22;
            *(_QWORD *)(v6 + 8 * (((unsigned __int64)*(unsigned __int8 *)(v6 + 368) >> 2) & 0xF) + 304) = v9;
            v23 = *(_BYTE *)(v6 + 368) ^ (*(_BYTE *)(v6 + 368) ^ (*(_BYTE *)(v6 + 368) + 4)) & 0x3C;
            *(_BYTE *)(v6 + 368) = v23;
            if ( (v23 & 0x3C) == 0x20 )
            {
              LOBYTE(v18) = 8;
              v24 = CxPlatHpComputeMask(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL), v18, v6 + 48, v6 + 176);
              if ( v24 >= 0 )
              {
                v25 = *(_BYTE *)(v6 + 368);
                v26 = 0;
                if ( (v25 & 0x3C) != 0 )
                {
                  do
                  {
                    v27 = 0;
                    v28 = *(_BYTE **)(v6 + 8LL * v26 + 304);
                    *v28 ^= *(_BYTE *)(v6 + 16LL * v26 + 176) & 0x1F;
                    v29 = &v28[*(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 144LL) + 33LL) + 1];
                    if ( *(_BYTE *)(v6 + 377) )
                    {
                      do
                      {
                        v30 = v27++;
                        v29[v30] ^= *(_BYTE *)(v6 + v30 + 16LL * v26 + 177);
                      }
                      while ( v27 < *(_BYTE *)(v6 + 377) );
                    }
                    v25 = *(_BYTE *)(v6 + 368);
                    ++v26;
                  }
                  while ( v26 < (unsigned __int8)((v25 >> 2) & 0xF) );
                }
                *(_BYTE *)(v6 + 368) = v25 & 0xC3;
              }
              else
              {
                CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\packet_builder.c", 674, "0");
                QuicConnTryClose(*(_QWORD *)v6, 18, v24, (unsigned int)"HP failure", 10);
              }
            }
          }
          else
          {
            LOBYTE(v18) = 1;
            v31 = CxPlatHpComputeMask(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL), v18, v22, v6 + 176);
            if ( v31 < 0 )
            {
              CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\packet_builder.c", 899, "0");
              QuicConnTryClose(v3, 18, v31, (unsigned int)"HP failure", 10);
              goto LABEL_26;
            }
            v32 = 0;
            *v9 ^= *(_BYTE *)(v6 + 176) & 0xF;
            if ( *(_BYTE *)(v6 + 377) )
            {
              do
              {
                v33 = v32++;
                v21[v33] ^= *(_BYTE *)(v33 + v6 + 177);
              }
              while ( v32 < *(_BYTE *)(v6 + 377) );
            }
          }
        }
        v34 = *(_QWORD *)(v3 + 8LL * *(int *)(v6 + 372) + 2760);
        v35 = *(_QWORD *)(v34 + 416) + v8 - *(unsigned __int8 *)(v6 + 370);
        *(_QWORD *)(v34 + 416) = v35;
        if ( *(_BYTE *)(v6 + 376) == 0xFF
          && (unsigned __int64)(v35 + 1500) >= *(_QWORD *)(v3 + 112)
          && (*(_BYTE *)(v34 + 424) & 2) == 0
          && (*(_BYTE *)(v3 + 250) & 2) != 0 )
        {
          NewKeys = QuicCryptoGenerateNewKeys(v3);
          v39 = NewKeys;
          if ( NewKeys < 0 )
          {
            if ( (byte_14005C48B & 4) != 0 )
              McTemplateU0pqs_EtwWriteTransfer(
                v38,
                (unsigned int)QuicConnErrorStatus,
                v3,
                NewKeys,
                (__int64)"Send-triggered key update");
            QuicConnTryClose(v3, 18, v39, (unsigned int)"Send-triggered key update", 25);
            goto LABEL_26;
          }
          LOBYTE(v37) = 1;
          QuicCryptoUpdateKeyPhase(v3, v37);
          *(_QWORD *)(v6 + 40) = *(_QWORD *)(v3 + 2944);
        }
      }
      PerformanceCounter = KeQueryPerformanceCounter(0);
      *(_QWORD *)(*(_QWORD *)(v6 + 408) + 32LL) = ((1000000
                                                  * HIDWORD(PerformanceCounter.QuadPart)
                                                  / (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32)
                                                + (1000000LL * PerformanceCounter.LowPart
                                                 + ((1000000 * HIDWORD(PerformanceCounter.QuadPart)
                                                   % (unsigned __int64)CxPlatPerfFreq.QuadPart) << 32))
                                                / CxPlatPerfFreq.QuadPart;
      *(_WORD *)(*(_QWORD *)(v6 + 408) + 40LL) = *(_WORD *)(v6 + 388) + v8;
      *(_BYTE *)(*(_QWORD *)(v6 + 408) + 89LL) ^= (*(_BYTE *)(*(_QWORD *)(v6 + 408) + 89LL)
                                                 ^ (*(_BYTE *)(v6 + 368) >> 6))
                                                & 1;
      if ( (byte_14005C48B & 8) != 0 )
      {
        v41 = *(_QWORD *)(v6 + 408);
        v42 = *(unsigned __int8 *)(v41 + 88);
        LOBYTE(v42) = v42 & 3;
        if ( (_BYTE)v42 == 3 )
          LOBYTE(v42) = 5;
        else
          LOBYTE(v42) = v42 + 1;
        McTemplateU0pxuh_EtwWriteTransfer(
          v42,
          (unsigned int)QuicConnPacketSent,
          v3,
          *(_QWORD *)(v41 + 16),
          v42,
          *(_WORD *)(v41 + 40));
      }
      QuicLossDetectionOnPacketSent(v3 + 2632, *(_QWORD *)(v6 + 8), *(_QWORD *)(v6 + 408));
      *(_BYTE *)(*(_QWORD *)(v6 + 408) + 90LL) = 0;
      v43 = *(_QWORD *)(v6 + 408);
      if ( (*(_BYTE *)(v43 + 88) & 4) != 0 )
      {
        *(_BYTE *)(v6 + 368) |= 2u;
        v44 = *(unsigned __int16 *)(v43 + 40);
        v45 = *(_DWORD *)(v6 + 392);
        if ( v44 <= v45 )
          *(_DWORD *)(v6 + 392) = v45 - v44;
        else
          *(_DWORD *)(v6 + 392) = 0;
      }
LABEL_26:
      if ( !v65 )
      {
        if ( !a2 )
          return 1;
LABEL_95:
        if ( *(_QWORD *)(v6 + 32) )
        {
          CxPlatSendDataFreeBuffer(*(_QWORD *)(v6 + 24));
          *(_QWORD *)(v6 + 32) = 0;
          *(_WORD *)(v6 + 378) = 0;
        }
        if ( *(_QWORD *)(v6 + 24) )
        {
          CxPlatSendDataFree();
          result = v64;
          *(_QWORD *)(v6 + 24) = 0;
          return result;
        }
        return v64;
      }
LABEL_71:
      if ( *(_QWORD *)(v6 + 32) )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v6 + 408) + 89LL) & 1) != 0 )
          ++*(_QWORD *)(v3 + 3440);
        **(_DWORD **)(v6 + 32) = *(unsigned __int16 *)(v6 + 378);
        v48 = *(unsigned __int16 *)(v6 + 378);
        ++*(_BYTE *)(v6 + 369);
        *(_DWORD *)(v6 + 380) += v48;
        *(_QWORD *)(v6 + 32) = 0;
        *(_WORD *)(v6 + 378) = 0;
      }
      if ( a2 || (unsigned __int8)CxPlatSendDataIsFull(*(_QWORD *)(v6 + 24)) )
      {
        v49 = *(unsigned __int8 *)(v6 + 368);
        LOBYTE(v49) = ((unsigned __int8)v49 >> 2) & 0xF;
        if ( (_BYTE)v49 )
        {
          v50 = CxPlatHpComputeMask(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 16LL), v49, v6 + 48, v6 + 176);
          if ( v50 >= 0 )
          {
            v51 = *(_BYTE *)(v6 + 368);
            v52 = 0;
            if ( (v51 & 0x3C) != 0 )
            {
              do
              {
                v53 = 0;
                v54 = *(_BYTE **)(v6 + 8LL * v52 + 304);
                *v54 ^= *(_BYTE *)(v6 + 16LL * v52 + 176) & 0x1F;
                v55 = &v54[*(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 144LL) + 33LL) + 1];
                if ( *(_BYTE *)(v6 + 377) )
                {
                  do
                  {
                    v56 = v53++;
                    v55[v56] ^= *(_BYTE *)(v6 + v56 + 16LL * v52 + 177);
                  }
                  while ( v53 < *(_BYTE *)(v6 + 377) );
                }
                v51 = *(_BYTE *)(v6 + 368);
                ++v52;
              }
              while ( v52 < (unsigned __int8)((v51 >> 2) & 0xF) );
            }
            *(_BYTE *)(v6 + 368) = v51 & 0xC3;
          }
          else
          {
            CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\packet_builder.c", 674, "0");
            QuicConnTryClose(*(_QWORD *)v6, 18, v50, (unsigned int)"HP failure", 10);
          }
        }
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Sending batch. %hu datagrams",
            *(unsigned __int8 *)(v6 + 369));
          McTemplateU0ps_EtwWriteTransfer(v57, QuicConnLogVerbose, *(_QWORD *)v6, DstBuf);
        }
        v58 = *(unsigned __int8 *)(v6 + 369);
        v59 = *(_DWORD *)(v6 + 380);
        v60 = *(volatile signed __int64 **)(*(_QWORD *)v6 + 72LL);
        CxPlatSocketSend(
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 40LL) + 32LL),
          *(_QWORD *)(v6 + 8) + 48LL,
          *(_QWORD *)(v6 + 24));
        _InterlockedAdd64(v60 + 289, v58);
        _InterlockedAdd64(v60 + 291, v59);
        _InterlockedIncrement64(v60 + 293);
        *(_BYTE *)(v6 + 368) |= 1u;
        v62 = *(_QWORD *)(v6 + 408);
        *(_QWORD *)(v6 + 24) = 0;
        *(_DWORD *)(v6 + 380) = 0;
        *(_BYTE *)(v62 + 90) = 0;
        if ( (byte_14005C48F & 1) != 0 )
          McTemplateU0p_EtwWriteTransfer(v61, QuicPacketBatchSent);
      }
      v63 = *(_BYTE *)(v6 + 376);
      if ( *(_DWORD *)(v3 + 3636) == -817679509 )
      {
        if ( v63 )
          return v64;
      }
      else if ( v63 != 3 )
      {
        return v64;
      }
      QuicConnCloseLocally(v3, 1, 0);
      return v64;
    }
    --*(_QWORD *)(v3 + 3424);
    v4 = 0;
    v46 = *(_WORD *)(a1 + 388);
    v47 = *(_WORD *)(a1 + 378) == v46;
    *(_WORD *)(a1 + 378) -= v46;
    *(_WORD *)(a1 + 388) = 0;
    v64 = 0;
    if ( v47 )
    {
      CxPlatSendDataFreeBuffer(*(_QWORD *)(a1 + 24));
      *(_QWORD *)(v6 + 32) = 0;
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)(v6 + 8) + 208LL) != -1 )
    QuicConnAddOutFlowBlockedReason(v3, 4);
  if ( a2 )
  {
    if ( !*(_BYTE *)(v6 + 369) )
      goto LABEL_95;
    goto LABEL_71;
  }
  return v4;
}

```

## disassembly

```asm
0x140017580  mov     [rsp+arg_8], rbx
0x140017585  mov     [rsp+arg_10], rbp
0x14001758a  mov     [rsp+arg_18], rsi
0x14001758f  push    rdi
0x140017590  push    r12
0x140017592  push    r13
0x140017594  push    r14
0x140017596  push    r15
0x140017598  sub     rsp, 110h
0x14001759f  mov     rax, cs:__security_cookie
0x1400175a6  xor     rax, rsp
0x1400175a9  mov     [rsp+138h+var_38], rax
0x1400175b1  mov     r9, [rcx+20h]
0x1400175b5  mov     ebp, 0Ah
0x1400175ba  mov     r14, [rcx]
0x1400175bd  xor     r15d, r15d
0x1400175c0  mov     [rsp+138h+var_F7], 0
0x1400175c5  mov     sil, 1
0x1400175c8  mov     [rsp+138h+var_F8], sil
0x1400175cd  movzx   r12d, dl
0x1400175d1  lea     r13d, [rbp+8]
0x1400175d5  mov     rbx, rcx
0x1400175d8  test    r9, r9
0x1400175db  jz      loc_140017D2E
0x1400175e1  mov     rax, [rcx+198h]
0x1400175e8  cmp     [rax+5Ah], r15b
0x1400175ec  jz      loc_140017CF9
0x1400175f2  movzx   r11d, word ptr [rcx+17Ah]
0x1400175fa  movzx   eax, word ptr [rcx+182h]
0x140017601  movzx   ebp, r11w
0x140017605  movzx   r10d, byte ptr [rcx+172h]
0x14001760d  sub     bp, ax
0x140017610  sub     bp, [rcx+184h]
0x140017617  mov     esi, eax
0x140017619  add     rsi, [r9+8]
0x14001761d  add     r10w, r11w
0x140017621  test    dl, dl
0x140017623  jnz     short loc_14001763D
0x140017625  cmp     byte ptr [rcx+178h], 0FFh
0x14001762c  jz      short loc_14001763D
0x14001762e  movzx   ecx, word ptr [r9]
0x140017632  movzx   eax, r10w
0x140017636  sub     ecx, eax
0x140017638  cmp     ecx, 40h ; '@'
0x14001763b  jge     short loc_140017679
0x14001763d  mov     [rsp+138h+var_F7], 1
0x140017642  test    r12b, r12b
0x140017645  jnz     short loc_140017666
0x140017647  mov     rdx, [rbx+18h]
0x14001764b  mov     rcx, cs:qword_14005C590
0x140017652  call    CxPlatDataPathIsPaddingPreferred
0x140017657  test    al, al
0x140017659  jz      short loc_140017666
0x14001765b  movzx   eax, word ptr [r9]
0x14001765f  mov     [rbx+180h], ax
0x140017666  movzx   edi, word ptr [rbx+180h]
0x14001766d  cmp     r10w, di
0x140017671  jnb     short loc_140017679
0x140017673  sub     di, r10w
0x140017677  jmp     short loc_140017697
0x140017679  movzx   edx, byte ptr [rbx+179h]
0x140017680  movzx   ecx, bp
0x140017683  add     rcx, rdx
0x140017686  cmp     rcx, 4
0x14001768a  jnb     short loc_1400176B8
0x14001768c  mov     edi, 4
0x140017691  sub     di, dx
0x140017694  sub     di, bp
0x140017697  test    di, di
0x14001769a  jz      short loc_1400176B8
0x14001769c  mov     rcx, r11
0x14001769f  movzx   r8d, di; Size
0x1400176a3  add     rcx, [r9+8]; void *
0x1400176a7  xor     edx, edx; Val
0x1400176a9  call    memset
0x1400176ae  add     bp, di
0x1400176b1  add     [rbx+17Ah], di
0x1400176b8  cmp     byte ptr [rbx+178h], 0FFh
0x1400176bf  jz      short loc_1400176EC
0x1400176c1  movzx   eax, byte ptr [rbx+172h]
0x1400176c8  movzx   ecx, byte ptr [rbx+179h]
0x1400176cf  add     cx, ax
0x1400176d2  mov     eax, 4000h
0x1400176d7  add     cx, bp
0x1400176da  or      cx, ax
0x1400176dd  movzx   eax, word ptr [rbx+186h]
0x1400176e4  ror     cx, 8
0x1400176e8  mov     [rax+rsi], cx
0x1400176ec  movzx   eax, cs:byte_14005C48E
0x1400176f3  test    al, al
0x1400176f5  jns     short loc_140017765
0x1400176f7  mov     rax, [rbx+8]
0x1400176fb  movzx   ecx, bp
0x1400176fe  add     cx, [rbx+184h]
0x140017705  xor     edx, edx
0x140017707  mov     r9, [rbx+198h]
0x14001770e  mov     r8, [rax+90h]
0x140017715  mov     eax, [r14+0E34h]
0x14001771c  mov     r9, [r9+10h]
0x140017720  mov     [rsp+138h+var_108], eax
0x140017724  movzx   r8d, byte ptr [r8+21h]
0x140017729  mov     [rsp+138h+pbInput], rsi
0x14001772e  mov     [rsp+138h+var_118], cx
0x140017733  mov     rcx, r14
0x140017736  call    QuicPacketLogHeader
0x14001773b  movzx   eax, word ptr [rbx+184h]
0x140017742  xor     edx, edx
0x140017744  mov     r8, [rbx+198h]
0x14001774b  mov     rcx, r14
0x14001774e  mov     word ptr [rsp+138h+pbInput], ax
0x140017753  mov     qword ptr [rsp+138h+var_118], rsi
0x140017758  lea     r9d, [rax+rbp]
0x14001775c  mov     r8, [r8+10h]
0x140017760  call    QuicFrameLogAll
0x140017765  cmp     [rbx+172h], r15b
0x14001776c  jz      loc_140017B9F
0x140017772  mov     rax, [rbx+28h]
0x140017776  cmp     dword ptr [rax], 3
0x140017779  jnz     short loc_140017789
0x14001777b  test    byte ptr [r14+142h], 20h
0x140017783  jnz     loc_140017B9F
0x140017789  test    cs:byte_14005C48F, 1
0x140017790  jz      short loc_1400177A9
0x140017792  mov     r8, [rbx+198h]
0x140017799  lea     rdx, QuicPacketEncrypt
0x1400177a0  mov     r8, [r8+8]
0x1400177a4  call    McTemplateU0p_EtwWriteTransfer
0x1400177a9  mov     r10, [rbx+28h]
0x1400177ad  mov     r9, rsi
0x1400177b0  mov     rdx, [rbx+198h]
0x1400177b7  movzx   ecx, byte ptr [rbx+172h]
0x1400177be  add     [rbx+17Ah], cx
0x1400177c5  movzx   r8d, word ptr [rbx+184h]
0x1400177cd  lea     eax, [rcx+rbp]
0x1400177d0  movzx   ebp, ax
0x1400177d3  movzx   eax, byte ptr [r10+18h]
0x1400177d8  lea     rdi, [rsi+r8]
0x1400177dc  mov     [rsp+138h+var_F0], al
0x1400177e0  movzx   eax, byte ptr [r10+19h]
0x1400177e5  mov     [rsp+138h+var_EF], al
0x1400177e9  movzx   eax, byte ptr [r10+1Ah]
0x1400177ee  mov     [rsp+138h+var_EE], al
0x1400177f2  movzx   eax, byte ptr [r10+1Bh]
0x1400177f7  mov     [rsp+138h+var_ED], al
0x1400177fb  movzx   ecx, byte ptr [r10+1Ch]
0x140017800  xor     cl, [rdx+17h]
0x140017803  mov     [rsp+138h+var_EC], cl
0x140017807  movzx   ecx, byte ptr [r10+1Dh]
0x14001780c  xor     cl, [rdx+16h]
0x14001780f  mov     [rsp+138h+var_EB], cl
0x140017813  movzx   ecx, byte ptr [r10+1Eh]
0x140017818  xor     cl, [rdx+15h]
0x14001781b  mov     [rsp+138h+var_EA], cl
0x14001781f  movzx   ecx, byte ptr [r10+1Fh]
0x140017824  xor     cl, [rdx+14h]
0x140017827  mov     [rsp+138h+var_E9], cl
0x14001782b  movzx   ecx, byte ptr [r10+20h]
0x140017830  xor     cl, [rdx+13h]
0x140017833  mov     [rsp+138h+var_E8], cl
0x140017837  movzx   ecx, byte ptr [r10+21h]
0x14001783c  xor     cl, [rdx+12h]
0x14001783f  mov     [rsp+138h+var_E7], cl
0x140017843  movzx   ecx, byte ptr [r10+22h]
0x140017848  xor     cl, [rdx+11h]
0x14001784b  mov     [rsp+138h+var_E6], cl
0x14001784f  movzx   ecx, byte ptr [r10+23h]
0x140017854  xor     cl, [rdx+10h]
0x140017857  lea     rdx, [rsp+138h+var_F0]
0x14001785c  mov     [rsp+138h+var_E5], cl
0x140017860  mov     rcx, [r10+8]; hKey
0x140017864  mov     [rsp+138h+pbInput], rdi; pbInput
0x140017869  mov     [rsp+138h+var_118], bp; __int16
0x14001786e  call    CxPlatEncrypt
0x140017873  test    eax, eax
0x140017875  jns     short loc_1400178B3
0x140017877  movsxd  r8, eax
0x14001787a  lea     r9, aEncryptionFail; "Encryption failure"
0x140017881  mov     [rsp+138h+var_118], r13w
0x140017887  mov     edx, r13d
0x14001788a  mov     rcx, r14
0x14001788d  call    QuicConnTryClose
0x140017892  mov     ebp, 0Ah
0x140017897  cmp     [rsp+138h+var_F7], r15b
0x14001789c  jnz     loc_140017D5E
0x1400178a2  cmp     r12b, 0
0x1400178a6  jnz     loc_140017FD4
0x1400178ac  mov     al, 1
0x1400178ae  jmp     loc_14001800D
0x1400178b3  test    cs:byte_14005C48F, 1
0x1400178ba  jz      short loc_1400178D3
0x1400178bc  mov     r8, [rbx+198h]
0x1400178c3  lea     rdx, QuicPacketFinalize
0x1400178ca  mov     r8, [r8+8]
0x1400178ce  call    McTemplateU0p_EtwWriteTransfer
0x1400178d3  test    byte ptr [r14+0F9h], 8
0x1400178db  jz      loc_140017AE1
0x1400178e1  movzx   eax, byte ptr [rbx+179h]
0x1400178e8  sub     rdi, rax
0x1400178eb  cmp     byte ptr [rbx+178h], 0FFh
0x1400178f2  lea     r8, [rdi+4]
0x1400178f6  jnz     loc_140017A49
0x1400178fc  movzx   eax, byte ptr [rbx+170h]
0x140017903  movups  xmm0, xmmword ptr [r8]
0x140017907  shr     eax, 2
0x14001790a  and     eax, 0Fh
0x14001790d  shl     eax, 4
0x140017910  movups  xmmword ptr [rax+rbx+30h], xmm0
0x140017915  movzx   eax, byte ptr [rbx+170h]
0x14001791c  shr     rax, 2
0x140017920  and     eax, 0Fh
0x140017923  mov     [rbx+rax*8+130h], rsi
0x14001792b  movzx   eax, byte ptr [rbx+170h]
0x140017932  lea     ecx, [rax+4]
0x140017935  xor     cl, al
0x140017937  and     cl, 3Ch
0x14001793a  xor     cl, al
0x14001793c  mov     [rbx+170h], cl
0x140017942  and     cl, 3Ch
0x140017945  cmp     cl, 20h ; ' '
0x140017948  jnz     loc_140017AE1
0x14001794e  mov     rcx, [rbx+28h]
0x140017952  lea     r9, [rbx+0B0h]
0x140017959  lea     r8, [rbx+30h]
0x14001795d  mov     dl, 8
0x14001795f  mov     rcx, [rcx+10h]
0x140017963  call    CxPlatHpComputeMask
0x140017968  movsxd  rdi, eax
0x14001796b  test    eax, eax
0x14001796d  jns     short loc_1400179A8
0x14001796f  lea     r8, a0; "0"
0x140017976  mov     edx, 2A2h
0x14001797b  lea     rcx, aCW1SMsquicSrcC_13; "C:\\__w\\1\\s\\msquic\\src\\core\\packe"...
0x140017982  call    CxPlatLogAssert
0x140017987  mov     rcx, [rbx]
0x14001798a  lea     r9, aHpFailure; "HP failure"
0x140017991  mov     r8, rdi
0x140017994  mov     [rsp+138h+var_118], 0Ah
0x14001799b  mov     edx, r13d
0x14001799e  call    QuicConnTryClose
0x1400179a3  jmp     loc_140017AE1
0x1400179a8  movzx   ecx, byte ptr [rbx+170h]
0x1400179af  xor     r11b, r11b
0x1400179b2  test    cl, 3Ch
0x1400179b5  jbe     loc_140017A3B
0x1400179bb  nop     dword ptr [rax+rax+00h]
0x1400179c0  movzx   eax, r11b
0x1400179c4  xor     r8b, r8b
0x1400179c7  movzx   r9d, r11b
0x1400179cb  add     r9, r9
0x1400179ce  mov     rdx, [rbx+rax*8+130h]
0x1400179d6  movzx   eax, byte ptr [rbx+r9*8+0B0h]
0x1400179df  and     al, 1Fh
0x1400179e1  xor     [rdx], al
0x1400179e3  mov     rax, [rbx+8]
0x1400179e7  mov     rcx, [rax+90h]
0x1400179ee  movzx   r10d, byte ptr [rcx+21h]
0x1400179f3  inc     r10
0x1400179f6  add     r10, rdx
0x1400179f9  cmp     [rbx+179h], r8b
0x140017a00  jbe     short loc_140017A24
0x140017a02  movzx   eax, r8b
0x140017a06  inc     r8b
0x140017a09  lea     rdx, [rax+r10]
0x140017a0d  add     rax, rbx
0x140017a10  movzx   ecx, byte ptr [rax+r9*8+0B1h]
0x140017a19  xor     [rdx], cl
0x140017a1b  cmp     r8b, [rbx+179h]
0x140017a22  jb      short loc_140017A02
0x140017a24  movzx   ecx, byte ptr [rbx+170h]
0x140017a2b  inc     r11b
0x140017a2e  movzx   eax, cl
0x140017a31  shr     al, 2
0x140017a34  and     al, 0Fh
0x140017a36  cmp     r11b, al
0x140017a39  jb      short loc_1400179C0
0x140017a3b  and     cl, 0C3h
0x140017a3e  mov     [rbx+170h], cl
0x140017a44  jmp     loc_140017AE1
0x140017a49  mov     rcx, [rbx+28h]
0x140017a4d  lea     r9, [rbx+0B0h]
0x140017a54  mov     dl, 1
0x140017a56  mov     rcx, [rcx+10h]
0x140017a5a  call    CxPlatHpComputeMask
0x140017a5f  movsxd  r13, eax
0x140017a62  test    eax, eax
0x140017a64  jns     short loc_140017AA8
0x140017a66  lea     r8, a0; "0"
0x140017a6d  mov     edx, 383h
0x140017a72  lea     rcx, aCW1SMsquicSrcC_13; "C:\\__w\\1\\s\\msquic\\src\\core\\packe"...
0x140017a79  call    CxPlatLogAssert
0x140017a7e  mov     r8, r13
0x140017a81  lea     r9, aHpFailure; "HP failure"
0x140017a88  mov     r13d, 12h
0x140017a8e  mov     ebp, 0Ah
0x140017a93  mov     edx, r13d
0x140017a96  mov     [rsp+138h+var_118], bp
0x140017a9b  mov     rcx, r14
0x140017a9e  call    QuicConnTryClose
0x140017aa3  jmp     loc_140017897
0x140017aa8  movzx   eax, byte ptr [rbx+0B0h]
  ... truncated ...
```
