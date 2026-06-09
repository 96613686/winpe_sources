# UlpSendSimpleStatusWorker

- ea: `0x140039ff0`
- end: `0x14003a868`
- name: `UlpSendSimpleStatusWorker`
- size: `2168`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x14007d580`

## callees

- `0x14000a350`
- `0x14000a520`
- `0x14000e420`
- `0x14002186c`
- `0x140021f80`
- `0x140022610`
- `0x1400397d0`
- `0x140039c80`
- `0x140039ff0`
- `0x14003bf20`
- `0x1400ca8c4`
- `0x14012a390`
- `0x14015585c`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d32ac`
- `0x1401d35ac`
- `0x1401d9cac`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003a4fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a784`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a4fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a784`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003a525`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003a525`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003a565`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003a565`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a136`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a4b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a136`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a4b3`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003a40b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003a40b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a0cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a483`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a0cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a483`

## pseudocode

```c
void __fastcall UlpSendSimpleStatusWorker(ULONG_PTR a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  int v5; // eax
  unsigned __int8 v6; // si
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // r14
  __int64 v10; // r12
  __int64 v11; // rdi
  KIRQL v12; // al
  __int64 v13; // r9
  KIRQL v14; // r13
  __int64 v15; // rdi
  __int64 v16; // rax
  int v17; // r12d
  __int64 v18; // r13
  int v19; // r9d
  __int16 v20; // r15
  _QWORD *v21; // rdi
  __int64 v22; // r8
  __int64 v23; // rsi
  __int64 v24; // rdx
  int v25; // edi
  int v26; // eax
  unsigned int v27; // r12d
  __int64 v28; // rsi
  unsigned int v29; // eax
  int v30; // edi
  char v31; // si
  __int64 v32; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v34; // r9
  __int64 v35; // rdi
  __int64 v36; // rcx
  KSPIN_LOCK *v37; // rsi
  KIRQL v38; // al
  __int64 v39; // rdx
  __int64 v40; // r8
  char v41; // si
  __int64 v42; // rax
  __int64 v43; // rbp
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rax
  int v51; // [rsp+80h] [rbp-78h]
  __int64 v52; // [rsp+88h] [rbp-70h]
  __int64 v53; // [rsp+90h] [rbp-68h] BYREF
  __int64 v54[4]; // [rsp+98h] [rbp-60h] BYREF
  char v55; // [rsp+100h] [rbp+8h] BYREF
  unsigned __int8 v56; // [rsp+108h] [rbp+10h] BYREF
  char v57; // [rsp+110h] [rbp+18h]
  int v58; // [rsp+118h] [rbp+20h]

  v3 = 0;
  v55 = 0;
  v57 = 0;
  v56 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 266, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1);
  v5 = *(_DWORD *)(a1 + 48);
  v6 = *(_BYTE *)(a1 + 52);
  v56 = v6;
  v51 = v5;
  if ( v5 == 2 )
  {
    v7 = *(_QWORD *)(a1 + 80);
    v55 = 1;
    v3 = *(_QWORD *)(v7 + 24);
    v8 = _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
    if ( UxDebugCheckRefcount && v8 <= -1 )
      UlBugCheckEx(3u, v3 + 40, 0x21u, v8);
    v6 = v56;
    v57 = 1;
  }
  v9 = *(_QWORD *)(a1 + 80);
  v10 = *(unsigned int *)(a1 + 56);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( v9 )
      v49 = *(_QWORD *)(v9 + 64);
    else
      v49 = 0;
    WPP_SF_qiIlqq(v49, &v55, a3, v9, v49, v10, v6, 0, &v55);
  }
  if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
    UlBugCheckEx(4u, 0, (ULONG_PTR)"minio\\http\\sys\\sendresponse.c", 0x15DEu);
  v11 = *(_QWORD *)(v9 + 24);
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 640));
  ++*(_DWORD *)(v9 + 1624);
  v14 = v12;
  ++*(_DWORD *)(v11 + 336);
  if ( v55 && *(_DWORD *)(v11 + 336) >= 3u )
  {
    *(_BYTE *)(v11 + 521) = 1;
    *(_BYTE *)(v11 + 522) = v6;
    *(_BYTE *)(v11 + 523) = 1;
    v55 = 0;
  }
  LOBYTE(v13) = 1;
  UlSetBundleTimerEx(v11 + 648, 2, v10, v13);
  KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 640), v14);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 82, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
  v15 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v15 + 3214) )
  {
    v27 = *(_DWORD *)(a1 + 196);
    v18 = a1 + 488;
    v28 = *(_QWORD *)(a1 + 200);
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    {
      if ( v15 )
        v50 = *(_QWORD *)(v15 + 64);
      else
        v50 = 0;
      WPP_SF_qiqLqq(1033, 22, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v15, v50, a1 + 328, 1, v28, a1 + 488);
    }
    v29 = UlpSanitizeResponseHeaders(v15, a1 + 328, v28, v27, a1 + 488);
    v30 = v29;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 23, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v29);
    if ( v30 < 0 )
    {
      v31 = byte_1401A3780;
      if ( SBYTE2(xmmword_1401A2CA0) < 0 )
        WPP_SF_d(1047, 10, WPP_b6616b8acc683c557a6f97eb9025b7cb_Traceguids, (unsigned __int8)byte_1401A3780);
      if ( v31 )
        UxPktMonTraceDropHttpSend(*(_QWORD *)(a1 + 80), 0, (unsigned int)v30);
      goto LABEL_50;
    }
    v19 = 0;
    v17 = 0;
  }
  else
  {
    v16 = *(_QWORD *)(a1 + 72);
    v17 = a1 + 88;
    *(_DWORD *)(a1 + 88) = 3;
    v18 = 0;
    *(_QWORD *)(a1 + 96) = v16;
    v19 = 1;
  }
  v58 = v19;
  if ( v56 )
    v20 = 3;
  else
    v20 = 4;
  v21 = *(_QWORD **)(a1 + 80);
  *(_OWORD *)v54 = 0;
  v22 = v21[3];
  v52 = v22;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v21 )
      v44 = v21[8];
    else
      LODWORD(v44) = 0;
    if ( v22 )
      v45 = *(_QWORD *)(v22 + 48);
    else
      LODWORD(v45) = 0;
    WPP_SF_qiqlLlqqiqqqq(
      v45,
      v44,
      v22,
      v22,
      v45,
      v17,
      v19,
      0,
      v20,
      0,
      (char)v21,
      v44,
      (char)UlpRestartSendSimpleStatus,
      a1,
      0,
      0);
    v22 = v52;
  }
  if ( (v20 & 1) != 0 )
  {
    v37 = (KSPIN_LOCK *)(v22 + 640);
    v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v22 + 640));
    if ( *(_BYTE *)(v52 + 790) )
      v20 &= ~2u;
    else
      *(_WORD *)(v52 + 788) = 256;
    KeReleaseSpinLock(v37, v38);
  }
  v23 = 0;
  v53 = 0;
  if ( UlHkeQosClassficationEnabled && (UlpHkeAcquireQoS(v21, &v53), (v23 = v53) != 0) )
  {
    v20 |= 0x8000u;
    v24 = v53;
  }
  else
  {
    v24 = v21[310];
    if ( v24 )
      v20 |= 0x4000u;
  }
  if ( v21[8] )
    v54[0] = (__int64)(v21 + 9);
  v25 = UxTpTransmitPacket(
          (int)v52 + 976,
          v17,
          v58,
          0,
          v20,
          0,
          (__int64)UlpRestartSendSimpleStatus,
          a1,
          (__int64)v21,
          v24,
          0,
          0,
          (__int64)v54,
          v18,
          0);
  if ( v23 )
    UlHkeDereferenceCalloutContext(v23, 10);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 107, WPP_682cf469470432b235cb9a4961616e40_Traceguids, (unsigned int)v25);
  if ( v51 == 2 )
  {
    if ( v55 || (UlSetPostSendState(v3, &v55, &v56), v55) )
      UlResumeParsing(v3, v56);
  }
  if ( v25 < 0 )
LABEL_50:
    UlpRestartSendSimpleStatus(a1);
  if ( v57 )
  {
    v26 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 40));
    if ( UxDebugCheckRefcount && v26 <= -1 )
      UlBugCheckEx(3u, v3 + 40, 0x21u, v26);
    if ( !v26 )
    {
      v32 = v3 + 64;
      CurrentProcess = IoGetCurrentProcess();
      v35 = *(_QWORD *)(v3 + 1088);
      v36 = *(_QWORD *)(v3 + 64);
      if ( UxSystemProcess == CurrentProcess )
      {
        if ( v36 || *(_QWORD *)(v3 + 80) || *(_QWORD *)(v3 + 96) )
          UlBugCheckEx(1u, v3 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
        if ( !KeGetCurrentIrql() )
        {
          v41 = 0;
          *(_OWORD *)v54 = 0;
          if ( v35 == -1 )
          {
            v43 = v54[1];
          }
          else
          {
            v42 = PsAttachSiloToCurrentThread(v35);
            v43 = v42;
            v41 = 1;
            if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            {
              WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v42, v35);
              UlFreeHttpConnection(v32, v46, v47, v48);
LABEL_67:
              if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v43);
              PsDetachSiloFromCurrentThread(v43);
              goto LABEL_36;
            }
          }
          UlFreeHttpConnection(v32, v39, v40, v34);
          if ( !v41 )
            goto LABEL_36;
          goto LABEL_67;
        }
      }
      else if ( v36 || *(_QWORD *)(v3 + 80) || *(_QWORD *)(v3 + 96) )
      {
        UlBugCheckEx(1u, v3 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      }
      LOBYTE(v34) = 1;
      UlThreadPoolEnqueueWorkItem(0, v3 + 64, UlFreeHttpConnection, v34, v35, -1);
    }
  }
LABEL_36:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 267, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
}

```

## disassembly

```asm
0x140039ff0  mov     rax, rsp
0x140039ff3  push    rbx
0x140039ff4  push    rbp
0x140039ff5  push    rsi
0x140039ff6  sub     rsp, 0E0h
0x140039ffd  xor     ebp, ebp
0x140039fff  mov     byte ptr [rax+8], 0
0x14003a003  mov     [rsp+0F8h+arg_10], bpl
0x14003a00b  mov     rbx, rcx
0x14003a00e  mov     byte ptr [rax+10h], 0
0x14003a012  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a019  jnz     loc_14003A766
0x14003a01f  mov     eax, [rbx+30h]
0x14003a022  movzx   esi, byte ptr [rbx+34h]
0x14003a026  mov     [rsp+0F8h+arg_8], sil
0x14003a02e  mov     [rsp+0F8h+var_38], r14
0x14003a036  mov     [rsp+0F8h+var_78], eax
0x14003a03d  cmp     eax, 2
0x14003a040  jnz     short loc_14003A07E
0x14003a042  mov     rax, [rbx+50h]
0x14003a046  mov     [rsp+0F8h+arg_0], 1
0x14003a04e  mov     rbp, [rax+18h]
0x14003a052  mov     eax, 1
0x14003a057  lea     rdx, [rbp+28h]; BugCheckParameter2
0x14003a05b  lock xadd [rdx], eax
0x14003a05f  inc     eax
0x14003a061  cmp     cs:UxDebugCheckRefcount, 0
0x14003a068  jnz     loc_14003A35B
0x14003a06e  movzx   esi, [rsp+0F8h+arg_8]
0x14003a076  mov     [rsp+0F8h+arg_10], 1
0x14003a07e  mov     r14, [rbx+50h]
0x14003a082  mov     [rsp+0F8h+var_28], r12
0x14003a08a  mov     r12d, [rbx+38h]
0x14003a08e  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a095  jnz     loc_14003A6DD
0x14003a09b  cmp     cs:UxEnableIrqlEnforcement, 0
0x14003a0a2  mov     [rsp+0F8h+var_40], r15
0x14003a0aa  jnz     loc_14003A784
0x14003a0b0  mov     [rsp+0F8h+var_20], rdi
0x14003a0b8  mov     rdi, [r14+18h]
0x14003a0bc  mov     [rsp+0F8h+var_30], r13
0x14003a0c4  lea     rcx, [rdi+280h]; SpinLock
0x14003a0cb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a0d2  nop     dword ptr [rax+rax+00h]
0x14003a0d7  inc     dword ptr [r14+658h]
0x14003a0de  movzx   r13d, al
0x14003a0e2  cmp     cs:UxKirHttpBugFix25Q1, 0
0x14003a0e9  jz      loc_14003A4F3
0x14003a0ef  mov     eax, [rdi+150h]
0x14003a0f5  inc     eax
0x14003a0f7  mov     [rdi+150h], eax
0x14003a0fd  cmp     [rsp+0F8h+arg_0], 0
0x14003a105  jz      short loc_14003A114
0x14003a107  cmp     dword ptr [rdi+150h], 3
0x14003a10e  jnb     loc_14003A7B2
0x14003a114  lea     rcx, [rdi+288h]
0x14003a11b  mov     r9b, 1
0x14003a11e  mov     r8, r12
0x14003a121  mov     edx, 2
0x14003a126  call    UlSetBundleTimerEx
0x14003a12b  movzx   edx, r13b; NewIrql
0x14003a12f  lea     rcx, [rdi+280h]; SpinLock
0x14003a136  call    cs:__imp_KeReleaseSpinLock
0x14003a13d  nop     dword ptr [rax+rax+00h]
0x14003a142  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a149  jnz     loc_14003A7D4
0x14003a14f  mov     rdi, [rbx+50h]
0x14003a153  mov     r14d, 3
0x14003a159  cmp     byte ptr [rdi+0C8Eh], 0
0x14003a160  jnz     loc_14003A378
0x14003a166  mov     rax, [rbx+48h]
0x14003a16a  lea     r12, [rbx+58h]
0x14003a16e  mov     [r12], r14d
0x14003a172  xor     r13d, r13d
0x14003a175  mov     [rbx+60h], rax
0x14003a179  mov     r9d, 1
0x14003a17f  cmp     [rsp+0F8h+arg_8], 0
0x14003a187  mov     [rsp+0F8h+arg_18], r9d
0x14003a18f  jnz     loc_14003A4C4
0x14003a195  mov     r15d, 4
0x14003a19b  mov     rdi, [rbx+50h]
0x14003a19f  xorps   xmm0, xmm0
0x14003a1a2  movups  xmmword ptr [rsp+0F8h+var_60], xmm0
0x14003a1aa  mov     r8, [rdi+18h]
0x14003a1ae  mov     [rsp+0F8h+var_70], r8
0x14003a1b6  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a1bd  lea     r10, UlpRestartSendSimpleStatus
0x14003a1c4  jnz     loc_14003A5D2
0x14003a1ca  test    r15b, 1
0x14003a1ce  jnz     loc_14003A479
0x14003a1d4  xor     esi, esi
0x14003a1d6  cmp     cs:UlHkeQosClassficationEnabled, esi
0x14003a1dc  mov     [rsp+0F8h+var_68], rsi
0x14003a1e4  jz      short loc_14003A207
0x14003a1e6  lea     rdx, [rsp+0F8h+var_68]
0x14003a1ee  mov     rcx, rdi
0x14003a1f1  call    UlpHkeAcquireQoS
0x14003a1f6  mov     rsi, [rsp+0F8h+var_68]
0x14003a1fe  test    rsi, rsi
0x14003a201  jnz     loc_14003A34D
0x14003a207  mov     rdx, [rdi+9B0h]
0x14003a20e  test    rdx, rdx
0x14003a211  jnz     loc_14003A6A7
0x14003a217  cmp     qword ptr [rdi+40h], 0
0x14003a21c  jz      short loc_14003A22A
0x14003a21e  lea     rax, [rdi+48h]
0x14003a222  mov     [rsp+0F8h+var_60], rax
0x14003a22a  mov     rcx, [rsp+0F8h+var_70]
0x14003a232  lea     rax, [rsp+0F8h+var_60]
0x14003a23a  xor     r8d, r8d
0x14003a23d  add     rcx, 3D0h; int
0x14003a244  mov     [rsp+0F8h+var_88], r8; __int64
0x14003a249  xor     r9d, r9d; int
0x14003a24c  mov     [rsp+0F8h+var_90], r13; __int64
0x14003a251  mov     [rsp+0F8h+var_98], rax; __int64
0x14003a256  lea     rax, UlpRestartSendSimpleStatus
0x14003a25d  mov     [rsp+0F8h+var_A0], r8; __int64
0x14003a262  mov     [rsp+0F8h+var_A8], r8; __int64
0x14003a267  mov     [rsp+0F8h+var_B0], rdx; __int64
0x14003a26c  mov     rdx, r12; int
0x14003a26f  mov     [rsp+0F8h+var_B8], rdi; __int64
0x14003a274  mov     [rsp+0F8h+var_C0], rbx; __int64
0x14003a279  mov     [rsp+0F8h+var_C8], rax; __int64
0x14003a27e  mov     [rsp+0F8h+Irp], r8; Irp
0x14003a283  mov     r8d, [rsp+0F8h+arg_18]; int
0x14003a28b  mov     [rsp+0F8h+var_D8], r15w; __int16
0x14003a291  call    UxTpTransmitPacket
0x14003a296  mov     edi, eax
0x14003a298  test    rsi, rsi
0x14003a29b  jnz     loc_14003A7EF
0x14003a2a1  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a2a8  jnz     loc_14003A801
0x14003a2ae  cmp     [rsp+0F8h+var_78], 2
0x14003a2b6  jnz     short loc_14003A2D6
0x14003a2b8  cmp     [rsp+0F8h+arg_0], 0
0x14003a2c0  jz      loc_14003A81F
0x14003a2c6  movzx   edx, [rsp+0F8h+arg_8]
0x14003a2ce  mov     rcx, rbp
0x14003a2d1  call    UlResumeParsing
0x14003a2d6  test    edi, edi
0x14003a2d8  js      loc_14003A3F5
0x14003a2de  cmp     [rsp+0F8h+arg_10], 0
0x14003a2e6  mov     r13, [rsp+0F8h+var_30]
0x14003a2ee  jz      short loc_14003A314
0x14003a2f0  lea     rdx, [rbp+28h]; BugCheckParameter2
0x14003a2f4  mov     eax, 0FFFFFFFFh
0x14003a2f9  lock xadd [rdx], eax
0x14003a2fd  dec     eax
0x14003a2ff  cmp     cs:UxDebugCheckRefcount, 0
0x14003a306  jnz     loc_14003A45E
0x14003a30c  test    eax, eax
0x14003a30e  jz      loc_14003A407
0x14003a314  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a31b  jnz     loc_14003A4D8
0x14003a321  mov     rdi, [rsp+0F8h+var_20]
0x14003a329  mov     r15, [rsp+0F8h+var_40]
0x14003a331  mov     r12, [rsp+0F8h+var_28]
0x14003a339  mov     r14, [rsp+0F8h+var_38]
0x14003a341  add     rsp, 0E0h
0x14003a348  pop     rsi
0x14003a349  pop     rbp
0x14003a34a  pop     rbx
0x14003a34b  retn
0x14003a34d  or      r15w, 8000h
0x14003a353  mov     rdx, rsi
0x14003a356  jmp     loc_14003A217
0x14003a35b  cmp     eax, 0FFFFFFFFh
0x14003a35e  jg      loc_14003A06E
0x14003a364  movsxd  r9, eax; BugCheckParameter4
0x14003a367  mov     ecx, 3; BugCheckParameter1
0x14003a36c  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14003a372  call    UlBugCheckEx
0x14003a378  mov     r12d, [rbx+0C4h]
0x14003a37f  lea     r13, [rbx+1E8h]
0x14003a386  mov     rsi, [rbx+0C8h]
0x14003a38d  lea     r15, [rbx+148h]
0x14003a394  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a39b  jnz     loc_14003A71F
0x14003a3a1  mov     r9d, r12d
0x14003a3a4  mov     qword ptr [rsp+0F8h+var_D8], r13
0x14003a3a9  mov     r8, rsi
0x14003a3ac  mov     rdx, r15
0x14003a3af  mov     rcx, rdi
0x14003a3b2  call    UlpSanitizeResponseHeaders
0x14003a3b7  mov     edi, eax
0x14003a3b9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a3c0  jnz     loc_14003A64F
0x14003a3c6  test    edi, edi
0x14003a3c8  jns     loc_14003A4CD
0x14003a3ce  movzx   esi, cs:byte_1401A3780
0x14003a3d5  cmp     byte ptr cs:xmmword_1401A2CA0+2, 0
0x14003a3dc  jl      loc_14003A66D
0x14003a3e2  test    sil, sil
0x14003a3e5  jz      short loc_14003A3F5
0x14003a3e7  mov     rcx, [rbx+50h]
0x14003a3eb  mov     r8d, edi
0x14003a3ee  xor     edx, edx
0x14003a3f0  call    UxPktMonTraceDropHttpSend
0x14003a3f5  xor     r8d, r8d
0x14003a3f8  mov     edx, edi
0x14003a3fa  mov     rcx, rbx; BugCheckParameter2
0x14003a3fd  call    UlpRestartSendSimpleStatus
0x14003a402  jmp     loc_14003A2DE
0x14003a407  lea     rbx, [rbp+40h]
0x14003a40b  call    cs:__imp_IoGetCurrentProcess
0x14003a412  nop     dword ptr [rax+rax+00h]
0x14003a417  cmp     cs:UxSystemProcess, rax
0x14003a41e  mov     rdi, [rbp+440h]
0x14003a425  mov     rcx, [rbx]
0x14003a428  jnz     loc_14003A5A6
0x14003a42e  test    rcx, rcx
0x14003a431  jnz     short loc_14003A443
0x14003a433  cmp     [rbx+10h], rcx
0x14003a437  jnz     short loc_14003A443
0x14003a439  cmp     [rbx+20h], rcx
0x14003a43d  jz      loc_14003A4FE
0x14003a443  mov     r9d, 0E1h; BugCheckParameter4
0x14003a449  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003a450  mov     rdx, rbx; BugCheckParameter2
0x14003a453  mov     ecx, 1; BugCheckParameter1
0x14003a458  call    UlBugCheckEx
0x14003a45e  cmp     eax, 0FFFFFFFFh
0x14003a461  jg      loc_14003A30C
0x14003a467  movsxd  r9, eax; BugCheckParameter4
0x14003a46a  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14003a470  mov     rcx, r14; BugCheckParameter1
0x14003a473  call    UlBugCheckEx
0x14003a479  lea     rsi, [r8+280h]
0x14003a480  mov     rcx, rsi; SpinLock
0x14003a483  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a48a  nop     dword ptr [rax+rax+00h]
0x14003a48f  mov     rcx, [rsp+0F8h+var_70]
0x14003a497  cmp     byte ptr [rcx+316h], 0
0x14003a49e  jnz     loc_14003A699
0x14003a4a4  mov     word ptr [rcx+314h], 100h
0x14003a4ad  movzx   edx, al; NewIrql
0x14003a4b0  mov     rcx, rsi; SpinLock
0x14003a4b3  call    cs:__imp_KeReleaseSpinLock
0x14003a4ba  nop     dword ptr [rax+rax+00h]
0x14003a4bf  jmp     loc_14003A1D4
0x14003a4c4  movzx   r15d, r14w
0x14003a4c8  jmp     loc_14003A19B
0x14003a4cd  xor     r9d, r9d
0x14003a4d0  xor     r12d, r12d
0x14003a4d3  jmp     loc_14003A17F
0x14003a4d8  mov     edx, 10Bh
0x14003a4dd  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x14003a4e4  mov     ecx, 408h
0x14003a4e9  call    WPP_SF_
0x14003a4ee  jmp     loc_14003A321
0x14003a4f3  inc     dword ptr [rdi+150h]
0x14003a4f9  jmp     loc_14003A0FD
0x14003a4fe  call    cs:__imp_KeGetCurrentIrql
0x14003a505  nop     dword ptr [rax+rax+00h]
0x14003a50a  test    al, al
0x14003a50c  jnz     short loc_14003A576
0x14003a50e  xor     sil, sil
0x14003a511  xorps   xmm0, xmm0
0x14003a514  movups  xmmword ptr [rsp+0F8h+var_60], xmm0
0x14003a51c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14003a520  jz      short loc_14003A59C
0x14003a522  mov     rcx, rdi
0x14003a525  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003a52c  nop     dword ptr [rax+rax+00h]
0x14003a531  mov     rbp, rax
0x14003a534  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003a53b  mov     sil, 1
0x14003a53e  jnz     loc_14003A6B2
0x14003a544  mov     rcx, rbx
0x14003a547  call    UlFreeHttpConnection
0x14003a54c  test    sil, sil
0x14003a54f  jz      loc_14003A314
0x14003a555  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003a55c  jnz     loc_14003A84A
0x14003a562  mov     rcx, rbp
0x14003a565  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14003a56c  nop     dword ptr [rax+rax+00h]
0x14003a571  jmp     loc_14003A314
0x14003a576  mov     dword ptr [rsp+0F8h+Irp], 0FFFFFFFFh
0x14003a57e  lea     r8, UlFreeHttpConnection
0x14003a585  mov     r9b, 1
0x14003a588  mov     qword ptr [rsp+0F8h+var_D8], rdi
0x14003a58d  mov     rdx, rbx
0x14003a590  xor     ecx, ecx
0x14003a592  call    UlThreadPoolEnqueueWorkItem
0x14003a597  jmp     loc_14003A314
0x14003a59c  mov     rbp, [rsp+0F8h+var_60+8]
0x14003a5a4  jmp     short loc_14003A544
0x14003a5a6  test    rcx, rcx
0x14003a5a9  jnz     short loc_14003A5B7
0x14003a5ab  cmp     [rbx+10h], rcx
0x14003a5af  jnz     short loc_14003A5B7
0x14003a5b1  cmp     [rbx+20h], rcx
0x14003a5b5  jz      short loc_14003A576
0x14003a5b7  mov     r9d, 0DBh; BugCheckParameter4
0x14003a5bd  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003a5c4  mov     rdx, rbx; BugCheckParameter2
0x14003a5c7  mov     ecx, 1; BugCheckParameter1
0x14003a5cc  call    UlBugCheckEx
0x14003a5d2  test    rdi, rdi
  ... truncated ...
```
