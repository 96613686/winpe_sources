# UlpSendSimpleStatusWorker

- ea: `0x140039fd0`
- end: `0x14003a848`
- name: `UlpSendSimpleStatusWorker`
- size: `2168`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x14007d560`

## callees

- `0x14000a350`
- `0x14000a520`
- `0x14000e420`
- `0x14002186c`
- `0x140021f80`
- `0x140022610`
- `0x1400397b0`
- `0x140039c60`
- `0x140039fd0`
- `0x14003bf00`
- `0x1400ca7e4`
- `0x14012a480`
- `0x14015596c`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d32ac`
- `0x1401d35ac`
- `0x1401d9cac`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003a4de`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a764`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a4de`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a764`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003a505`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003a505`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003a545`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14003a545`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a116`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a493`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a116`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a493`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003a3eb`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003a3eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a0ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a463`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a0ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a463`

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
  PIRP Irp; // [rsp+28h] [rbp-D0h]
  int v52; // [rsp+80h] [rbp-78h]
  __int64 v53; // [rsp+88h] [rbp-70h]
  __int64 v54; // [rsp+90h] [rbp-68h] BYREF
  __int64 v55[4]; // [rsp+98h] [rbp-60h] BYREF
  char v56; // [rsp+100h] [rbp+8h] BYREF
  unsigned __int8 v57; // [rsp+108h] [rbp+10h] BYREF
  char v58; // [rsp+110h] [rbp+18h]
  int v59; // [rsp+118h] [rbp+20h]

  v3 = 0;
  v56 = 0;
  v58 = 0;
  v57 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 266, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1);
  v5 = *(_DWORD *)(a1 + 48);
  v6 = *(_BYTE *)(a1 + 52);
  v57 = v6;
  v52 = v5;
  if ( v5 == 2 )
  {
    v7 = *(_QWORD *)(a1 + 80);
    v56 = 1;
    v3 = *(_QWORD *)(v7 + 24);
    v8 = _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
    if ( UxDebugCheckRefcount && v8 <= -1 )
      UlBugCheckEx(3u, v3 + 40, 0x21u, v8);
    v6 = v57;
    v58 = 1;
  }
  v9 = *(_QWORD *)(a1 + 80);
  v10 = *(unsigned int *)(a1 + 56);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( v9 )
      v49 = *(_QWORD *)(v9 + 64);
    else
      v49 = 0;
    WPP_SF_qiIlqq(v49, &v56, a3, v9, v49, v10, v6, 0, &v56);
  }
  if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
    UlBugCheckEx(4u, 0, (ULONG_PTR)"minio\\http\\sys\\sendresponse.c", 0x15DEu);
  v11 = *(_QWORD *)(v9 + 24);
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 640));
  ++*(_DWORD *)(v9 + 1624);
  v14 = v12;
  ++*(_DWORD *)(v11 + 336);
  if ( v56 && *(_DWORD *)(v11 + 336) >= 3u )
  {
    *(_BYTE *)(v11 + 521) = 1;
    *(_BYTE *)(v11 + 522) = v6;
    *(_BYTE *)(v11 + 523) = 1;
    v56 = 0;
  }
  LOBYTE(v13) = 1;
  UlSetBundleTimerEx(v11 + 648, 2, v10, v13);
  KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 640), v14);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 82, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
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
      WPP_SF_qiqLqq(1033, 22, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v15, v50, a1 + 328, 1, v28, a1 + 488);
    }
    v29 = UlpSanitizeResponseHeaders(v15, a1 + 328, v28, v27, a1 + 488);
    v30 = v29;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 23, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v29);
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
  v59 = v19;
  if ( v57 )
    v20 = 3;
  else
    v20 = 4;
  v21 = *(_QWORD **)(a1 + 80);
  *(_OWORD *)v55 = 0;
  v22 = v21[3];
  v53 = v22;
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
    v22 = v53;
  }
  if ( (v20 & 1) != 0 )
  {
    v37 = (KSPIN_LOCK *)(v22 + 640);
    v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v22 + 640));
    if ( *(_BYTE *)(v53 + 790) )
      v20 &= ~2u;
    else
      *(_WORD *)(v53 + 788) = 256;
    KeReleaseSpinLock(v37, v38);
  }
  v23 = 0;
  v54 = 0;
  if ( UlHkeQosClassficationEnabled && (UlpHkeAcquireQoS(v21, &v54), (v23 = v54) != 0) )
  {
    v20 |= 0x8000u;
    v24 = v54;
  }
  else
  {
    v24 = v21[310];
    if ( v24 )
      v20 |= 0x4000u;
  }
  if ( v21[8] )
    v55[0] = (__int64)(v21 + 9);
  v25 = UxTpTransmitPacket(
          (int)v53 + 976,
          v17,
          v59,
          0,
          v20,
          0,
          (__int64)UlpRestartSendSimpleStatus,
          a1,
          (__int64)v21,
          v24,
          0,
          0,
          (__int64)v55,
          v18,
          0);
  if ( v23 )
    UlHkeDereferenceCalloutContext(v23, 10);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 107, WPP_682cf469470432b235cb9a4961616e40_Traceguids, (unsigned int)v25);
  if ( v52 == 2 )
  {
    if ( v56 || (UlSetPostSendState(v3, &v56, &v57), v56) )
      UlResumeParsing(v3, v57);
  }
  if ( v25 < 0 )
LABEL_50:
    UlpRestartSendSimpleStatus(a1);
  if ( v58 )
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
          *(_OWORD *)v55 = 0;
          if ( v35 == -1 )
          {
            v43 = v55[1];
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
      LODWORD(Irp) = -1;
      LOBYTE(v34) = 1;
      UlThreadPoolEnqueueWorkItem(0, v3 + 64, UlFreeHttpConnection, v34, v35, Irp);
    }
  }
LABEL_36:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 267, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids);
}

```

## disassembly

```asm
0x140039fd0  mov     rax, rsp
0x140039fd3  push    rbx
0x140039fd4  push    rbp
0x140039fd5  push    rsi
0x140039fd6  sub     rsp, 0E0h
0x140039fdd  xor     ebp, ebp
0x140039fdf  mov     byte ptr [rax+8], 0
0x140039fe3  mov     [rsp+0F8h+arg_10], bpl
0x140039feb  mov     rbx, rcx
0x140039fee  mov     byte ptr [rax+10h], 0
0x140039ff2  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140039ff9  jnz     loc_14003A746
0x140039fff  mov     eax, [rbx+30h]
0x14003a002  movzx   esi, byte ptr [rbx+34h]
0x14003a006  mov     [rsp+0F8h+arg_8], sil
0x14003a00e  mov     [rsp+0F8h+var_38], r14
0x14003a016  mov     [rsp+0F8h+var_78], eax
0x14003a01d  cmp     eax, 2
0x14003a020  jnz     short loc_14003A05E
0x14003a022  mov     rax, [rbx+50h]
0x14003a026  mov     [rsp+0F8h+arg_0], 1
0x14003a02e  mov     rbp, [rax+18h]
0x14003a032  mov     eax, 1
0x14003a037  lea     rdx, [rbp+28h]; BugCheckParameter2
0x14003a03b  lock xadd [rdx], eax
0x14003a03f  inc     eax
0x14003a041  cmp     cs:UxDebugCheckRefcount, 0
0x14003a048  jnz     loc_14003A33B
0x14003a04e  movzx   esi, [rsp+0F8h+arg_8]
0x14003a056  mov     [rsp+0F8h+arg_10], 1
0x14003a05e  mov     r14, [rbx+50h]
0x14003a062  mov     [rsp+0F8h+var_28], r12
0x14003a06a  mov     r12d, [rbx+38h]
0x14003a06e  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a075  jnz     loc_14003A6BD
0x14003a07b  cmp     cs:UxEnableIrqlEnforcement, 0
0x14003a082  mov     [rsp+0F8h+var_40], r15
0x14003a08a  jnz     loc_14003A764
0x14003a090  mov     [rsp+0F8h+var_20], rdi
0x14003a098  mov     rdi, [r14+18h]
0x14003a09c  mov     [rsp+0F8h+var_30], r13
0x14003a0a4  lea     rcx, [rdi+280h]; SpinLock
0x14003a0ab  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a0b2  nop     dword ptr [rax+rax+00h]
0x14003a0b7  inc     dword ptr [r14+658h]
0x14003a0be  movzx   r13d, al
0x14003a0c2  cmp     cs:UxKirHttpBugFix25Q1, 0
0x14003a0c9  jz      loc_14003A4D3
0x14003a0cf  mov     eax, [rdi+150h]
0x14003a0d5  inc     eax
0x14003a0d7  mov     [rdi+150h], eax
0x14003a0dd  cmp     [rsp+0F8h+arg_0], 0
0x14003a0e5  jz      short loc_14003A0F4
0x14003a0e7  cmp     dword ptr [rdi+150h], 3
0x14003a0ee  jnb     loc_14003A792
0x14003a0f4  lea     rcx, [rdi+288h]
0x14003a0fb  mov     r9b, 1
0x14003a0fe  mov     r8, r12
0x14003a101  mov     edx, 2
0x14003a106  call    UlSetBundleTimerEx
0x14003a10b  movzx   edx, r13b; NewIrql
0x14003a10f  lea     rcx, [rdi+280h]; SpinLock
0x14003a116  call    cs:__imp_KeReleaseSpinLock
0x14003a11d  nop     dword ptr [rax+rax+00h]
0x14003a122  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a129  jnz     loc_14003A7B4
0x14003a12f  mov     rdi, [rbx+50h]
0x14003a133  mov     r14d, 3
0x14003a139  cmp     byte ptr [rdi+0C8Eh], 0
0x14003a140  jnz     loc_14003A358
0x14003a146  mov     rax, [rbx+48h]
0x14003a14a  lea     r12, [rbx+58h]
0x14003a14e  mov     [r12], r14d
0x14003a152  xor     r13d, r13d
0x14003a155  mov     [rbx+60h], rax
0x14003a159  mov     r9d, 1
0x14003a15f  cmp     [rsp+0F8h+arg_8], 0
0x14003a167  mov     [rsp+0F8h+arg_18], r9d
0x14003a16f  jnz     loc_14003A4A4
0x14003a175  mov     r15d, 4
0x14003a17b  mov     rdi, [rbx+50h]
0x14003a17f  xorps   xmm0, xmm0
0x14003a182  movups  xmmword ptr [rsp+0F8h+var_60], xmm0
0x14003a18a  mov     r8, [rdi+18h]
0x14003a18e  mov     [rsp+0F8h+var_70], r8
0x14003a196  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a19d  lea     r10, UlpRestartSendSimpleStatus
0x14003a1a4  jnz     loc_14003A5B2
0x14003a1aa  test    r15b, 1
0x14003a1ae  jnz     loc_14003A459
0x14003a1b4  xor     esi, esi
0x14003a1b6  cmp     cs:UlHkeQosClassficationEnabled, esi
0x14003a1bc  mov     [rsp+0F8h+var_68], rsi
0x14003a1c4  jz      short loc_14003A1E7
0x14003a1c6  lea     rdx, [rsp+0F8h+var_68]
0x14003a1ce  mov     rcx, rdi
0x14003a1d1  call    UlpHkeAcquireQoS
0x14003a1d6  mov     rsi, [rsp+0F8h+var_68]
0x14003a1de  test    rsi, rsi
0x14003a1e1  jnz     loc_14003A32D
0x14003a1e7  mov     rdx, [rdi+9B0h]
0x14003a1ee  test    rdx, rdx
0x14003a1f1  jnz     loc_14003A687
0x14003a1f7  cmp     qword ptr [rdi+40h], 0
0x14003a1fc  jz      short loc_14003A20A
0x14003a1fe  lea     rax, [rdi+48h]
0x14003a202  mov     [rsp+0F8h+var_60], rax
0x14003a20a  mov     rcx, [rsp+0F8h+var_70]
0x14003a212  lea     rax, [rsp+0F8h+var_60]
0x14003a21a  xor     r8d, r8d
0x14003a21d  add     rcx, 3D0h; int
0x14003a224  mov     [rsp+0F8h+var_88], r8; __int64
0x14003a229  xor     r9d, r9d; int
0x14003a22c  mov     [rsp+0F8h+var_90], r13; __int64
0x14003a231  mov     [rsp+0F8h+var_98], rax; __int64
0x14003a236  lea     rax, UlpRestartSendSimpleStatus
0x14003a23d  mov     [rsp+0F8h+var_A0], r8; __int64
0x14003a242  mov     [rsp+0F8h+var_A8], r8; __int64
0x14003a247  mov     [rsp+0F8h+var_B0], rdx; __int64
0x14003a24c  mov     rdx, r12; int
0x14003a24f  mov     [rsp+0F8h+var_B8], rdi; __int64
0x14003a254  mov     [rsp+0F8h+var_C0], rbx; __int64
0x14003a259  mov     [rsp+0F8h+var_C8], rax; __int64
0x14003a25e  mov     [rsp+0F8h+Irp], r8; Irp
0x14003a263  mov     r8d, [rsp+0F8h+arg_18]; int
0x14003a26b  mov     [rsp+0F8h+var_D8], r15w; __int16
0x14003a271  call    UxTpTransmitPacket
0x14003a276  mov     edi, eax
0x14003a278  test    rsi, rsi
0x14003a27b  jnz     loc_14003A7CF
0x14003a281  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a288  jnz     loc_14003A7E1
0x14003a28e  cmp     [rsp+0F8h+var_78], 2
0x14003a296  jnz     short loc_14003A2B6
0x14003a298  cmp     [rsp+0F8h+arg_0], 0
0x14003a2a0  jz      loc_14003A7FF
0x14003a2a6  movzx   edx, [rsp+0F8h+arg_8]
0x14003a2ae  mov     rcx, rbp
0x14003a2b1  call    UlResumeParsing
0x14003a2b6  test    edi, edi
0x14003a2b8  js      loc_14003A3D5
0x14003a2be  cmp     [rsp+0F8h+arg_10], 0
0x14003a2c6  mov     r13, [rsp+0F8h+var_30]
0x14003a2ce  jz      short loc_14003A2F4
0x14003a2d0  lea     rdx, [rbp+28h]; BugCheckParameter2
0x14003a2d4  mov     eax, 0FFFFFFFFh
0x14003a2d9  lock xadd [rdx], eax
0x14003a2dd  dec     eax
0x14003a2df  cmp     cs:UxDebugCheckRefcount, 0
0x14003a2e6  jnz     loc_14003A43E
0x14003a2ec  test    eax, eax
0x14003a2ee  jz      loc_14003A3E7
0x14003a2f4  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14003a2fb  jnz     loc_14003A4B8
0x14003a301  mov     rdi, [rsp+0F8h+var_20]
0x14003a309  mov     r15, [rsp+0F8h+var_40]
0x14003a311  mov     r12, [rsp+0F8h+var_28]
0x14003a319  mov     r14, [rsp+0F8h+var_38]
0x14003a321  add     rsp, 0E0h
0x14003a328  pop     rsi
0x14003a329  pop     rbp
0x14003a32a  pop     rbx
0x14003a32b  retn
0x14003a32d  or      r15w, 8000h
0x14003a333  mov     rdx, rsi
0x14003a336  jmp     loc_14003A1F7
0x14003a33b  cmp     eax, 0FFFFFFFFh
0x14003a33e  jg      loc_14003A04E
0x14003a344  movsxd  r9, eax; BugCheckParameter4
0x14003a347  mov     ecx, 3; BugCheckParameter1
0x14003a34c  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14003a352  call    UlBugCheckEx
0x14003a358  mov     r12d, [rbx+0C4h]
0x14003a35f  lea     r13, [rbx+1E8h]
0x14003a366  mov     rsi, [rbx+0C8h]
0x14003a36d  lea     r15, [rbx+148h]
0x14003a374  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a37b  jnz     loc_14003A6FF
0x14003a381  mov     r9d, r12d
0x14003a384  mov     qword ptr [rsp+0F8h+var_D8], r13
0x14003a389  mov     r8, rsi
0x14003a38c  mov     rdx, r15
0x14003a38f  mov     rcx, rdi
0x14003a392  call    UlpSanitizeResponseHeaders
0x14003a397  mov     edi, eax
0x14003a399  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14003a3a0  jnz     loc_14003A62F
0x14003a3a6  test    edi, edi
0x14003a3a8  jns     loc_14003A4AD
0x14003a3ae  movzx   esi, cs:byte_1401A3780
0x14003a3b5  cmp     byte ptr cs:xmmword_1401A2CA0+2, 0
0x14003a3bc  jl      loc_14003A64D
0x14003a3c2  test    sil, sil
0x14003a3c5  jz      short loc_14003A3D5
0x14003a3c7  mov     rcx, [rbx+50h]
0x14003a3cb  mov     r8d, edi
0x14003a3ce  xor     edx, edx
0x14003a3d0  call    UxPktMonTraceDropHttpSend
0x14003a3d5  xor     r8d, r8d
0x14003a3d8  mov     edx, edi
0x14003a3da  mov     rcx, rbx; BugCheckParameter2
0x14003a3dd  call    UlpRestartSendSimpleStatus
0x14003a3e2  jmp     loc_14003A2BE
0x14003a3e7  lea     rbx, [rbp+40h]
0x14003a3eb  call    cs:__imp_IoGetCurrentProcess
0x14003a3f2  nop     dword ptr [rax+rax+00h]
0x14003a3f7  cmp     cs:UxSystemProcess, rax
0x14003a3fe  mov     rdi, [rbp+440h]
0x14003a405  mov     rcx, [rbx]
0x14003a408  jnz     loc_14003A586
0x14003a40e  test    rcx, rcx
0x14003a411  jnz     short loc_14003A423
0x14003a413  cmp     [rbx+10h], rcx
0x14003a417  jnz     short loc_14003A423
0x14003a419  cmp     [rbx+20h], rcx
0x14003a41d  jz      loc_14003A4DE
0x14003a423  mov     r9d, 0E1h; BugCheckParameter4
0x14003a429  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003a430  mov     rdx, rbx; BugCheckParameter2
0x14003a433  mov     ecx, 1; BugCheckParameter1
0x14003a438  call    UlBugCheckEx
0x14003a43e  cmp     eax, 0FFFFFFFFh
0x14003a441  jg      loc_14003A2EC
0x14003a447  movsxd  r9, eax; BugCheckParameter4
0x14003a44a  mov     r8d, 21h ; '!'; BugCheckParameter3
0x14003a450  mov     rcx, r14; BugCheckParameter1
0x14003a453  call    UlBugCheckEx
0x14003a459  lea     rsi, [r8+280h]
0x14003a460  mov     rcx, rsi; SpinLock
0x14003a463  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a46a  nop     dword ptr [rax+rax+00h]
0x14003a46f  mov     rcx, [rsp+0F8h+var_70]
0x14003a477  cmp     byte ptr [rcx+316h], 0
0x14003a47e  jnz     loc_14003A679
0x14003a484  mov     word ptr [rcx+314h], 100h
0x14003a48d  movzx   edx, al; NewIrql
0x14003a490  mov     rcx, rsi; SpinLock
0x14003a493  call    cs:__imp_KeReleaseSpinLock
0x14003a49a  nop     dword ptr [rax+rax+00h]
0x14003a49f  jmp     loc_14003A1B4
0x14003a4a4  movzx   r15d, r14w
0x14003a4a8  jmp     loc_14003A17B
0x14003a4ad  xor     r9d, r9d
0x14003a4b0  xor     r12d, r12d
0x14003a4b3  jmp     loc_14003A15F
0x14003a4b8  mov     edx, 10Bh
0x14003a4bd  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x14003a4c4  mov     ecx, 408h
0x14003a4c9  call    WPP_SF_
0x14003a4ce  jmp     loc_14003A301
0x14003a4d3  inc     dword ptr [rdi+150h]
0x14003a4d9  jmp     loc_14003A0DD
0x14003a4de  call    cs:__imp_KeGetCurrentIrql
0x14003a4e5  nop     dword ptr [rax+rax+00h]
0x14003a4ea  test    al, al
0x14003a4ec  jnz     short loc_14003A556
0x14003a4ee  xor     sil, sil
0x14003a4f1  xorps   xmm0, xmm0
0x14003a4f4  movups  xmmword ptr [rsp+0F8h+var_60], xmm0
0x14003a4fc  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14003a500  jz      short loc_14003A57C
0x14003a502  mov     rcx, rdi
0x14003a505  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003a50c  nop     dword ptr [rax+rax+00h]
0x14003a511  mov     rbp, rax
0x14003a514  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003a51b  mov     sil, 1
0x14003a51e  jnz     loc_14003A692
0x14003a524  mov     rcx, rbx
0x14003a527  call    UlFreeHttpConnection
0x14003a52c  test    sil, sil
0x14003a52f  jz      loc_14003A2F4
0x14003a535  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x14003a53c  jnz     loc_14003A82A
0x14003a542  mov     rcx, rbp
0x14003a545  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14003a54c  nop     dword ptr [rax+rax+00h]
0x14003a551  jmp     loc_14003A2F4
0x14003a556  mov     dword ptr [rsp+0F8h+Irp], 0FFFFFFFFh
0x14003a55e  lea     r8, UlFreeHttpConnection
0x14003a565  mov     r9b, 1
0x14003a568  mov     qword ptr [rsp+0F8h+var_D8], rdi
0x14003a56d  mov     rdx, rbx
0x14003a570  xor     ecx, ecx
0x14003a572  call    UlThreadPoolEnqueueWorkItem
0x14003a577  jmp     loc_14003A2F4
0x14003a57c  mov     rbp, [rsp+0F8h+var_60+8]
0x14003a584  jmp     short loc_14003A524
0x14003a586  test    rcx, rcx
0x14003a589  jnz     short loc_14003A597
0x14003a58b  cmp     [rbx+10h], rcx
0x14003a58f  jnz     short loc_14003A597
0x14003a591  cmp     [rbx+20h], rcx
0x14003a595  jz      short loc_14003A556
0x14003a597  mov     r9d, 0DBh; BugCheckParameter4
0x14003a59d  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003a5a4  mov     rdx, rbx; BugCheckParameter2
0x14003a5a7  mov     ecx, 1; BugCheckParameter1
0x14003a5ac  call    UlBugCheckEx
0x14003a5b2  test    rdi, rdi
  ... truncated ...
```
