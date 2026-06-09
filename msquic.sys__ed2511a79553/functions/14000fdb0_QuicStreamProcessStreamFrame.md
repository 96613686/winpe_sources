# QuicStreamProcessStreamFrame

- ea: `0x14000fdb0`
- end: `0x140010435`
- name: `QuicStreamProcessStreamFrame`
- size: `1669`
- prototype: `__int64 __fastcall(__int64, char, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140027154`

## callees

- `0x14000a2b0`
- `0x14000c5b0`
- `0x14000fbc0`
- `0x14000fdb0`
- `0x14001c638`
- `0x1400290b4`
- `0x14002974c`
- `0x14002d92c`
- `0x14003c8e0`
- `0x14003ec10`
- `0x14003ed00`
- `0x140049624`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000fe66`
- `ntoskrnl!_snprintf_s` at `0x14000fec5`
- `ntoskrnl!_snprintf_s` at `0x1400100ac`
- `ntoskrnl!_snprintf_s` at `0x140010196`
- `ntoskrnl!_snprintf_s` at `0x1400102da`
- `ntoskrnl!_snprintf_s` at `0x140010327`
- `ntoskrnl!_snprintf_s` at `0x1400103bb`
- `ntoskrnl!_snprintf_s` at `0x14001040c`
- `ntoskrnl!_snprintf_s` at `0x14000fe66`
- `ntoskrnl!_snprintf_s` at `0x14000fec5`
- `ntoskrnl!_snprintf_s` at `0x1400100ac`
- `ntoskrnl!_snprintf_s` at `0x140010196`
- `ntoskrnl!_snprintf_s` at `0x1400102da`
- `ntoskrnl!_snprintf_s` at `0x140010327`
- `ntoskrnl!_snprintf_s` at `0x1400103bb`
- `ntoskrnl!_snprintf_s` at `0x14001040c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001024c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001024c`

## string_xrefs

- `0x1400102ad`: `Received %hu bytes, offset=%llu Ready=%hhu`
- `0x14001030f`: `Tried to write beyond end of buffer!`
- `0x1400103a3`: `Tried to write beyond flow control limit!`

## pseudocode

```c
__int64 __fastcall QuicStreamProcessStreamFrame(__int64 a1, char a2, char *a3)
{
  __int64 v4; // r8
  unsigned __int8 v5; // r12
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // r15
  char v11; // al
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // esi
  unsigned __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // r12
  int v21; // eax
  char v22; // cl
  _QWORD *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  char v26; // cl
  __int64 v27; // rdx
  __int64 v28; // rcx
  PSLIST_ENTRY v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  _QWORD *p_Next; // r15
  __int64 v33; // rdi
  __int64 v34; // r12
  KIRQL v35; // al
  _QWORD *v36; // rcx
  bool v37; // r13
  _QWORD *v38; // rax
  KIRQL v39; // dl
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rcx
  char v45; // [rsp+40h] [rbp-C0h] BYREF
  char v46; // [rsp+41h] [rbp-BFh]
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v49[128]; // [rsp+60h] [rbp-A0h] BYREF
  char DstBuf[128]; // [rsp+E0h] [rbp-20h] BYREF

  v46 = a2;
  v4 = *((_QWORD *)a3 + 3);
  v5 = 0;
  v45 = 0;
  v7 = *(unsigned __int8 *)(a1 + 90);
  v8 = *((_QWORD *)a3 + 2);
  v9 = v8 + v4;
  if ( (v7 & 0x10) != 0 )
  {
    if ( (byte_14005C48C & 0x10) != 0 )
      McTemplateU0ps_EtwWriteTransfer(v7, QuicStreamError, a1, "Receive on unidirectional stream");
    return 3221225860LL;
  }
  if ( (v7 & 0x60) != 0 )
  {
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(v49, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Ignoring recv after close");
      McTemplateU0ps_EtwWriteTransfer(v44, QuicStreamLogVerbose, a1, v49);
    }
    return 0;
  }
  v11 = *a3;
  if ( (v7 & 0x80u) == 0LL )
  {
    if ( v11 )
    {
      v14 = *(_QWORD *)(a1 + 680);
      if ( v14 != -1 && v9 != v14 )
      {
        v15 = -1073741811;
        goto LABEL_68;
      }
    }
    v16 = *(_QWORD *)(a1 + 680);
    if ( *(char *)(a1 + 89) >= 0 )
    {
      if ( v9 > v16 )
      {
        v15 = -1073741811;
        goto LABEL_68;
      }
    }
    else if ( *(_QWORD *)(a1 + 640) >= v16 )
    {
      return 0;
    }
    if ( v9 > 0x3FFFFFFFFFFFFFFFLL )
    {
      QuicConnCloseLocally(*(_QWORD *)(a1 + 72), 2, 3);
      v15 = -1073741811;
      goto LABEL_68;
    }
    v17 = 0;
    if ( v4 )
    {
      v18 = *(_QWORD *)(a1 + 72);
      v19 = *((_QWORD *)a3 + 4);
      v48[0] = 0;
      v47 = 0;
      v20 = *(_QWORD *)(v18 + 3448) - *(_QWORD *)(v18 + 3464);
      v15 = QuicRecvBufferWrite((int)a1 + 448, v8, v4, v19, v20, (__int64)v48, (__int64)&v45, (__int64)&v47);
      if ( v47 && *(_DWORD *)(a1 + 664) == 3 )
      {
        QuicStreamNotifyReceiveBufferNeeded(a1);
        if ( *(char *)(a1 + 90) < 0 )
          return 0;
        v15 = QuicRecvBufferWrite(
                (int)a1 + 448,
                *((_QWORD *)a3 + 2),
                *((unsigned __int16 *)a3 + 12),
                *((_QWORD *)a3 + 4),
                v20,
                (__int64)v48,
                (__int64)&v45,
                (__int64)&v47);
      }
      if ( v15 < 0 )
      {
LABEL_67:
        if ( v15 != -1073741811 )
        {
          if ( v15 != -1073741789 )
            return (unsigned int)v15;
          if ( (byte_14005C48C & 0x40) != 0 )
          {
            _snprintf_s(v49, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Tried to write beyond flow control limit!");
            McTemplateU0ps_EtwWriteTransfer(v43, QuicStreamLogWarning, a1, v49);
          }
          v42 = 3;
LABEL_71:
          QuicConnCloseLocally(*(_QWORD *)(a1 + 72), 2, v42);
          return (unsigned int)v15;
        }
LABEL_68:
        if ( (byte_14005C48C & 0x40) != 0 )
        {
          _snprintf_s(v49, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Tried to write beyond end of buffer!");
          McTemplateU0ps_EtwWriteTransfer(v41, QuicStreamLogWarning, a1, v49);
        }
        v42 = 6;
        goto LABEL_71;
      }
      *(_QWORD *)(*(_QWORD *)(a1 + 72) + 3464LL) += v48[0];
      v21 = *(_DWORD *)(a1 + 488);
      if ( v21 )
      {
        v22 = 1;
        v23 = (_QWORD *)(*(_QWORD *)(a1 + 480) + 16LL * (unsigned int)(v21 - 1));
        v17 = v23[1] + *v23 - 1LL;
      }
      else
      {
        v22 = 0;
      }
      v24 = v17 + 1;
      if ( !v22 )
        v24 = v17;
      if ( v24 == *(_QWORD *)(a1 + 424) && (byte_14005C48D & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Flow control window exhausted!");
        McTemplateU0ps_EtwWriteTransfer(v25, QuicStreamLogVerbose, a1, DstBuf);
      }
      if ( v46 && v9 > *(_QWORD *)(a1 + 672) )
        *(_QWORD *)(a1 + 672) = v9;
      v5 = v45;
      *(_QWORD *)(*(_QWORD *)(a1 + 72) + 3840LL) += *((_QWORD *)a3 + 3);
    }
    else
    {
      v15 = 0;
    }
    if ( *a3 && (*(_QWORD *)(a1 + 680) = v9, *(_QWORD *)(a1 + 640) == v9) )
    {
      v5 = 1;
      v45 = 1;
    }
    else if ( !v5 )
    {
LABEL_65:
      if ( (byte_14005C48D & 1) != 0 )
      {
        _snprintf_s(
          v49,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Received %hu bytes, offset=%llu Ready=%hhu",
          *((unsigned __int16 *)a3 + 12),
          *((_QWORD *)a3 + 2),
          v5);
        McTemplateU0ps_EtwWriteTransfer(v40, QuicStreamLogVerbose, a1, v49);
      }
      goto LABEL_67;
    }
    if ( *(_DWORD *)(a1 + 664) == 2 || !*(_QWORD *)(a1 + 632) )
    {
      v26 = *(_BYTE *)(a1 + 91);
      v27 = *(_QWORD *)(a1 + 680);
      *(_BYTE *)(a1 + 91) = v26 | 0x40;
      if ( (v26 & 4) != 0 )
      {
        if ( *(_QWORD *)(a1 + 640) == v27 )
        {
          QuicStreamRecvFlush(a1);
        }
        else if ( (v26 & 0x20) == 0 )
        {
          if ( (byte_14005C48D & 1) != 0 )
          {
            _snprintf_s(v49, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Queuing recv flush");
            McTemplateU0ps_EtwWriteTransfer(v28, QuicStreamLogVerbose, a1, v49);
          }
          v29 = CxPlatPoolAlloc(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 72LL) + 2016LL);
          p_Next = &v29->Next;
          if ( v29 )
          {
            LODWORD(v29[1].Next) = 3;
            BYTE4(v29[1].Next) = 1;
            *((_QWORD *)&v29[1].Next + 1) = a1;
            CxPlatRefIncrement(a1 + 16);
            v33 = *(_QWORD *)(a1 + 72);
            v34 = *(_QWORD *)(v33 + 72);
            v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v33 + 1432));
            v36 = (_QWORD *)(v33 + 1448);
            *(_BYTE *)(v33 + 1440) = v35;
            v37 = (_QWORD *)*v36 == v36 && !*(_BYTE *)(v33 + 1424);
            v38 = *(_QWORD **)(v33 + 1456);
            *p_Next = v36;
            p_Next[1] = v38;
            *v38 = p_Next;
            v39 = *(_BYTE *)(v33 + 1440);
            *(_QWORD *)(v33 + 1456) = p_Next;
            KeReleaseSpinLock((PKSPIN_LOCK)(v33 + 1432), v39);
            _InterlockedIncrement64((volatile signed __int64 *)(v34 + 2384));
            _InterlockedIncrement64((volatile signed __int64 *)(v34 + 2376));
            if ( v37 )
              QuicWorkerQueueConnection(*(_QWORD *)(v33 + 64), v33);
            *(_BYTE *)(a1 + 91) |= 0x20u;
            v5 = v45;
          }
          else if ( (Microsoft_QuicEnableBits & 2) != 0 )
          {
            McTemplateU0sx_EtwWriteTransfer(v31, v30, "Flush Stream Recv operation", 0);
          }
        }
      }
    }
    goto LABEL_65;
  }
  if ( !v11 )
  {
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Ignoring received frame after receive abort");
      McTemplateU0ps_EtwWriteTransfer(v13, QuicStreamLogVerbose, a1, DstBuf);
      return 0;
    }
    return 0;
  }
  if ( byte_14005C48C < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Treating FIN after receive abort as reset");
    McTemplateU0ps_EtwWriteTransfer(v12, QuicStreamLogInfo, a1, DstBuf);
  }
  QuicStreamProcessResetFrame(a1, *((_QWORD *)a3 + 3) + *((_QWORD *)a3 + 2), 0);
  return 0;
}

```

## disassembly

```asm
0x14000fdb0  push    rbp
0x14000fdb2  push    rbx
0x14000fdb3  push    r12
0x14000fdb5  push    r14
0x14000fdb7  push    r15
0x14000fdb9  lea     rbp, [rsp-80h]
0x14000fdbe  sub     rsp, 180h
0x14000fdc5  mov     rax, cs:__security_cookie
0x14000fdcc  xor     rax, rsp
0x14000fdcf  mov     [rbp+0A0h+var_40], rax
0x14000fdd3  mov     r14, r8
0x14000fdd6  mov     [rsp+1A0h+var_15F], dl
0x14000fdda  mov     r8, [r8+18h]
0x14000fdde  xor     r12b, r12b
0x14000fde1  mov     rbx, rcx
0x14000fde4  mov     [rsp+1A0h+var_160], r12b
0x14000fde9  movzx   ecx, byte ptr [rcx+5Ah]
0x14000fded  mov     rdx, [r14+10h]
0x14000fdf1  lea     r15, [rdx+r8]
0x14000fdf5  test    cl, 10h
0x14000fdf8  jz      short loc_14000FE23
0x14000fdfa  test    cs:byte_14005C48C, 10h
0x14000fe01  jz      short loc_14000FE19
0x14000fe03  lea     r9, aReceiveOnUnidi; "Receive on unidirectional stream"
0x14000fe0a  mov     r8, rbx
0x14000fe0d  lea     rdx, QuicStreamError
0x14000fe14  call    McTemplateU0ps_EtwWriteTransfer
0x14000fe19  mov     eax, 0C0000184h
0x14000fe1e  jmp     loc_140010375
0x14000fe23  mov     [rsp+1A0h+var_28], rdi
0x14000fe2b  test    cl, 60h
0x14000fe2e  jnz     loc_1400103EB
0x14000fe34  movzx   eax, byte ptr [r14]
0x14000fe38  test    cl, cl
0x14000fe3a  jns     loc_14000FEED
0x14000fe40  test    al, al
0x14000fe42  jz      short loc_14000FEA1
0x14000fe44  movzx   eax, cs:byte_14005C48C
0x14000fe4b  test    al, al
0x14000fe4d  jns     short loc_14000FE85
0x14000fe4f  lea     r9, aTreatingFinAft; "Treating FIN after receive abort as res"...
0x14000fe56  mov     edx, 80h; SizeInBytes
0x14000fe5b  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000fe62  lea     rcx, [rbp+0A0h+DstBuf]; DstBuf
0x14000fe66  call    cs:__imp__snprintf_s
0x14000fe6d  nop     dword ptr [rax+rax+00h]
0x14000fe72  lea     r9, [rbp+0A0h+DstBuf]
0x14000fe76  mov     r8, rbx
0x14000fe79  lea     rdx, QuicStreamLogInfo
0x14000fe80  call    McTemplateU0ps_EtwWriteTransfer
0x14000fe85  mov     rdx, [r14+10h]
0x14000fe89  xor     r8d, r8d
0x14000fe8c  add     rdx, [r14+18h]
0x14000fe90  mov     rcx, rbx
0x14000fe93  call    QuicStreamProcessResetFrame
0x14000fe98  xor     edi, edi
0x14000fe9a  mov     eax, edi
0x14000fe9c  jmp     loc_14001036D
0x14000fea1  test    cs:byte_14005C48D, 1
0x14000fea8  jz      loc_14001042C
0x14000feae  lea     r9, aIgnoringReceiv_2; "Ignoring received frame after receive a"...
0x14000feb5  mov     edx, 80h; SizeInBytes
0x14000feba  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000fec1  lea     rcx, [rbp+0A0h+DstBuf]; DstBuf
0x14000fec5  call    cs:__imp__snprintf_s
0x14000fecc  nop     dword ptr [rax+rax+00h]
0x14000fed1  lea     r9, [rbp+0A0h+DstBuf]
0x14000fed5  mov     r8, rbx
0x14000fed8  lea     rdx, QuicStreamLogVerbose
0x14000fedf  call    McTemplateU0ps_EtwWriteTransfer
0x14000fee4  xor     edi, edi
0x14000fee6  mov     eax, edi
0x14000fee8  jmp     loc_14001036D
0x14000feed  mov     [rsp+1A0h+arg_8], rsi
0x14000fef5  mov     [rsp+1A0h+var_30], r13
0x14000fefd  test    al, al
0x14000feff  jz      short loc_14000FF1D
0x14000ff01  mov     rax, [rbx+2A8h]
0x14000ff08  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ff0c  jz      short loc_14000FF1D
0x14000ff0e  cmp     r15, rax
0x14000ff11  jz      short loc_14000FF1D
0x14000ff13  mov     esi, 0C000000Dh
0x14000ff18  jmp     loc_140010306
0x14000ff1d  mov     rax, [rbx+2A8h]
0x14000ff24  cmp     [rbx+59h], r12b
0x14000ff28  jge     short loc_14000FF3C
0x14000ff2a  cmp     [rbx+280h], rax
0x14000ff31  jb      short loc_14000FF4B
0x14000ff33  xor     edi, edi
0x14000ff35  mov     eax, edi
0x14000ff37  jmp     loc_14001035D
0x14000ff3c  cmp     r15, rax
0x14000ff3f  jbe     short loc_14000FF4B
0x14000ff41  mov     esi, 0C000000Dh
0x14000ff46  jmp     loc_140010306
0x14000ff4b  mov     rax, 3FFFFFFFFFFFFFFFh
0x14000ff55  cmp     r15, rax
0x14000ff58  jbe     short loc_14000FF78
0x14000ff5a  mov     rcx, [rbx+48h]
0x14000ff5e  xor     r9d, r9d
0x14000ff61  lea     edx, [r9+2]
0x14000ff65  lea     r8d, [r9+3]
0x14000ff69  call    QuicConnCloseLocally
0x14000ff6e  mov     esi, 0C000000Dh
0x14000ff73  jmp     loc_140010306
0x14000ff78  xor     edi, edi
0x14000ff7a  test    r8, r8
0x14000ff7d  jnz     short loc_14000FF86
0x14000ff7f  mov     esi, edi
0x14000ff81  jmp     loc_1400100F7
0x14000ff86  mov     rax, [rbx+48h]
0x14000ff8a  lea     rcx, [rbx+1C0h]
0x14000ff91  mov     r9, [r14+20h]
0x14000ff95  mov     [rsp+1A0h+var_150], rdi
0x14000ff9a  mov     [rsp+1A0h+var_158], rdi
0x14000ff9f  mov     r12, [rax+0D78h]
0x14000ffa6  sub     r12, [rax+0D88h]
0x14000ffad  lea     rax, [rsp+1A0h+var_158]
0x14000ffb2  mov     [rsp+1A0h+var_168], rax
0x14000ffb7  lea     rax, [rsp+1A0h+var_160]
0x14000ffbc  mov     [rsp+1A0h+var_170], rax
0x14000ffc1  lea     rax, [rsp+1A0h+var_150]
0x14000ffc6  mov     [rsp+1A0h+var_178], rax
0x14000ffcb  mov     [rsp+1A0h+var_180], r12
0x14000ffd0  call    QuicRecvBufferWrite
0x14000ffd5  mov     rdx, [rsp+1A0h+var_158]
0x14000ffda  mov     esi, eax
0x14000ffdc  test    rdx, rdx
0x14000ffdf  jz      short loc_14001003A
0x14000ffe1  cmp     dword ptr [rbx+298h], 3
0x14000ffe8  jnz     short loc_14001003A
0x14000ffea  mov     rcx, rbx
0x14000ffed  call    QuicStreamNotifyReceiveBufferNeeded
0x14000fff2  cmp     [rbx+5Ah], dil
0x14000fff6  jl      loc_14000FF35
0x14000fffc  mov     r9, [r14+20h]
0x140010000  lea     rax, [rsp+1A0h+var_158]
0x140010005  movzx   r8d, word ptr [r14+18h]
0x14001000a  lea     rcx, [rbx+1C0h]
0x140010011  mov     rdx, [r14+10h]
0x140010015  mov     [rsp+1A0h+var_168], rax
0x14001001a  lea     rax, [rsp+1A0h+var_160]
0x14001001f  mov     [rsp+1A0h+var_170], rax
0x140010024  lea     rax, [rsp+1A0h+var_150]
0x140010029  mov     [rsp+1A0h+var_178], rax
0x14001002e  mov     [rsp+1A0h+var_180], r12
0x140010033  call    QuicRecvBufferWrite
0x140010038  mov     esi, eax
0x14001003a  test    esi, esi
0x14001003c  js      loc_1400102FA
0x140010042  mov     rax, [rsp+1A0h+var_150]
0x140010047  mov     rcx, [rbx+48h]
0x14001004b  add     [rcx+0D88h], rax
0x140010052  mov     eax, [rbx+1E8h]
0x140010058  test    eax, eax
0x14001005a  jz      short loc_140010077
0x14001005c  dec     eax
0x14001005e  mov     cl, 1
0x140010060  shl     rax, 4
0x140010064  add     rax, [rbx+1E0h]
0x14001006b  mov     rdi, [rax]
0x14001006e  dec     rdi
0x140010071  add     rdi, [rax+8]
0x140010075  jmp     short loc_140010079
0x140010077  xor     cl, cl
0x140010079  test    cl, cl
0x14001007b  lea     rax, [rdi+1]
0x14001007f  cmovz   rax, rdi
0x140010083  cmp     rax, [rbx+1A8h]
0x14001008a  jnz     short loc_1400100CB
0x14001008c  test    cs:byte_14005C48D, 1
0x140010093  jz      short loc_1400100CB
0x140010095  lea     r9, aFlowControlWin; "Flow control window exhausted!"
0x14001009c  mov     edx, 80h; SizeInBytes
0x1400100a1  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400100a8  lea     rcx, [rbp+0A0h+DstBuf]; DstBuf
0x1400100ac  call    cs:__imp__snprintf_s
0x1400100b3  nop     dword ptr [rax+rax+00h]
0x1400100b8  lea     r9, [rbp+0A0h+DstBuf]
0x1400100bc  mov     r8, rbx
0x1400100bf  lea     rdx, QuicStreamLogVerbose
0x1400100c6  call    McTemplateU0ps_EtwWriteTransfer
0x1400100cb  cmp     [rsp+1A0h+var_15F], 0
0x1400100d0  jz      short loc_1400100E2
0x1400100d2  cmp     r15, [rbx+2A0h]
0x1400100d9  jbe     short loc_1400100E2
0x1400100db  mov     [rbx+2A0h], r15
0x1400100e2  mov     rcx, [rbx+48h]
0x1400100e6  mov     rax, [r14+18h]
0x1400100ea  movzx   r12d, [rsp+1A0h+var_160]
0x1400100f0  add     [rcx+0F00h], rax
0x1400100f7  cmp     byte ptr [r14], 0
0x1400100fb  jz      short loc_140010117
0x1400100fd  mov     [rbx+2A8h], r15
0x140010104  cmp     [rbx+280h], r15
0x14001010b  jnz     short loc_140010117
0x14001010d  mov     r12b, 1
0x140010110  mov     [rsp+1A0h+var_160], r12b
0x140010115  jmp     short loc_140010120
0x140010117  test    r12b, r12b
0x14001011a  jz      loc_14001029F
0x140010120  cmp     dword ptr [rbx+298h], 2
0x140010127  jz      short loc_140010137
0x140010129  cmp     qword ptr [rbx+278h], 0
0x140010131  jnz     loc_14001029F
0x140010137  movzx   ecx, byte ptr [rbx+5Bh]
0x14001013b  mov     rdx, [rbx+2A8h]
0x140010142  movzx   eax, cl
0x140010145  or      al, 40h
0x140010147  mov     [rbx+5Bh], al
0x14001014a  mov     rax, [rbx+280h]
0x140010151  test    cl, 4
0x140010154  jz      loc_14001029F
0x14001015a  cmp     rax, rdx
0x14001015d  jnz     short loc_14001016C
0x14001015f  mov     rcx, rbx
0x140010162  call    QuicStreamRecvFlush
0x140010167  jmp     loc_14001029F
0x14001016c  test    cl, 20h
0x14001016f  jnz     loc_14001029F
0x140010175  test    cs:byte_14005C48D, 1
0x14001017c  jz      short loc_1400101B6
0x14001017e  lea     r9, aQueuingRecvFlu; "Queuing recv flush"
0x140010185  mov     edx, 80h; SizeInBytes
0x14001018a  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140010191  lea     rcx, [rsp+1A0h+var_140]; DstBuf
0x140010196  call    cs:__imp__snprintf_s
0x14001019d  nop     dword ptr [rax+rax+00h]
0x1400101a2  lea     r9, [rsp+1A0h+var_140]
0x1400101a7  mov     r8, rbx
0x1400101aa  lea     rdx, QuicStreamLogVerbose
0x1400101b1  call    McTemplateU0ps_EtwWriteTransfer
0x1400101b6  mov     rax, [rbx+48h]
0x1400101ba  mov     rcx, [rax+48h]
0x1400101be  add     rcx, 7E0h
0x1400101c5  call    CxPlatPoolAlloc
0x1400101ca  mov     r15, rax
0x1400101cd  test    rax, rax
0x1400101d0  jz      loc_140010287
0x1400101d6  mov     dword ptr [rax+10h], 3
0x1400101dd  lea     rcx, [rbx+10h]
0x1400101e1  mov     byte ptr [rax+14h], 1
0x1400101e5  mov     [rax+18h], rbx
0x1400101e9  call    CxPlatRefIncrement
0x1400101ee  mov     rdi, [rbx+48h]
0x1400101f2  mov     r12, [rdi+48h]
0x1400101f6  lea     rcx, [rdi+598h]; SpinLock
0x1400101fd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010204  nop     dword ptr [rax+rax+00h]
0x140010209  lea     rcx, [rdi+5A8h]
0x140010210  mov     [rdi+5A0h], al
0x140010216  cmp     [rcx], rcx
0x140010219  jnz     short loc_140010229
0x14001021b  cmp     byte ptr [rdi+590h], 0
0x140010222  jnz     short loc_140010229
0x140010224  mov     r13b, 1
0x140010227  jmp     short loc_14001022C
0x140010229  xor     r13b, r13b
0x14001022c  mov     rax, [rcx+8]
0x140010230  mov     [r15], rcx
0x140010233  mov     [r15+8], rax
0x140010237  mov     [rax], r15
0x14001023a  movzx   edx, byte ptr [rdi+5A0h]; NewIrql
0x140010241  mov     [rcx+8], r15
0x140010245  lea     rcx, [rdi+598h]; SpinLock
0x14001024c  call    cs:__imp_KeReleaseSpinLock
0x140010253  nop     dword ptr [rax+rax+00h]
0x140010258  lock inc qword ptr [r12+950h]
0x140010261  lock inc qword ptr [r12+948h]
0x14001026a  test    r13b, r13b
0x14001026d  jz      short loc_14001027B
0x14001026f  mov     rcx, [rdi+40h]
0x140010273  mov     rdx, rdi
0x140010276  call    QuicWorkerQueueConnection
0x14001027b  or      byte ptr [rbx+5Bh], 20h
0x14001027f  movzx   r12d, [rsp+1A0h+var_160]
0x140010285  jmp     short loc_14001029F
0x140010287  test    cs:Microsoft_QuicEnableBits, 2
0x14001028e  jz      short loc_14001029F
0x140010290  xor     r9d, r9d
0x140010293  lea     r8, aFlushStreamRec; "Flush Stream Recv operation"
0x14001029a  call    McTemplateU0sx_EtwWriteTransfer
0x14001029f  test    cs:byte_14005C48D, 1
0x1400102a6  jz      short loc_1400102FA
0x1400102a8  movzx   ecx, word ptr [r14+18h]
0x1400102ad  lea     r9, aReceivedHuByte; "Received %hu bytes, offset=%llu Ready=%"...
0x1400102b4  movzx   eax, r12b
0x1400102b8  mov     edx, 80h; SizeInBytes
0x1400102bd  mov     dword ptr [rsp+1A0h+var_170], eax
0x1400102c1  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400102c8  mov     rax, [r14+10h]
0x1400102cc  mov     [rsp+1A0h+var_178], rax
0x1400102d1  mov     dword ptr [rsp+1A0h+var_180], ecx
0x1400102d5  lea     rcx, [rsp+1A0h+var_140]; DstBuf
0x1400102da  call    cs:__imp__snprintf_s
0x1400102e1  nop     dword ptr [rax+rax+00h]
0x1400102e6  lea     r9, [rsp+1A0h+var_140]
0x1400102eb  mov     r8, rbx
0x1400102ee  lea     rdx, QuicStreamLogVerbose
  ... truncated ...
```
