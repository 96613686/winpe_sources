# QuicBindingProcessStatelessOperation

- ea: `0x1400401b4`
- end: `0x14004085e`
- name: `QuicBindingProcessStatelessOperation`
- size: `1706`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14002e380`

## callees

- `0x140026b8c`
- `0x140028658`
- `0x1400291b0`
- `0x14002d290`
- `0x1400337e4`
- `0x140033810`
- `0x14003462c`
- `0x140034ef8`
- `0x140034f68`
- `0x140034f88`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ead8`
- `0x14003ed00`
- `0x14003fd84`
- `0x1400401b4`
- `0x140040b80`
- `0x140041a20`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400403c2`
- `ntoskrnl!_snprintf_s` at `0x1400404e5`
- `ntoskrnl!_snprintf_s` at `0x1400407c4`
- `ntoskrnl!_snprintf_s` at `0x1400403c2`
- `ntoskrnl!_snprintf_s` at `0x1400404e5`
- `ntoskrnl!_snprintf_s` at `0x1400407c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040656`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040656`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004067a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400406c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004067a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400406c3`

## string_xrefs

- `0x14004078f`: `[S][TX][-] LH Ver:0x%x DestCid:%s SrcCid:%s Type:R OrigDestCid:%s (Token %hu bytes)`

## pseudocode

```c
__int64 __fastcall QuicBindingProcessStatelessOperation(__int64 a1, __int64 *a2)
{
  __int64 v2; // rsi
  int v3; // ebx
  __int64 v4; // r15
  char *v5; // r14
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r12
  unsigned int v11; // r13d
  unsigned __int16 v12; // bx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r15
  __int64 v17; // r9
  const char *v18; // r8
  __int64 v19; // rbx
  _BYTE *v20; // rdi
  _DWORD *v21; // rdi
  void *v22; // rdx
  int v23; // ebx
  __int64 v24; // rcx
  unsigned __int8 v25; // al
  __int64 v26; // rax
  _BYTE *v27; // rbx
  char v28; // dl
  __int64 v29; // r8
  __int64 v30; // r9
  const char *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  unsigned int v34; // ebx
  const void *v35; // rdx
  __int64 v36; // rax
  unsigned __int8 v37; // r9
  unsigned __int8 v38; // r8
  char *v39; // r10
  int v40; // ecx
  unsigned __int8 v41; // kr00_1
  char v42; // al
  void *CurrentStatelessRetryKey; // rax
  int v44; // ebx
  __int64 v45; // r8
  unsigned __int16 v46; // ax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // r8
  const char *v51; // rdi
  __int64 v52; // r9
  __int64 v53; // rax
  __int64 v54; // r8
  const char *v55; // rbx
  __int64 v56; // r9
  const char *v57; // rax
  __int64 v58; // rcx
  int v59; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v60; // [rsp+60h] [rbp-A0h]
  __int64 v61; // [rsp+68h] [rbp-98h]
  __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+78h] [rbp-88h]
  char v64; // [rsp+7Ch] [rbp-84h]
  __int16 v65; // [rsp+7Dh] [rbp-83h]
  char v66; // [rsp+7Fh] [rbp-81h]
  _BYTE v67[512]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v68[512]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v69[512]; // [rsp+480h] [rbp+380h] BYREF
  void *Src; // [rsp+680h] [rbp+580h] BYREF
  int v71; // [rsp+688h] [rbp+588h]
  char v72; // [rsp+68Ch] [rbp+58Ch] BYREF
  void *v73; // [rsp+690h] [rbp+590h] BYREF
  int v74; // [rsp+698h] [rbp+598h]
  char DstBuf[128]; // [rsp+6C0h] [rbp+5C0h] BYREF
  char v76[128]; // [rsp+740h] [rbp+640h] BYREF

  v2 = a2[11];
  v3 = a1;
  v4 = *a2;
  v61 = *a2;
  v5 = (char *)Val + 2496 * *(unsigned __int16 *)(v2 + 26);
  if ( (byte_14005C48D & 0x40) != 0 )
    McTemplateU0pq_EtwWriteTransfer(a1, QuicBindingExecOper, v4, (unsigned int)a1);
  v6 = *(_QWORD *)(v4 + 32);
  v62 = *(_QWORD *)(v2 + 8);
  v65 = 0;
  v66 = 0;
  v63 = 0;
  v64 = 0;
  result = CxPlatSendDataAlloc(v6, &v62);
  v10 = result;
  if ( result )
  {
    if ( v3 == 9 )
    {
      if ( (qword_14005C4B0 & 0x40000000) != 0 )
      {
        v11 = *(_DWORD *)(qword_14005C4B8 + 28);
        Src = *(void **)(qword_14005C4B8 + 8);
      }
      else
      {
        v11 = 4;
        Src = DefaultSupportedVersionsList;
      }
      v12 = *(unsigned __int8 *)(v2 + 86) + 11 + *(unsigned __int8 *)(v2 + 87) + 4 * v11;
      v13 = CxPlatSendDataAllocBuffer(result, v12);
      v16 = v13;
      if ( !v13 )
      {
        if ( (Microsoft_QuicEnableBits & 2) == 0 )
          return CxPlatSendDataFree(v10);
        v17 = v12;
        v18 = "vn datagram";
LABEL_13:
        McTemplateU0sx_EtwWriteTransfer(v15, v14, v18, v17);
        return CxPlatSendDataFree(v10);
      }
      v19 = *(_QWORD *)(v13 + 8);
      *(_BYTE *)v19 |= 0x80u;
      *(_DWORD *)(v19 + 1) = 0;
      *(_BYTE *)(v19 + 5) = *(_BYTE *)(v2 + 87);
      memmove((void *)(v19 + 6), *(const void **)(v2 + 72), *(unsigned __int8 *)(v2 + 87));
      v20 = (_BYTE *)(*(unsigned __int8 *)(v2 + 87) + v19 + 6);
      *v20++ = *(_BYTE *)(v2 + 86);
      memmove(v20, *(const void **)(v2 + 64), *(unsigned __int8 *)(v2 + 86));
      v21 = &v20[*(unsigned __int8 *)(v2 + 86)];
      CxPlatRandom(1u);
      v22 = Src;
      *(_BYTE *)v19 &= 0x80u;
      v23 = v61;
      *v21 = *(_DWORD *)(v61 + 24);
      memmove(v21 + 1, v22, 4LL * v11);
      *(_BYTE *)(v2 + 93) &= ~1u;
      if ( byte_14005C48E < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[S][TX][-] VN");
        McTemplateU0s_EtwWriteTransfer(v24, QuicLogVerbose, DstBuf);
      }
    }
    else
    {
      if ( v3 == 10 )
      {
        CxPlatRandom(1u);
        v60 = 41;
        v25 = 41;
        if ( *(_WORD *)(v2 + 80) <= 0x29u )
        {
          v25 = *(_BYTE *)(v2 + 80) - 1;
          v60 = v25;
        }
        if ( v25 < 0x15u )
          return CxPlatSendDataFree(v10);
        v26 = CxPlatSendDataAllocBuffer(v10, v25);
        v16 = v26;
        if ( !v26 )
        {
          if ( (Microsoft_QuicEnableBits & 2) == 0 )
            return CxPlatSendDataFree(v10);
          v17 = v60;
          v18 = "reset datagram";
          goto LABEL_13;
        }
        v27 = *(_BYTE **)(v26 + 8);
        CxPlatRandom(v60 - 16);
        v28 = *v27 & 0x3F | 0x40;
        *v27 = v28;
        *v27 = v28 ^ (**(_BYTE **)(v2 + 56) ^ v28) & 4;
        QuicLibraryGenerateStatelessResetToken(v5, *(_QWORD *)(v2 + 64), v60 - 16LL + *(_QWORD *)(v16 + 8));
        if ( byte_14005C48E < 0 )
        {
          LOBYTE(v29) = 16;
          v31 = (const char *)QuicCidBufToStr(v67, v60 - 16LL + *(_QWORD *)(v16 + 8), v29, v30);
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[S][TX][-] SR %s", v31);
          McTemplateU0s_EtwWriteTransfer(v32, QuicLogVerbose, DstBuf);
        }
        _InterlockedIncrement64((volatile signed __int64 *)v5 + 305);
      }
      else
      {
        if ( v3 != 11 )
        {
          CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\binding.c", 1047, "0");
          return CxPlatSendDataFree(v10);
        }
        v16 = CxPlatSendDataAllocBuffer(result, 147);
        if ( !v16 )
        {
          if ( (Microsoft_QuicEnableBits & 2) == 0 )
            return CxPlatSendDataFree(v10);
          v17 = 147;
          v18 = "retry datagram";
          goto LABEL_13;
        }
        CxPlatRandom(0xEu);
        memset(DstBuf, 0, 0x50u);
        v33 = CxPlatTimeEpochMs64();
        v34 = *(unsigned __int8 *)(v2 + 86);
        v35 = *(const void **)(v2 + 64);
        *(_QWORD *)DstBuf = 2 * v33;
        v36 = *(_QWORD *)(v2 + 8);
        *(_OWORD *)&DstBuf[8] = *(_OWORD *)(v36 + 8);
        *(_QWORD *)&DstBuf[24] = *(_QWORD *)(v36 + 24);
        *(_DWORD *)&DstBuf[32] = *(_DWORD *)(v36 + 32);
        memmove(&DstBuf[36], v35, v34);
        v37 = byte_14005C562;
        v38 = 12;
        DstBuf[56] = v34;
        if ( (unsigned __int8)byte_14005C562 < 0xCu )
        {
          v73 = 0;
          v74 = 0;
          memmove(&v73, &Src, (unsigned __int8)byte_14005C562);
        }
        else
        {
          v73 = Src;
          v74 = v71;
          if ( (unsigned __int8)byte_14005C562 > 0xCu )
          {
            v39 = &v72;
            do
            {
              v40 = v38;
              v41 = v38++;
              v42 = *v39++;
              *((_BYTE *)&v73 + (int)(v40 - 12 * (v41 / 0xCu))) ^= v42;
            }
            while ( v38 < v37 );
          }
        }
        v5[56] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5 + 6);
        CurrentStatelessRetryKey = (void *)QuicPartitionGetCurrentStatelessRetryKey(v5);
        if ( !CurrentStatelessRetryKey )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)v5 + 6, v5[56]);
          return CxPlatSendDataFree(v10);
        }
        v44 = CxPlatEncrypt(CurrentStatelessRetryKey, 68, (PUCHAR)&DstBuf[8]);
        KeReleaseSpinLock((PKSPIN_LOCK)v5 + 6, v5[56]);
        if ( v44 < 0 )
          return CxPlatSendDataFree(v10);
        LOBYTE(v45) = *(_BYTE *)(v2 + 87);
        LOBYTE(v59) = byte_14005C562;
        v46 = QuicPacketEncodeRetryV1(
                *(unsigned int *)(*(_QWORD *)(v2 + 56) + 1LL),
                *(_QWORD *)(v2 + 72),
                v45,
                &Src,
                v59,
                *(_QWORD *)(v2 + 64),
                *(_BYTE *)(v2 + 86));
        *(_DWORD *)v16 = v46;
        if ( !v46 )
          return CxPlatSendDataFree(v10);
        if ( byte_14005C48E < 0 )
        {
          LOBYTE(v47) = *(_BYTE *)(v2 + 86);
          v49 = QuicCidBufToStr(v67, *(_QWORD *)(v2 + 64), v47, v48);
          LOBYTE(v50) = byte_14005C562;
          v51 = (const char *)v49;
          v53 = QuicCidBufToStr(v68, &Src, v50, v52);
          LOBYTE(v54) = *(_BYTE *)(v2 + 87);
          v55 = (const char *)v53;
          v57 = (const char *)QuicCidBufToStr(v69, *(_QWORD *)(v2 + 72), v54, v56);
          _snprintf_s(
            v76,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "[S][TX][-] LH Ver:0x%x DestCid:%s SrcCid:%s Type:R OrigDestCid:%s (Token %hu bytes)",
            *(_DWORD *)(*(_QWORD *)(v2 + 56) + 1LL),
            v57,
            v55,
            v51,
            80);
          McTemplateU0s_EtwWriteTransfer(v58, QuicLogVerbose, v76);
        }
        _InterlockedIncrement64((volatile signed __int64 *)v5 + 306);
      }
      v23 = v61;
    }
    return QuicBindingSend(v23, (_DWORD)v5, *(_QWORD *)(v2 + 8), v10, *(_DWORD *)v16, 1);
  }
  if ( (Microsoft_QuicEnableBits & 2) != 0 )
    return McTemplateU0sx_EtwWriteTransfer(v9, v8, "stateless send data", 0);
  return result;
}

```

## disassembly

```asm
0x1400401b4  mov     [rsp-8+arg_10], rbx
0x1400401b9  push    rbp
0x1400401ba  push    rsi
0x1400401bb  push    rdi
0x1400401bc  push    r12
0x1400401be  push    r13
0x1400401c0  push    r14
0x1400401c2  push    r15
0x1400401c4  lea     rbp, [rsp-6D0h]
0x1400401cc  sub     rsp, 7D0h
0x1400401d3  mov     rax, cs:__security_cookie
0x1400401da  xor     rax, rsp
0x1400401dd  mov     [rbp+700h+var_40], rax
0x1400401e4  mov     rsi, [rdx+58h]
0x1400401e8  mov     ebx, ecx
0x1400401ea  mov     r15, [rdx]
0x1400401ed  mov     [rsp+800h+var_798], r15
0x1400401f2  movzx   eax, word ptr [rsi+1Ah]
0x1400401f6  imul    r14, rax, 9C0h
0x1400401fd  add     r14, cs:Val
0x140040204  test    cs:byte_14005C48D, 40h
0x14004020b  jz      short loc_14004021F
0x14004020d  mov     r9d, ecx
0x140040210  lea     rdx, QuicBindingExecOper
0x140040217  mov     r8, r15
0x14004021a  call    McTemplateU0pq_EtwWriteTransfer
0x14004021f  mov     rax, [rsi+8]
0x140040223  lea     rdx, [rsp+800h+var_790]
0x140040228  mov     rcx, [r15+20h]
0x14004022c  xor     r13d, r13d
0x14004022f  mov     [rsp+800h+var_790], rax
0x140040234  xor     eax, eax
0x140040236  mov     [rsp+800h+var_783], ax
0x14004023b  mov     [rsp+800h+var_781], al
0x14004023f  mov     [rsp+800h+var_788], r13d
0x140040244  mov     [rsp+800h+var_784], r13b
0x140040249  call    CxPlatSendDataAlloc
0x14004024e  mov     r12, rax
0x140040251  test    rax, rax
0x140040254  jnz     short loc_140040277
0x140040256  test    cs:Microsoft_QuicEnableBits, 2
0x14004025d  jz      loc_140040833
0x140040263  xor     r9d, r9d
0x140040266  lea     r8, aStatelessSendD; "stateless send data"
0x14004026d  call    McTemplateU0sx_EtwWriteTransfer
0x140040272  jmp     loc_140040833
0x140040277  cmp     ebx, 9
0x14004027a  jnz     loc_1400403E6
0x140040280  test    cs:qword_14005C4B0, 40000000h
0x14004028b  jz      short loc_1400402A5
0x14004028d  mov     rax, cs:qword_14005C4B8
0x140040294  mov     rdi, [rax+8]
0x140040298  mov     r13d, [rax+1Ch]
0x14004029c  mov     [rbp+700h+Src], rdi
0x1400402a3  jmp     short loc_1400402B9
0x1400402a5  lea     rax, DefaultSupportedVersionsList
0x1400402ac  mov     r13d, 4
0x1400402b2  mov     [rbp+700h+Src], rax
0x1400402b9  movzx   eax, byte ptr [rsi+57h]
0x1400402bd  movzx   ebx, r13w
0x1400402c1  shl     bx, 2
0x1400402c5  mov     rcx, r12
0x1400402c8  add     bx, ax
0x1400402cb  movzx   eax, byte ptr [rsi+56h]
0x1400402cf  add     ax, 0Bh
0x1400402d3  add     bx, ax
0x1400402d6  movzx   edx, bx
0x1400402d9  call    CxPlatSendDataAllocBuffer
0x1400402de  mov     r15, rax
0x1400402e1  test    rax, rax
0x1400402e4  jnz     short loc_140040308
0x1400402e6  test    cs:Microsoft_QuicEnableBits, 2
0x1400402ed  jz      loc_14004082B
0x1400402f3  movzx   r9d, bx
0x1400402f7  lea     r8, aVnDatagram; "vn datagram"
0x1400402fe  call    McTemplateU0sx_EtwWriteTransfer
0x140040303  jmp     loc_14004082B
0x140040308  mov     rbx, [rax+8]
0x14004030c  or      byte ptr [rbx], 80h
0x14004030f  lea     rdi, [rbx+6]
0x140040313  and     dword ptr [rbx+1], 0
0x140040317  mov     rcx, rdi; void *
0x14004031a  mov     al, [rsi+57h]
0x14004031d  mov     [rbx+5], al
0x140040320  movzx   r8d, byte ptr [rsi+57h]; Size
0x140040325  mov     rdx, [rsi+48h]; Src
0x140040329  call    memmove
0x14004032e  movzx   eax, byte ptr [rsi+57h]
0x140040332  add     rdi, rax
0x140040335  mov     al, [rsi+56h]
0x140040338  mov     [rdi], al
0x14004033a  inc     rdi
0x14004033d  movzx   r8d, byte ptr [rsi+56h]; Size
0x140040342  mov     rcx, rdi; void *
0x140040345  mov     rdx, [rsi+40h]; Src
0x140040349  call    memmove
0x14004034e  movzx   eax, byte ptr [rsi+56h]
0x140040352  lea     rdx, [rsp+800h+var_79F]
0x140040357  mov     ecx, 1; cbBuffer
0x14004035c  mov     [rsp+800h+var_79F], 0
0x140040361  add     rdi, rax
0x140040364  call    CxPlatRandom
0x140040369  mov     cl, [rbx]
0x14004036b  mov     al, [rsp+800h+var_79F]
0x14004036f  and     cl, 80h
0x140040372  mov     rdx, [rbp+700h+Src]; Src
0x140040379  and     al, 7Fh
0x14004037b  or      cl, al
0x14004037d  mov     r8d, r13d
0x140040380  mov     [rbx], cl
0x140040382  lea     rcx, [rdi+4]; void *
0x140040386  mov     rbx, [rsp+800h+var_798]
0x14004038b  shl     r8, 2; Size
0x14004038f  mov     eax, [rbx+18h]
0x140040392  mov     [rdi], eax
0x140040394  call    memmove
0x140040399  and     byte ptr [rsi+5Dh], 0FEh
0x14004039d  mov     al, cs:byte_14005C48E
0x1400403a3  test    al, al
0x1400403a5  jns     loc_1400407F0
0x1400403ab  lea     r9, aSTxVn; "[S][TX][-] VN"
0x1400403b2  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400403b6  mov     edx, 80h; SizeInBytes
0x1400403bb  lea     rcx, [rbp+700h+DstBuf]; DstBuf
0x1400403c2  call    cs:__imp__snprintf_s
0x1400403c9  nop     dword ptr [rax+rax+00h]
0x1400403ce  lea     r8, [rbp+700h+DstBuf]
0x1400403d5  lea     rdx, QuicLogVerbose
0x1400403dc  call    McTemplateU0s_EtwWriteTransfer
0x1400403e1  jmp     loc_1400407F0
0x1400403e6  cmp     ebx, 0Ah
0x1400403e9  jnz     loc_140040511
0x1400403ef  lea     rdx, [rsp+800h+var_7A0]
0x1400403f4  mov     [rsp+800h+var_7A0], r13b
0x1400403f9  lea     ecx, [rbx-9]; cbBuffer
0x1400403fc  call    CxPlatRandom
0x140040401  mov     al, [rsp+800h+var_7A0]
0x140040405  shr     al, 5
0x140040408  add     al, 29h ; ')'
0x14004040a  movzx   eax, al
0x14004040d  mov     [rsp+800h+var_7A0], al
0x140040411  cmp     ax, [rsi+50h]
0x140040415  jb      short loc_140040420
0x140040417  mov     al, [rsi+50h]
0x14004041a  dec     al
0x14004041c  mov     [rsp+800h+var_7A0], al
0x140040420  cmp     al, 15h
0x140040422  jb      loc_14004082B
0x140040428  movzx   edx, al
0x14004042b  mov     rcx, r12
0x14004042e  call    CxPlatSendDataAllocBuffer
0x140040433  mov     r15, rax
0x140040436  test    rax, rax
0x140040439  jnz     short loc_14004045A
0x14004043b  test    cs:Microsoft_QuicEnableBits, 2
0x140040442  jz      loc_14004082B
0x140040448  movzx   r9d, [rsp+800h+var_7A0]
0x14004044e  lea     r8, aResetDatagram; "reset datagram"
0x140040455  jmp     loc_1400402FE
0x14004045a  mov     rbx, [rax+8]
0x14004045e  movzx   ecx, [rsp+800h+var_7A0]
0x140040463  mov     rdx, rbx
0x140040466  sub     ecx, 10h; cbBuffer
0x140040469  call    CxPlatRandom
0x14004046e  mov     dl, [rbx]
0x140040470  and     dl, 3Fh
0x140040473  or      dl, 40h
0x140040476  mov     [rbx], dl
0x140040478  mov     cl, dl
0x14004047a  mov     rax, [rsi+38h]
0x14004047e  xor     cl, [rax]
0x140040480  and     cl, 4
0x140040483  xor     cl, dl
0x140040485  mov     [rbx], cl
0x140040487  movzx   ecx, [rsp+800h+var_7A0]
0x14004048c  mov     r8, [r15+8]
0x140040490  add     rcx, 0FFFFFFFFFFFFFFF0h
0x140040494  mov     rdx, [rsi+40h]
0x140040498  add     r8, rcx
0x14004049b  mov     rcx, r14
0x14004049e  call    QuicLibraryGenerateStatelessResetToken
0x1400404a3  mov     al, cs:byte_14005C48E
0x1400404a9  test    al, al
0x1400404ab  jns     short loc_140040504
0x1400404ad  movzx   ecx, [rsp+800h+var_7A0]
0x1400404b2  mov     r8b, 10h
0x1400404b5  mov     rdx, [r15+8]
0x1400404b9  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1400404bd  add     rdx, rcx
0x1400404c0  lea     rcx, [rbp+700h+var_780]
0x1400404c4  call    QuicCidBufToStr
0x1400404c9  lea     r9, aSTxSrS; "[S][TX][-] SR %s"
0x1400404d0  mov     qword ptr [rsp+800h+var_7E0], rax
0x1400404d5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400404d9  lea     rcx, [rbp+700h+DstBuf]; DstBuf
0x1400404e0  mov     edx, 80h; SizeInBytes
0x1400404e5  call    cs:__imp__snprintf_s
0x1400404ec  nop     dword ptr [rax+rax+00h]
0x1400404f1  lea     r8, [rbp+700h+DstBuf]
0x1400404f8  lea     rdx, QuicLogVerbose
0x1400404ff  call    McTemplateU0s_EtwWriteTransfer
0x140040504  lock inc qword ptr [r14+988h]
0x14004050c  jmp     loc_1400407EB
0x140040511  mov     eax, 0Bh
0x140040516  cmp     ebx, eax
0x140040518  jnz     loc_140040813
0x14004051e  mov     ebx, 93h
0x140040523  mov     rcx, r12
0x140040526  mov     edx, ebx
0x140040528  call    CxPlatSendDataAllocBuffer
0x14004052d  mov     r15, rax
0x140040530  test    rax, rax
0x140040533  jnz     short loc_140040551
0x140040535  test    cs:Microsoft_QuicEnableBits, 2
0x14004053c  jz      loc_14004082B
0x140040542  mov     r9d, ebx
0x140040545  lea     r8, aRetryDatagram; "retry datagram"
0x14004054c  jmp     loc_1400402FE
0x140040551  lea     rdx, [rbp+700h+Src]
0x140040558  mov     ecx, 0Eh; cbBuffer
0x14004055d  call    CxPlatRandom
0x140040562  xor     edx, edx; Val
0x140040564  lea     rcx, [rbp+700h+DstBuf]; void *
0x14004056b  lea     r8d, [rdx+50h]; Size
0x14004056f  call    memset
0x140040574  call    CxPlatTimeEpochMs64
0x140040579  movzx   ebx, byte ptr [rsi+56h]
0x14004057d  lea     rcx, [rbp+700h+var_11C]; void *
0x140040584  mov     rdx, [rsi+40h]; Src
0x140040588  add     rax, rax
0x14004058b  mov     qword ptr [rbp+700h+DstBuf], rax
0x140040592  mov     r8d, ebx; Size
0x140040595  mov     rax, [rsi+8]
0x140040599  movups  xmm0, xmmword ptr [rax+8]
0x14004059d  movups  xmmword ptr [rbp+700h+var_138], xmm0
0x1400405a4  movsd   xmm1, qword ptr [rax+18h]
0x1400405a9  movsd   [rbp+700h+var_128], xmm1
0x1400405b1  mov     eax, [rax+20h]
0x1400405b4  mov     [rbp+700h+var_120], eax
0x1400405ba  call    memmove
0x1400405bf  movzx   r9d, cs:byte_14005C562
0x1400405c7  mov     r8b, 0Ch
0x1400405ca  mov     [rbp+700h+var_108], bl
0x1400405d0  cmp     r9b, r8b
0x1400405d3  jb      short loc_14004062A
0x1400405d5  movsd   xmm0, [rbp+700h+Src]
0x1400405dd  mov     eax, [rbp+700h+var_178]
0x1400405e3  movsd   [rbp+700h+var_170], xmm0
0x1400405eb  mov     [rbp+700h+var_168], eax
0x1400405f1  jbe     short loc_14004064F
0x1400405f3  lea     r10, [rbp+700h+var_174]
0x1400405fa  movzx   ecx, r8b
0x1400405fe  mov     eax, 0AAAAAAABh
0x140040603  mul     ecx
0x140040605  inc     r8b
0x140040608  shr     edx, 3
0x14004060b  lea     eax, [rdx+rdx*2]
0x14004060e  shl     eax, 2
0x140040611  sub     ecx, eax
0x140040613  mov     al, [r10]
0x140040616  movsxd  rcx, ecx
0x140040619  inc     r10
0x14004061c  xor     byte ptr [rbp+rcx+700h+var_170], al
0x140040623  cmp     r8b, r9b
0x140040626  jb      short loc_1400405FA
0x140040628  jmp     short loc_14004064F
0x14004062a  xor     eax, eax
0x14004062c  lea     rdx, [rbp+700h+Src]; Src
0x140040633  mov     r8, r9; Size
0x140040636  mov     [rbp+700h+var_170], rax
0x14004063d  lea     rcx, [rbp+700h+var_170]; void *
0x140040644  mov     [rbp+700h+var_168], eax
0x14004064a  call    memmove
0x14004064f  lea     rdi, [r14+30h]
0x140040653  mov     rcx, rdi; SpinLock
0x140040656  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004065d  nop     dword ptr [rax+rax+00h]
0x140040662  mov     rcx, r14
0x140040665  mov     [r14+38h], al
0x140040669  call    QuicPartitionGetCurrentStatelessRetryKey
0x14004066e  test    rax, rax
0x140040671  jnz     short loc_14004068B
0x140040673  mov     dl, [r14+38h]; NewIrql
0x140040677  mov     rcx, rdi; SpinLock
0x14004067a  call    cs:__imp_KeReleaseSpinLock
0x140040681  nop     dword ptr [rax+rax+00h]
0x140040686  jmp     loc_14004082B
0x14004068b  lea     rcx, [rbp+700h+var_138]
0x140040692  mov     r8d, 8
0x140040698  mov     [rsp+800h+pbInput], rcx; pbInput
0x14004069d  lea     r9, [rbp+700h+DstBuf]
0x1400406a4  mov     rcx, rax; hKey
0x1400406a7  mov     [rsp+800h+var_7E0], 44h ; 'D'; __int16
0x1400406ae  lea     rdx, [rbp+700h+var_170]
0x1400406b5  call    CxPlatEncrypt
0x1400406ba  mov     dl, [r14+38h]; NewIrql
0x1400406be  mov     rcx, rdi; SpinLock
0x1400406c1  mov     ebx, eax
0x1400406c3  call    cs:__imp_KeReleaseSpinLock
0x1400406ca  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
