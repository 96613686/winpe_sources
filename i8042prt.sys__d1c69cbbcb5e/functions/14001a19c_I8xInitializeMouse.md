# I8xInitializeMouse

- ea: `0x14001a19c`
- end: `0x14001a7a6`
- name: `I8xInitializeMouse`
- size: `1546`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x14001be20`
- `0x14001eea0`

## callees

- `0x140004530`
- `0x140005440`
- `0x1400059c0`
- `0x1400066d0`
- `0x140006950`
- `0x140007b10`
- `0x140009840`
- `0x14000a394`
- `0x14000a48c`
- `0x14000bb7c`
- `0x14000bc74`
- `0x14000bcf0`
- `0x140019cfc`
- `0x14001a19c`
- `0x14001b574`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001a2eb`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001a2eb`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001a2fa`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001a2fa`

## pseudocode

```c
__int64 __fastcall I8xInitializeMouse(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r13
  int v6; // eax
  int v7; // edx
  unsigned int v8; // esi
  char DeferredRoutine_high; // bl
  int v10; // edi
  int v11; // r12d
  int v12; // r15d
  int v13; // edx
  unsigned int v14; // esi
  __int64 v15; // rdi
  int BytePolled; // eax
  int v17; // edx
  int v18; // r15d
  __int64 v19; // rbx
  int v20; // eax
  int v21; // edx
  int v22; // ebx
  int NumberOfMouseButtons; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int16 v28; // bx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  int v41; // eax
  __int64 v42; // [rsp+28h] [rbp-40h]
  unsigned __int8 v43; // [rsp+40h] [rbp-28h] BYREF
  char v44[7]; // [rsp+41h] [rbp-27h] BYREF
  __int128 v45; // [rsp+48h] [rbp-20h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-10h] BYREF

  v43 = 0;
  v44[0] = 0;
  Interval.QuadPart = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      53,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
  v5 = *a1;
  LOBYTE(a4) = -1;
  LOBYTE(a3) = 2;
  LOBYTE(a2) = 1;
  v45 = 0;
  v6 = I8xPutBytePolled(0, a2, a3, a4);
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        17,
        54,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v6);
    DeferredRoutine_high = HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine);
    v10 = 1074069535;
    *(_QWORD *)&v45 = 1;
    v11 = 1415;
    *((_QWORD *)&v45 + 1) = 0xFF000000D4LL;
    v12 = 4;
    TraceLoggingDeviceNotConnected(v8);
    v14 = -1073741667;
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x8000u;
    if ( !DeferredRoutine_high )
      goto LABEL_60;
    goto LABEL_59;
  }
  *((_WORD *)a1 + 506) = -1;
  *((_WORD *)a1 + 280) = 0;
  Interval.QuadPart = -100;
  v15 = MEMORY[0xFFFFF78000000320];
  do
  {
    BytePolled = I8xGetBytePolled(0, &v43);
    v18 = v43;
    v14 = BytePolled;
    if ( BytePolled >= 0 && v43 == 0xAA )
      goto LABEL_17;
    if ( BytePolled != -1073741643 )
      break;
    KeDelayExecutionThread(0, 0, &Interval);
    v19 = MEMORY[0xFFFFF78000000320];
  }
  while ( (v19 - v15) * KeQueryTimeIncrement() < 100000000 );
  if ( (v14 & 0x80000000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        17,
        55,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v14,
        v18);
    HIDWORD(v45) = v18;
    *(_QWORD *)&v45 = 4;
    v12 = 4;
    DWORD2(v45) = 170;
    v10 = -2147155950;
    v11 = 1420;
    TraceLoggingResetResponseFailed(v14);
    goto LABEL_59;
  }
LABEL_17:
  v20 = I8xGetBytePolled(0, &v43);
  v22 = v43;
  v14 = v20;
  if ( v20 < 0 || v43 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        17,
        56,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v20,
        v43);
    *(_QWORD *)&v45 = 4;
    DWORD2(v45) = 0;
    HIDWORD(v45) = v22;
    TraceLoggingResetResponseFailed(v14);
    if ( (v14 & 0x80000000) == 0 )
      goto LABEL_60;
    v10 = -2147155950;
    v12 = 4;
    v11 = 1425;
    goto LABEL_59;
  }
  if ( *((_BYTE *)a1 + 1108) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        14,
        58,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    *((_DWORD *)a1 + 232) = 16842752;
    I8xFindWheelMouse(a1);
    NumberOfMouseButtons = I8xQueryNumberOfMouseButtons(v44);
    v14 = NumberOfMouseButtons;
    if ( NumberOfMouseButtons < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          17,
          59,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          NumberOfMouseButtons);
      *(_QWORD *)&v45 = 1;
      v10 = -1073414110;
      DWORD2(v45) = 212;
      v11 = 1426;
      v12 = 3;
      TraceLoggingDetectButtonNumbersFailed(v14);
      goto LABEL_59;
    }
    v28 = (unsigned __int8)v44[0];
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dd(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        16,
        60,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v44[0],
        *((_WORD *)a1 + 293));
    if ( (_BYTE)v28 )
      *((_WORD *)a1 + 293) = v28;
    if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
    {
      *((_WORD *)a1 + 293) = 5;
    }
    else if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 8) != 0 )
    {
      *((_WORD *)a1 + 293) = 3;
    }
    LOBYTE(v27) = -13;
    LOBYTE(v25) = 1;
    LOBYTE(v26) = 2;
    v29 = I8xPutBytePolled(0, v25, v26, v27);
    v14 = v29;
    if ( v29 >= 0 )
    {
      LOBYTE(v32) = *((_BYTE *)a1 + 588);
      LOBYTE(v31) = 2;
      LOBYTE(v30) = 1;
      v33 = I8xPutBytePolled(0, v30, v31, v32);
      v14 = v33;
      if ( v33 >= 0 )
      {
        LOBYTE(v36) = -24;
        LOBYTE(v35) = 2;
        LOBYTE(v34) = 1;
        v37 = I8xPutBytePolled(0, v34, v35, v36);
        v14 = v37;
        if ( v37 >= 0 )
        {
          LOBYTE(v40) = *((_BYTE *)a1 + 1105);
          LOBYTE(v39) = 2;
          LOBYTE(v38) = 1;
          v41 = I8xPutBytePolled(0, v38, v39, v40);
          v14 = v41;
          if ( v41 >= 0 )
          {
LABEL_60:
            *((_BYTE *)a1 + 1015) = 0;
            a1[125] = 4;
            *((_BYTE *)a1 + 1104) = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v13,
                15,
                65,
                (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
            return v14;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v42) = v41;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v13,
              17,
              64,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              v42);
          }
          v11 = 1465;
          HIDWORD(v45) = *((unsigned __int8 *)a1 + 1105);
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v42) = v37;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v38,
              17,
              63,
              (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
              v42);
          }
          v11 = 1455;
          HIDWORD(v45) = 232;
        }
        DWORD2(v45) = 212;
        *(_QWORD *)&v45 = 1;
        v10 = -1073414121;
        v12 = 4;
        TraceLoggingSetResolutionFailed(v14);
LABEL_59:
        I8xLogError(v5, v10, v11, v14, (__int64)&v45, v12);
        goto LABEL_60;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v42) = v33;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v34,
          17,
          62,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          v42);
      }
      v11 = 1445;
      HIDWORD(v45) = *((unsigned __int16 *)a1 + 294);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v42) = v29;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v30,
          17,
          61,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          v42);
      }
      v11 = 1435;
      HIDWORD(v45) = 243;
    }
    DWORD2(v45) = 212;
    *(_QWORD *)&v45 = 1;
    v10 = -1073414122;
    v12 = 4;
    TraceLoggingSetSampleRateFailed(v14);
    goto LABEL_59;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      14,
      57,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14001a19c  push    rbp
0x14001a19e  push    rbx
0x14001a19f  push    rsi
0x14001a1a0  push    rdi
0x14001a1a1  push    r12
0x14001a1a3  push    r13
0x14001a1a5  push    r14
0x14001a1a7  push    r15
0x14001a1a9  mov     rbp, rsp
0x14001a1ac  sub     rsp, 68h
0x14001a1b0  xor     r12d, r12d
0x14001a1b3  mov     r14, rcx
0x14001a1b6  mov     [rbp+var_28], r12b
0x14001a1ba  mov     [rbp+var_27], r12b
0x14001a1be  mov     qword ptr [rbp+Interval], r12
0x14001a1c2  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001a1c9  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a1d0  lea     rdi, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a1d7  jz      short loc_14001A1F8
0x14001a1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1e0  lea     r9d, [r12+35h]
0x14001a1e5  lea     r8d, [r12+0Fh]
0x14001a1ea  mov     [rsp+68h+var_48], rdi
0x14001a1ef  mov     rcx, [rcx+40h]
0x14001a1f3  call    WPP_RECORDER_SF_
0x14001a1f8  mov     r13, [r14]
0x14001a1fb  xorps   xmm0, xmm0
0x14001a1fe  mov     r9b, 0FFh
0x14001a201  mov     r8b, 2
0x14001a204  mov     dl, 1
0x14001a206  xor     ecx, ecx
0x14001a208  movups  [rbp+var_20], xmm0
0x14001a20c  call    I8xPutBytePolled
0x14001a211  mov     esi, eax
0x14001a213  test    eax, eax
0x14001a215  jns     short loc_14001A294
0x14001a217  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a21e  jz      short loc_14001A243
0x14001a220  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a227  mov     r9d, 36h ; '6'
0x14001a22d  mov     dword ptr [rsp+68h+var_40], eax
0x14001a231  mov     [rsp+68h+var_48], rdi
0x14001a236  mov     rcx, [rcx+40h]
0x14001a23a  lea     r8d, [r9-25h]
0x14001a23e  call    WPP_RECORDER_SF_D
0x14001a243  mov     bl, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7
0x14001a249  mov     ecx, esi
0x14001a24b  mov     edi, 4005001Fh
0x14001a250  mov     qword ptr [rbp+var_20], 1
0x14001a258  mov     r12d, 587h
0x14001a25e  mov     dword ptr [rbp+var_20+8], 0D4h
0x14001a265  mov     dword ptr [rbp+var_20+0Ch], 0FFh
0x14001a26c  mov     r15d, 4
0x14001a272  call    TraceLoggingDeviceNotConnected
0x14001a277  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001a27e  mov     esi, 0C000009Dh
0x14001a283  bts     dword ptr [rax], 0Fh
0x14001a287  test    bl, bl
0x14001a289  jz      loc_14001A740
0x14001a28f  jmp     loc_14001A722
0x14001a294  mov     rbx, 0FFFFF78000000320h
0x14001a29e  mov     word ptr [r14+3F4h], 0FFFFh
0x14001a2a8  mov     [r14+230h], r12w
0x14001a2b0  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFFFF9Ch
0x14001a2b8  mov     rdi, [rbx]
0x14001a2bb  lea     rdx, [rbp+var_28]
0x14001a2bf  xor     ecx, ecx
0x14001a2c1  call    I8xGetBytePolled
0x14001a2c6  movzx   r15d, [rbp+var_28]
0x14001a2cb  mov     esi, eax
0x14001a2cd  test    eax, eax
0x14001a2cf  js      short loc_14001A2DB
0x14001a2d1  cmp     r15b, 0AAh
0x14001a2d5  jz      loc_14001A392
0x14001a2db  cmp     esi, 0C00000B5h
0x14001a2e1  jnz     short loc_14001A321
0x14001a2e3  lea     r8, [rbp+Interval]; Interval
0x14001a2e7  xor     edx, edx; Alertable
0x14001a2e9  xor     ecx, ecx; WaitMode
0x14001a2eb  call    cs:__imp_KeDelayExecutionThread
0x14001a2f2  nop     dword ptr [rax+rax+00h]
0x14001a2f7  mov     rbx, [rbx]
0x14001a2fa  call    cs:__imp_KeQueryTimeIncrement
0x14001a301  nop     dword ptr [rax+rax+00h]
0x14001a306  sub     rbx, rdi
0x14001a309  mov     eax, eax
0x14001a30b  imul    rax, rbx
0x14001a30f  mov     rbx, 0FFFFF78000000320h
0x14001a319  cmp     rax, 5F5E100h
0x14001a31f  jl      short loc_14001A2BB
0x14001a321  test    esi, esi
0x14001a323  jns     short loc_14001A392
0x14001a325  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a32c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a333  jz      short loc_14001A364
0x14001a335  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a33c  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a343  mov     r9d, 37h ; '7'
0x14001a349  mov     [rsp+68h+var_38], r15d
0x14001a34e  mov     dword ptr [rsp+68h+var_40], esi
0x14001a352  mov     [rsp+68h+var_48], rax
0x14001a357  mov     rcx, [rcx+40h]
0x14001a35b  lea     r8d, [r9-26h]
0x14001a35f  call    WPP_RECORDER_SF_dD
0x14001a364  mov     ecx, 4
0x14001a369  mov     dword ptr [rbp+var_20+0Ch], r15d
0x14001a36d  mov     qword ptr [rbp+var_20], rcx
0x14001a371  mov     r15d, ecx
0x14001a374  mov     ecx, esi
0x14001a376  mov     dword ptr [rbp+var_20+8], 0AAh
0x14001a37d  mov     edi, 80050012h
0x14001a382  mov     r12d, 58Ch
0x14001a388  call    TraceLoggingResetResponseFailed
0x14001a38d  jmp     loc_14001A722
0x14001a392  lea     rdx, [rbp+var_28]
0x14001a396  xor     ecx, ecx
0x14001a398  call    I8xGetBytePolled
0x14001a39d  movzx   ebx, [rbp+var_28]
0x14001a3a1  mov     esi, eax
0x14001a3a3  test    eax, eax
0x14001a3a5  js      loc_14001A6B9
0x14001a3ab  test    bl, bl
0x14001a3ad  jnz     loc_14001A6B9
0x14001a3b3  cmp     [r14+454h], r12b
0x14001a3ba  jnz     short loc_14001A3F9
0x14001a3bc  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a3c3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a3ca  jz      short loc_14001A3F2
0x14001a3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3d3  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a3da  mov     r9d, 39h ; '9'
0x14001a3e0  mov     [rsp+68h+var_48], rax
0x14001a3e5  mov     rcx, [rcx+40h]
0x14001a3e9  lea     r8d, [r9-2Bh]
0x14001a3ed  call    WPP_RECORDER_SF_
0x14001a3f2  xor     eax, eax
0x14001a3f4  jmp     loc_14001A794
0x14001a3f9  lea     r15, WPP_RECORDER_INITIALIZED
0x14001a400  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a407  lea     rdi, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a40e  jz      short loc_14001A42F
0x14001a410  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a417  mov     r9d, 3Ah ; ':'
0x14001a41d  mov     [rsp+68h+var_48], rdi
0x14001a422  mov     rcx, [rcx+40h]
0x14001a426  lea     r8d, [r9-2Ch]
0x14001a42a  call    WPP_RECORDER_SF_
0x14001a42f  mov     rcx, r14
0x14001a432  mov     dword ptr [r14+3A0h], 1010000h
0x14001a43d  call    I8xFindWheelMouse
0x14001a442  lea     rcx, [rbp+var_27]
0x14001a446  call    I8xQueryNumberOfMouseButtons
0x14001a44b  mov     esi, eax
0x14001a44d  test    eax, eax
0x14001a44f  jns     short loc_14001A4A9
0x14001a451  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a458  jz      short loc_14001A47D
0x14001a45a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a461  mov     r9d, 3Bh ; ';'
0x14001a467  mov     dword ptr [rsp+68h+var_40], eax
0x14001a46b  mov     [rsp+68h+var_48], rdi
0x14001a470  mov     rcx, [rcx+40h]
0x14001a474  lea     r8d, [r9-2Ah]
0x14001a478  call    WPP_RECORDER_SF_D
0x14001a47d  mov     ecx, esi
0x14001a47f  mov     qword ptr [rbp+var_20], 1
0x14001a487  mov     edi, 0C0050022h
0x14001a48c  mov     dword ptr [rbp+var_20+8], 0D4h
0x14001a493  mov     r12d, 592h
0x14001a499  mov     r15d, 3
0x14001a49f  call    TraceLoggingDetectButtonNumbersFailed
0x14001a4a4  jmp     loc_14001A722
0x14001a4a9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a4b0  movzx   ebx, [rbp+var_27]
0x14001a4b4  jz      short loc_14001A4E5
0x14001a4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4bd  mov     r9d, 3Ch ; '<'
0x14001a4c3  movzx   eax, word ptr [r14+24Ah]
0x14001a4cb  mov     [rsp+68h+var_38], eax
0x14001a4cf  mov     dword ptr [rsp+68h+var_40], ebx
0x14001a4d3  mov     rcx, [rcx+40h]
0x14001a4d7  lea     r8d, [r9-2Ch]
0x14001a4db  mov     [rsp+68h+var_48], rdi
0x14001a4e0  call    WPP_RECORDER_SF_dd
0x14001a4e5  test    bl, bl
0x14001a4e7  jz      short loc_14001A4F1
0x14001a4e9  mov     [r14+24Ah], bx
0x14001a4f1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001a4f8  mov     ecx, [rax]
0x14001a4fa  bt      ecx, 0Ch
0x14001a4fe  jnb     short loc_14001A50C
0x14001a500  mov     word ptr [r14+24Ah], 5
0x14001a50a  jmp     short loc_14001A522
0x14001a50c  test    cl, 8
0x14001a50f  jz      short loc_14001A522
0x14001a511  mov     word ptr [r14+24Ah], 3
0x14001a51b  lea     r15, WPP_RECORDER_INITIALIZED
0x14001a522  mov     ebx, 1
0x14001a527  mov     r9b, 0F3h
0x14001a52a  mov     dl, bl
0x14001a52c  mov     r8b, 2
0x14001a52f  xor     ecx, ecx
0x14001a531  call    I8xPutBytePolled
0x14001a536  mov     esi, eax
0x14001a538  test    eax, eax
0x14001a53a  jns     short loc_14001A595
0x14001a53c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a543  jz      short loc_14001A566
0x14001a545  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a54c  lea     r9d, [rbx+3Ch]
0x14001a550  mov     dword ptr [rsp+68h+var_40], eax
0x14001a554  lea     r8d, [rbx+10h]
0x14001a558  mov     [rsp+68h+var_48], rdi
0x14001a55d  mov     rcx, [rcx+40h]
0x14001a561  call    WPP_RECORDER_SF_D
0x14001a566  mov     r12d, 59Bh
0x14001a56c  mov     dword ptr [rbp+var_20+0Ch], 0F3h
0x14001a573  mov     ecx, esi
0x14001a575  mov     dword ptr [rbp+var_20+8], 0D4h
0x14001a57c  mov     qword ptr [rbp+var_20], rbx
0x14001a580  mov     edi, 0C0050016h
0x14001a585  mov     r15d, 4
0x14001a58b  call    TraceLoggingSetSampleRateFailed
0x14001a590  jmp     loc_14001A722
0x14001a595  mov     r9b, [r14+24Ch]
0x14001a59c  mov     r8b, 2
0x14001a59f  mov     dl, bl
0x14001a5a1  xor     ecx, ecx
0x14001a5a3  call    I8xPutBytePolled
0x14001a5a8  mov     esi, eax
0x14001a5aa  test    eax, eax
0x14001a5ac  jns     short loc_14001A5ED
0x14001a5ae  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a5b5  jz      short loc_14001A5DA
0x14001a5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a5be  mov     r9d, 3Eh ; '>'
0x14001a5c4  mov     dword ptr [rsp+68h+var_40], eax
0x14001a5c8  mov     [rsp+68h+var_48], rdi
0x14001a5cd  mov     rcx, [rcx+40h]
0x14001a5d1  lea     r8d, [r9-2Dh]
0x14001a5d5  call    WPP_RECORDER_SF_D
0x14001a5da  movzx   eax, word ptr [r14+24Ch]
0x14001a5e2  mov     r12d, 5A5h
0x14001a5e8  mov     dword ptr [rbp+var_20+0Ch], eax
0x14001a5eb  jmp     short loc_14001A573
0x14001a5ed  mov     r9b, 0E8h
0x14001a5f0  mov     r8b, 2
0x14001a5f3  mov     dl, bl
0x14001a5f5  xor     ecx, ecx
0x14001a5f7  call    I8xPutBytePolled
0x14001a5fc  mov     esi, eax
0x14001a5fe  test    eax, eax
0x14001a600  jns     short loc_14001A65D
0x14001a602  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a609  jz      short loc_14001A62E
0x14001a60b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a612  mov     r9d, 3Fh ; '?'
0x14001a618  mov     dword ptr [rsp+68h+var_40], eax
0x14001a61c  mov     [rsp+68h+var_48], rdi
0x14001a621  mov     rcx, [rcx+40h]
0x14001a625  lea     r8d, [r9-2Eh]
0x14001a629  call    WPP_RECORDER_SF_D
0x14001a62e  mov     r12d, 5AFh
0x14001a634  mov     dword ptr [rbp+var_20+0Ch], 0E8h
0x14001a63b  mov     ecx, esi
0x14001a63d  mov     dword ptr [rbp+var_20+8], 0D4h
0x14001a644  mov     qword ptr [rbp+var_20], rbx
0x14001a648  mov     edi, 0C0050017h
0x14001a64d  mov     r15d, 4
0x14001a653  call    TraceLoggingSetResolutionFailed
0x14001a658  jmp     loc_14001A722
0x14001a65d  mov     r9b, [r14+451h]
0x14001a664  mov     r8b, 2
0x14001a667  mov     dl, bl
0x14001a669  xor     ecx, ecx
0x14001a66b  call    I8xPutBytePolled
0x14001a670  mov     esi, eax
0x14001a672  test    eax, eax
0x14001a674  jns     loc_14001A743
0x14001a67a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001a681  jz      short loc_14001A6A6
0x14001a683  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a68a  mov     r9d, 40h ; '@'
0x14001a690  mov     dword ptr [rsp+68h+var_40], eax
0x14001a694  mov     [rsp+68h+var_48], rdi
0x14001a699  mov     rcx, [rcx+40h]
0x14001a69d  lea     r8d, [r9-2Fh]
0x14001a6a1  call    WPP_RECORDER_SF_D
0x14001a6a6  movzx   eax, byte ptr [r14+451h]
0x14001a6ae  mov     r12d, 5B9h
0x14001a6b4  mov     dword ptr [rbp+var_20+0Ch], eax
0x14001a6b7  jmp     short loc_14001A63B
0x14001a6b9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a6c0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a6c7  jz      short loc_14001A6F7
0x14001a6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6d0  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a6d7  mov     r9d, 38h ; '8'
0x14001a6dd  mov     [rsp+68h+var_38], ebx
0x14001a6e1  mov     dword ptr [rsp+68h+var_40], esi
  ... truncated ...
```
