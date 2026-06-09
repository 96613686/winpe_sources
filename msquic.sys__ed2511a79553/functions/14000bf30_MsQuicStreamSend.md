# MsQuicStreamSend

- ea: `0x14000bf30`
- end: `0x14000c43a`
- name: `MsQuicStreamSend`
- size: `1290`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14000bf30`
- `0x14000c5b0`
- `0x14000d0b0`
- `0x1400145c0`
- `0x140022440`
- `0x1400290b4`
- `0x140029104`
- `0x14002974c`
- `0x140029770`
- `0x14002b6f4`
- `0x1400337e4`
- `0x14003ec10`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c18e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c3b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c18e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c3b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c1be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c1e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c252`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c404`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c1be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c1e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c252`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c404`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c15c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c15c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000c16c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000c16c`

## pseudocode

```c
__int64 __fastcall MsQuicStreamSend(__int64 a1, __int64 a2, unsigned int a3, int a4, __int64 a5)
{
  __int64 v7; // rsi
  char v9; // r13
  __int64 v10; // rdi
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rbp
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // r11d
  __int64 v18; // r10
  __int64 v19; // rax
  unsigned __int64 v20; // rbp
  __int64 v22; // rdx
  PSLIST_ENTRY v23; // r14
  bool v24; // r15
  KIRQL v25; // al
  bool v26; // zf
  _QWORD *v27; // rcx
  PSLIST_ENTRY *v28; // rdx
  char v29; // al
  __int64 v30; // rbp
  PSLIST_ENTRY v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *p_Next; // r14
  PSLIST_ENTRY v35; // rax
  __int64 v36; // rsi
  KIRQL v37; // al
  _QWORD *v38; // rcx
  bool v39; // bp
  _QWORD *v40; // rax
  KIRQL v41; // dl
  int v42; // [rsp+88h] [rbp+20h]

  v7 = a1;
  v42 = a4 & 0x40;
  v9 = 1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 22, a1);
  if ( !v7 || *(_DWORD *)v7 != 5 || !a2 && a3 )
    goto LABEL_24;
  if ( (*(_BYTE *)(v7 + 92) & 8) != 0 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1058, "!Stream->Flags.HandleClosed");
  if ( (*(_BYTE *)(v7 + 92) & 0x40) != 0 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1059, "!Stream->Flags.Freed");
  v10 = *(_QWORD *)(v7 + 72);
  if ( (*(_BYTE *)(v10 + 248) & 0x20) != 0 )
  {
    v11 = -1073741536;
    goto LABEL_25;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( a3 < 2 )
  {
    if ( !a3 )
      goto LABEL_21;
    v18 = 0;
    goto LABEL_20;
  }
  a1 = a2;
  v15 = ((a3 - 2) >> 1) + 1;
  v16 = v15;
  v17 = 2 * v15;
  v18 = 2LL * v15;
  do
  {
    v19 = *(unsigned int *)a1;
    a1 += 32;
    v12 += v19;
    v13 += *(unsigned int *)(a1 - 16);
    --v16;
  }
  while ( v16 );
  if ( v17 < a3 )
LABEL_20:
    v14 = *(unsigned int *)(a2 + 16 * v18);
LABEL_21:
  v20 = v13 + v12 + v14;
  if ( v20 > 0xFFFFFFFF )
  {
    if ( (byte_14005C48C & 0x10) != 0 )
      McTemplateU0ps_EtwWriteTransfer(a1, QuicStreamError, v7, "Send request total length exceeds max");
LABEL_24:
    v11 = -1073741811;
    goto LABEL_25;
  }
  v23 = CxPlatPoolAlloc(*(_QWORD *)(v10 + 72) + 576LL);
  if ( !v23 )
  {
    v11 = -1073741801;
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(a1, v22, "Stream Send request", 0);
    goto LABEL_25;
  }
  if ( (byte_14005C48D & 2) != 0 )
    McTemplateU0pxqq_EtwWriteTransfer(a1, (unsigned int)QuicStreamAppSend, v7, v20, a3, a4);
  HIDWORD(v23[1].Next) = a4 & 0x7FFFFFFF;
  *((_QWORD *)&v23[3].Next + 1) = a5;
  v23->Next = 0;
  *((_QWORD *)&v23->Next + 1) = a2;
  LODWORD(v23[1].Next) = a3;
  v23[2].Next = (struct _SLIST_ENTRY *)v20;
  v24 = (*(_BYTE *)(v10 + 235) & 1) == 0 && KeGetCurrentIrql() != 2 && *(HANDLE *)(v10 + 256) == PsGetCurrentThreadId();
  v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 104));
  v26 = (*(_BYTE *)(v7 + 91) & 2) == 0;
  *(_BYTE *)(v7 + 112) = v25;
  if ( v26 )
  {
    if ( (*(_BYTE *)(v10 + 248) & 0x20) == 0 && (*(_BYTE *)(v7 + 90) & 1) == 0 )
    {
      v11 = -1073741436;
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 104), v25);
      CxPlatPoolFree(v23);
      goto LABEL_25;
    }
    v11 = -1073741536;
  }
  else
  {
    v27 = *(_QWORD **)(v7 + 120);
    v28 = (PSLIST_ENTRY *)(v7 + 120);
    if ( v27 )
    {
      v9 = 0;
      do
      {
        v28 = (PSLIST_ENTRY *)v27;
        v27 = (_QWORD *)*v27;
      }
      while ( v27 );
    }
    *v28 = v23;
    v11 = 0;
    if ( !v24 && v9 )
    {
      CxPlatRefIncrement(v7 + 16);
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 104), *(_BYTE *)(v7 + 112));
      v11 = 259;
      goto LABEL_56;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 104), *(_BYTE *)(v7 + 112));
  if ( v11 < 0 )
  {
    CxPlatPoolFree(v23);
    goto LABEL_25;
  }
  v11 = 259;
  if ( v24 )
  {
    v29 = *(_BYTE *)(v10 + 251);
    if ( (v29 & 0x20) != 0 )
    {
      QuicStreamSendFlush(v7);
    }
    else
    {
      *(_BYTE *)(v10 + 251) = v29 | 0x20;
      QuicStreamSendFlush(v7);
      *(_BYTE *)(v10 + 251) &= ~0x20u;
    }
    goto LABEL_25;
  }
  if ( !v9 )
    goto LABEL_25;
LABEL_56:
  v30 = *(_QWORD *)(v10 + 72);
  v31 = CxPlatPoolAlloc(v30 + 2016);
  p_Next = &v31->Next;
  if ( !v31 )
  {
LABEL_59:
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v33, v32, "STRM_SEND operation", 0);
    QuicStreamRelease(v7);
    a1 = 1;
    if ( !_InterlockedCompareExchange16((volatile signed __int16 *)(v10 + 1584), 1, 0) )
    {
      *(_BYTE *)(v10 + 1492) = 0;
      *(_QWORD *)(v10 + 1496) = v10 + 1528;
      *(_DWORD *)(v10 + 1488) = 0;
      *(_DWORD *)(v10 + 1528) = 1;
      *(_DWORD *)(*(_QWORD *)(v10 + 1496) + 24LL) = 32769;
      *(_QWORD *)(*(_QWORD *)(v10 + 1496) + 32LL) = -1073741801;
      *(_BYTE *)(*(_QWORD *)(v10 + 1496) + 28LL) &= ~1u;
      *(_BYTE *)(*(_QWORD *)(v10 + 1496) + 28LL) |= 2u;
      QuicConnQueueHighestPriorityOper(v10);
    }
    goto LABEL_25;
  }
  LODWORD(v31[1].Next) = 0;
  BYTE4(v31[1].Next) = 1;
  v35 = CxPlatPoolAlloc(v30 + 1824);
  p_Next[3] = v35;
  if ( !v35 )
  {
    CxPlatPoolFree(p_Next);
    goto LABEL_59;
  }
  *((_QWORD *)&v35->Next + 1) = 0;
  *(_QWORD *)(p_Next[3] + 16LL) = 0;
  *(_DWORD *)p_Next[3] = 8;
  *(_QWORD *)(p_Next[3] + 24LL) = v7;
  if ( v42 )
  {
    QuicConnQueuePriorityOper(v10, p_Next);
  }
  else
  {
    v36 = *(_QWORD *)(v10 + 72);
    v37 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 1432));
    v38 = (_QWORD *)(v10 + 1448);
    *(_BYTE *)(v10 + 1440) = v37;
    v39 = (_QWORD *)*v38 == v38 && !*(_BYTE *)(v10 + 1424);
    v40 = *(_QWORD **)(v10 + 1456);
    *p_Next = v38;
    p_Next[1] = v40;
    *v40 = p_Next;
    v41 = *(_BYTE *)(v10 + 1440);
    *(_QWORD *)(v10 + 1456) = p_Next;
    KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 1432), v41);
    _InterlockedIncrement64((volatile signed __int64 *)(v36 + 2384));
    _InterlockedIncrement64((volatile signed __int64 *)(v36 + 2376));
    if ( v39 )
      QuicWorkerQueueConnection(*(_QWORD *)(v10 + 64), v10);
  }
LABEL_25:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000bf30  push    rbx
0x14000bf32  sub     rsp, 60h
0x14000bf36  mov     [rsp+68h+var_10], rsi
0x14000bf3b  mov     eax, r9d
0x14000bf3e  mov     [rsp+68h+var_20], r12
0x14000bf43  and     eax, 40h
0x14000bf46  test    cs:Microsoft_QuicEnableBits, 8
0x14000bf4d  mov     ebx, r8d
0x14000bf50  mov     [rsp+68h+var_28], r13
0x14000bf55  mov     r12, rdx
0x14000bf58  mov     [rsp+68h+var_38], r15
0x14000bf5d  mov     rsi, rcx
0x14000bf60  mov     r15d, r9d
0x14000bf63  mov     [rsp+68h+arg_18], eax
0x14000bf6a  mov     r13b, 1
0x14000bf6d  jz      short loc_14000BF7D
0x14000bf6f  mov     r9, rcx
0x14000bf72  mov     r8d, 16h
0x14000bf78  call    McTemplateU0qp_EtwWriteTransfer
0x14000bf7d  mov     [rsp+68h+arg_8], rbp
0x14000bf82  mov     [rsp+68h+var_18], rdi
0x14000bf87  mov     [rsp+68h+var_30], r14
0x14000bf8c  test    rsi, rsi
0x14000bf8f  jz      loc_14000C087
0x14000bf95  cmp     dword ptr [rsi], 5
0x14000bf98  jnz     loc_14000C087
0x14000bf9e  test    r12, r12
0x14000bfa1  jnz     short loc_14000BFAB
0x14000bfa3  test    ebx, ebx
0x14000bfa5  jnz     loc_14000C087
0x14000bfab  test    byte ptr [rsi+5Ch], 8
0x14000bfaf  jz      short loc_14000BFC9
0x14000bfb1  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x14000bfb8  mov     edx, 422h
0x14000bfbd  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000bfc4  call    CxPlatLogAssert
0x14000bfc9  test    byte ptr [rsi+5Ch], 40h
0x14000bfcd  jz      short loc_14000BFE7
0x14000bfcf  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x14000bfd6  mov     edx, 423h
0x14000bfdb  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000bfe2  call    CxPlatLogAssert
0x14000bfe7  mov     rdi, [rsi+48h]
0x14000bfeb  test    byte ptr [rdi+0F8h], 20h
0x14000bff2  jz      short loc_14000BFFE
0x14000bff4  mov     ebx, 0C0000120h
0x14000bff9  jmp     loc_14000C08C
0x14000bffe  xor     r8d, r8d
0x14000c001  xor     r9d, r9d
0x14000c004  xor     ebp, ebp
0x14000c006  cmp     ebx, 2
0x14000c009  jb      short loc_14000C03C
0x14000c00b  lea     eax, [rbx-2]
0x14000c00e  mov     rcx, r12
0x14000c011  shr     eax, 1
0x14000c013  inc     eax
0x14000c015  mov     edx, eax
0x14000c017  lea     r11d, [rax+rax]
0x14000c01b  lea     r10, [rax+rax]
0x14000c01f  nop
0x14000c020  mov     eax, [rcx]
0x14000c022  lea     rcx, [rcx+20h]
0x14000c026  add     r8, rax
0x14000c029  mov     eax, [rcx-10h]
0x14000c02c  add     r9, rax
0x14000c02f  sub     rdx, 1
0x14000c033  jnz     short loc_14000C020
0x14000c035  cmp     r11d, ebx
0x14000c038  jb      short loc_14000C050
0x14000c03a  jmp     short loc_14000C057
0x14000c03c  test    ebx, ebx
0x14000c03e  jz      short loc_14000C057
0x14000c040  xor     r10d, r10d
0x14000c043  nop     dword ptr [rax+00h]
0x14000c047  nop     word ptr [rax+rax+00000000h]
0x14000c050  add     r10, r10
0x14000c053  mov     ebp, [r12+r10*8]
0x14000c057  lea     rax, [r9+r8]
0x14000c05b  add     rbp, rax
0x14000c05e  mov     eax, 0FFFFFFFFh
0x14000c063  cmp     rbp, rax
0x14000c066  jbe     short loc_14000C0D0
0x14000c068  test    cs:byte_14005C48C, 10h
0x14000c06f  jz      short loc_14000C087
0x14000c071  lea     r9, aSendRequestTot; "Send request total length exceeds max"
0x14000c078  mov     r8, rsi
0x14000c07b  lea     rdx, QuicStreamError
0x14000c082  call    McTemplateU0ps_EtwWriteTransfer
0x14000c087  mov     ebx, 0C000000Dh
0x14000c08c  test    cs:Microsoft_QuicEnableBits, 8
0x14000c093  mov     r15, [rsp+68h+var_38]
0x14000c098  mov     r14, [rsp+68h+var_30]
0x14000c09d  mov     r13, [rsp+68h+var_28]
0x14000c0a2  mov     r12, [rsp+68h+var_20]
0x14000c0a7  mov     rdi, [rsp+68h+var_18]
0x14000c0ac  mov     rsi, [rsp+68h+var_10]
0x14000c0b1  mov     rbp, [rsp+68h+arg_8]
0x14000c0b6  jz      short loc_14000C0C7
0x14000c0b8  mov     r8d, ebx
0x14000c0bb  lea     rdx, QuicApiExitStatus
0x14000c0c2  call    McTemplateU0q_EtwWriteTransfer
0x14000c0c7  mov     eax, ebx
0x14000c0c9  add     rsp, 60h
0x14000c0cd  pop     rbx
0x14000c0ce  retn
0x14000c0d0  mov     rcx, [rdi+48h]
0x14000c0d4  add     rcx, 240h
0x14000c0db  call    CxPlatPoolAlloc
0x14000c0e0  mov     r14, rax
0x14000c0e3  test    rax, rax
0x14000c0e6  jnz     short loc_14000C107
0x14000c0e8  test    cs:Microsoft_QuicEnableBits, 2
0x14000c0ef  mov     ebx, 0C0000017h
0x14000c0f4  jz      short loc_14000C08C
0x14000c0f6  xor     r9d, r9d
0x14000c0f9  lea     r8, aStreamSendRequ; "Stream Send request"
0x14000c100  call    McTemplateU0sx_EtwWriteTransfer
0x14000c105  jmp     short loc_14000C08C
0x14000c107  test    cs:byte_14005C48D, 2
0x14000c10e  jz      short loc_14000C12B
0x14000c110  mov     [rsp+68h+var_40], r15d
0x14000c115  lea     rdx, QuicStreamAppSend
0x14000c11c  mov     r9, rbp
0x14000c11f  mov     [rsp+68h+var_48], ebx
0x14000c123  mov     r8, rsi
0x14000c126  call    McTemplateU0pxqq_EtwWriteTransfer
0x14000c12b  mov     rax, [rsp+68h+arg_20]
0x14000c133  btr     r15d, 1Fh
0x14000c138  mov     [r14+14h], r15d
0x14000c13c  mov     [r14+38h], rax
0x14000c140  mov     qword ptr [r14], 0
0x14000c147  mov     [r14+8], r12
0x14000c14b  mov     [r14+10h], ebx
0x14000c14f  mov     [r14+20h], rbp
0x14000c153  test    [rdi+0EBh], r13b
0x14000c15a  jnz     short loc_14000C187
0x14000c15c  call    cs:__imp_KeGetCurrentIrql
0x14000c163  nop     dword ptr [rax+rax+00h]
0x14000c168  cmp     al, 2
0x14000c16a  jz      short loc_14000C187
0x14000c16c  call    cs:__imp_PsGetCurrentThreadId
0x14000c173  nop     dword ptr [rax+rax+00h]
0x14000c178  cmp     [rdi+100h], rax
0x14000c17f  jnz     short loc_14000C187
0x14000c181  movzx   r15d, r13b
0x14000c185  jmp     short loc_14000C18A
0x14000c187  xor     r15b, r15b
0x14000c18a  lea     rcx, [rsi+68h]; SpinLock
0x14000c18e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c195  nop     dword ptr [rax+rax+00h]
0x14000c19a  test    byte ptr [rsi+5Bh], 2
0x14000c19e  mov     [rsi+70h], al
0x14000c1a1  jnz     short loc_14000C204
0x14000c1a3  test    byte ptr [rdi+0F8h], 20h
0x14000c1aa  jnz     short loc_14000C1D7
0x14000c1ac  test    [rsi+5Ah], r13b
0x14000c1b0  jnz     short loc_14000C1D7
0x14000c1b2  movzx   edx, al; NewIrql
0x14000c1b5  lea     rcx, [rsi+68h]; SpinLock
0x14000c1b9  mov     ebx, 0C0000184h
0x14000c1be  call    cs:__imp_KeReleaseSpinLock
0x14000c1c5  nop     dword ptr [rax+rax+00h]
0x14000c1ca  mov     rcx, r14
0x14000c1cd  call    CxPlatPoolFree
0x14000c1d2  jmp     loc_14000C08C
0x14000c1d7  mov     ebx, 0C0000120h
0x14000c1dc  xor     r12d, r12d
0x14000c1df  movzx   edx, byte ptr [rsi+70h]; NewIrql
0x14000c1e3  lea     rcx, [rsi+68h]; SpinLock
0x14000c1e7  call    cs:__imp_KeReleaseSpinLock
0x14000c1ee  nop     dword ptr [rax+rax+00h]
0x14000c1f3  test    ebx, ebx
0x14000c1f5  jns     short loc_14000C265
0x14000c1f7  mov     rcx, r14
0x14000c1fa  call    CxPlatPoolFree
0x14000c1ff  jmp     loc_14000C08C
0x14000c204  mov     rcx, [rsi+78h]
0x14000c208  lea     rdx, [rsi+78h]
0x14000c20c  test    rcx, rcx
0x14000c20f  jz      short loc_14000C22E
0x14000c211  xor     r13b, r13b
0x14000c214  nop     dword ptr [rax+00h]
0x14000c218  nop     dword ptr [rax+rax+00000000h]
0x14000c220  mov     rax, [rcx]
0x14000c223  mov     rdx, rcx
0x14000c226  mov     rcx, rax
0x14000c229  test    rax, rax
0x14000c22c  jnz     short loc_14000C220
0x14000c22e  xor     r12d, r12d
0x14000c231  mov     [rdx], r14
0x14000c234  mov     ebx, r12d
0x14000c237  test    r15b, r15b
0x14000c23a  jnz     short loc_14000C1DF
0x14000c23c  test    r13b, r13b
0x14000c23f  jz      short loc_14000C1DF
0x14000c241  lea     rcx, [rsi+10h]
0x14000c245  call    CxPlatRefIncrement
0x14000c24a  movzx   edx, byte ptr [rsi+70h]; NewIrql
0x14000c24e  lea     rcx, [rsi+68h]; SpinLock
0x14000c252  call    cs:__imp_KeReleaseSpinLock
0x14000c259  nop     dword ptr [rax+rax+00h]
0x14000c25e  mov     ebx, 103h
0x14000c263  jmp     short loc_14000C2A9
0x14000c265  mov     ebx, 103h
0x14000c26a  test    r15b, r15b
0x14000c26d  jz      short loc_14000C2A0
0x14000c26f  movzx   eax, byte ptr [rdi+0FBh]
0x14000c276  mov     rcx, rsi
0x14000c279  test    al, 20h
0x14000c27b  jnz     short loc_14000C296
0x14000c27d  or      al, 20h
0x14000c27f  mov     [rdi+0FBh], al
0x14000c285  call    QuicStreamSendFlush
0x14000c28a  and     byte ptr [rdi+0FBh], 0DFh
0x14000c291  jmp     loc_14000C08C
0x14000c296  call    QuicStreamSendFlush
0x14000c29b  jmp     loc_14000C08C
0x14000c2a0  test    r13b, r13b
0x14000c2a3  jz      loc_14000C08C
0x14000c2a9  mov     rbp, [rdi+48h]
0x14000c2ad  lea     rcx, [rbp+7E0h]
0x14000c2b4  call    CxPlatPoolAlloc
0x14000c2b9  mov     r14, rax
0x14000c2bc  test    rax, rax
0x14000c2bf  jz      short loc_14000C2EA
0x14000c2c1  lea     rcx, [rbp+720h]
0x14000c2c8  mov     [rax+10h], r12d
0x14000c2cc  mov     byte ptr [rax+14h], 1
0x14000c2d0  call    CxPlatPoolAlloc
0x14000c2d5  mov     [r14+18h], rax
0x14000c2d9  test    rax, rax
0x14000c2dc  jnz     loc_14000C372
0x14000c2e2  mov     rcx, r14
0x14000c2e5  call    CxPlatPoolFree
0x14000c2ea  test    cs:Microsoft_QuicEnableBits, 2
0x14000c2f1  jz      short loc_14000C302
0x14000c2f3  xor     r9d, r9d
0x14000c2f6  lea     r8, aStrmSendOperat; "STRM_SEND operation"
0x14000c2fd  call    McTemplateU0sx_EtwWriteTransfer
0x14000c302  mov     rcx, rsi
0x14000c305  call    QuicStreamRelease
0x14000c30a  xor     eax, eax
0x14000c30c  mov     ecx, 1
0x14000c311  lock cmpxchg [rdi+630h], cx
0x14000c31a  test    ax, ax
0x14000c31d  jnz     loc_14000C08C
0x14000c323  lea     rdx, [rdi+5C0h]
0x14000c32a  mov     [rdx+14h], al
0x14000c32d  lea     rax, [rdi+5F8h]
0x14000c334  mov     [rdx+18h], rax
0x14000c338  mov     [rdx+10h], r12d
0x14000c33c  mov     [rax], ecx
0x14000c33e  mov     rcx, rdi
0x14000c341  mov     rax, [rdx+18h]
0x14000c345  mov     dword ptr [rax+18h], 8001h
0x14000c34c  mov     rax, [rdx+18h]
0x14000c350  mov     qword ptr [rax+20h], 0FFFFFFFFC0000017h
0x14000c358  mov     rax, [rdx+18h]
0x14000c35c  and     byte ptr [rax+1Ch], 0FEh
0x14000c360  mov     rax, [rdx+18h]
0x14000c364  or      byte ptr [rax+1Ch], 2
0x14000c368  call    QuicConnQueueHighestPriorityOper
0x14000c36d  jmp     loc_14000C08C
0x14000c372  cmp     [rsp+68h+arg_18], 0
0x14000c37a  mov     [rax+8], r12
0x14000c37e  mov     rax, [r14+18h]
0x14000c382  mov     [rax+10h], r12
0x14000c386  mov     rax, [r14+18h]
0x14000c38a  mov     dword ptr [rax], 8
0x14000c390  mov     rax, [r14+18h]
0x14000c394  mov     [rax+18h], rsi
0x14000c398  jz      short loc_14000C3AA
0x14000c39a  mov     rdx, r14
0x14000c39d  mov     rcx, rdi
0x14000c3a0  call    QuicConnQueuePriorityOper
0x14000c3a5  jmp     loc_14000C08C
0x14000c3aa  mov     rsi, [rdi+48h]
0x14000c3ae  lea     rcx, [rdi+598h]; SpinLock
0x14000c3b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c3bc  nop     dword ptr [rax+rax+00h]
0x14000c3c1  lea     rcx, [rdi+5A8h]
0x14000c3c8  mov     [rdi+5A0h], al
0x14000c3ce  cmp     [rcx], rcx
0x14000c3d1  jnz     short loc_14000C3E1
0x14000c3d3  cmp     byte ptr [rdi+590h], 0
0x14000c3da  jnz     short loc_14000C3E1
0x14000c3dc  mov     bpl, 1
0x14000c3df  jmp     short loc_14000C3E4
0x14000c3e1  xor     bpl, bpl
0x14000c3e4  mov     rax, [rcx+8]
0x14000c3e8  mov     [r14], rcx
0x14000c3eb  mov     [r14+8], rax
0x14000c3ef  mov     [rax], r14
0x14000c3f2  movzx   edx, byte ptr [rdi+5A0h]; NewIrql
0x14000c3f9  mov     [rcx+8], r14
0x14000c3fd  lea     rcx, [rdi+598h]; SpinLock
0x14000c404  call    cs:__imp_KeReleaseSpinLock
0x14000c40b  nop     dword ptr [rax+rax+00h]
0x14000c410  lock inc qword ptr [rsi+950h]
0x14000c418  lock inc qword ptr [rsi+948h]
  ... truncated ...
```
