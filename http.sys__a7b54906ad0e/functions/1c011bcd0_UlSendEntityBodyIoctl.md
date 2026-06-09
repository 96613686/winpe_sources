# UlSendEntityBodyIoctl

- ea: `0x1c011bcd0`
- end: `0x1c011c814`
- name: `UlSendEntityBodyIoctl`
- size: `2884`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `34`
- tags: `broker_com_uri`

## callees

- `0x1c0001ae0`
- `0x1c000aca8`
- `0x1c000ad10`
- `0x1c000b018`
- `0x1c000cb50`
- `0x1c000e148`
- `0x1c000fc68`
- `0x1c00102d0`
- `0x1c0010ce8`
- `0x1c0014720`
- `0x1c001a4b0`
- `0x1c001a8ac`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c00298a0`
- `0x1c002bb2c`
- `0x1c002c0e8`
- `0x1c002c2a8`
- `0x1c00311e8`
- `0x1c0031264`
- `0x1c0032300`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f4f0`
- `0x1c0097cfc`
- `0x1c0097d58`
- `0x1c0097da4`
- `0x1c00a13cc`
- `0x1c00bbfe0`
- `0x1c00c0360`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c011bcd0`
- `0x1c0137d14`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1c011c77c`
- `ntoskrnl!IofCompleteRequest` at `0x1c011c77c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c011c5a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c011c5a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c011c10c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c011c10c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c011c100`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c011c100`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c011c0c4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c011c0c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c011c0aa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c011c0aa`

## pseudocode

```c
__int64 __fastcall UlSendEntityBodyIoctl(PIRP Irp, __int64 a2)
{
  __int64 v4; // rsi
  char v5; // r12
  int v6; // edx
  NTSTATUS Consumer; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v11; // r12d
  __int64 v12; // rcx
  __int64 RequestFromId; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  bool v16; // r15
  __int64 v17; // rax
  int v18; // ecx
  char v19; // al
  __int64 v20; // rbx
  __int64 v21; // r12
  unsigned int v22; // eax
  _QWORD *v23; // rdx
  __int64 v24; // r8
  _QWORD *v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rax
  int v29[2]; // [rsp+20h] [rbp-368h]
  PVOID v30; // [rsp+28h] [rbp-360h]
  int v31; // [rsp+84h] [rbp-304h]
  bool v32; // [rsp+88h] [rbp-300h]
  char v33; // [rsp+8Bh] [rbp-2FDh] BYREF
  int v34; // [rsp+8Ch] [rbp-2FCh]
  bool v35; // [rsp+90h] [rbp-2F8h]
  char v36; // [rsp+91h] [rbp-2F7h]
  __int16 v37; // [rsp+94h] [rbp-2F4h] BYREF
  __int64 v38; // [rsp+98h] [rbp-2F0h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-2E8h] BYREF
  PVOID P; // [rsp+A8h] [rbp-2E0h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-2D8h]
  __int64 v42; // [rsp+B8h] [rbp-2D0h]
  __int128 v43; // [rsp+C0h] [rbp-2C8h] BYREF
  int v44[4]; // [rsp+D0h] [rbp-2B8h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-2A8h]
  __int128 v46; // [rsp+F0h] [rbp-298h]
  __int64 v47; // [rsp+100h] [rbp-288h]
  _BYTE v48[144]; // [rsp+110h] [rbp-278h] BYREF
  _QWORD v49[3]; // [rsp+1A0h] [rbp-1E8h] BYREF
  char v50; // [rsp+1B8h] [rbp-1D0h]
  int v51; // [rsp+1B9h] [rbp-1CFh]
  __int16 v52; // [rsp+1BDh] [rbp-1CBh]
  char v53; // [rsp+1BFh] [rbp-1C9h]
  _QWORD v54[2]; // [rsp+1C0h] [rbp-1C8h] BYREF
  __int128 v55; // [rsp+1D0h] [rbp-1B8h]
  _OWORD v56[2]; // [rsp+1E0h] [rbp-1A8h] BYREF
  __int128 v57; // [rsp+200h] [rbp-188h] BYREF
  _BYTE v58[320]; // [rsp+210h] [rbp-178h] BYREF

  *(_QWORD *)&v43 = Irp;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v38 = 0;
  v4 = 0;
  v42 = 0;
  v39 = 0;
  v5 = 0;
  v32 = 0;
  v34 = 0;
  v36 = 0;
  v41 = 0;
  P = 0;
  v33 = 0;
  memset(v48, 0, sizeof(v48));
  v37 = 0;
  v57 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qq(80, WPP_18ca8755388c316524f95a91261e2540_Traceguids, Irp, a2);
  Consumer = UlGetConsumer(*(_QWORD *)(a2 + 48), 1, &v39);
  v31 = Consumer;
  if ( Consumer < 0 )
    goto LABEL_78;
  LOBYTE(v6) = Irp->RequestorMode;
  Consumer = UlpGetSendInfo((_DWORD)Irp, v6, *(_QWORD *)(a2 + 32), *(_DWORD *)(a2 + 16), (__int64)v44);
  v31 = Consumer;
  if ( Consumer < 0 )
    goto LABEL_78;
  Consumer = UlpGetChunkInfo(Irp, v29[0], v58, (__int64)&P, (__int64)&v33);
  v31 = Consumer;
  if ( Consumer < 0 )
  {
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(81, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    goto LABEL_78;
  }
  LOBYTE(v9) = Irp->RequestorMode;
  Consumer = UlpGetLogInfo(Irp, v9, v44, v48);
  v31 = Consumer;
  if ( Consumer < 0 )
    goto LABEL_78;
  v11 = DWORD2(v46);
  v32 = (BYTE8(v46) & 2) == 0;
  if ( (BYTE8(v46) & 2) == 0 )
  {
    v41 = v46;
    *((_QWORD *)&v57 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
    *(_QWORD *)&v57 = v46;
    v12 = *(_QWORD *)(v39 + 8);
    if ( *(_BYTE *)(*(_QWORD *)(v12 + 328) + 1568LL) )
    {
      v55 = *(unsigned __int64 *)(v12 + 328);
      v54[0] = &v57;
      v54[1] = 0;
      McTemplateK0p_UlEtwWriteEventWrapper(v12, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY, v54);
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
    WPP_SF_iD(82, v10, v41, v11);
  RequestFromId = UlGetRequestFromId(v46, v39);
  v4 = RequestFromId;
  v42 = RequestFromId;
  if ( !RequestFromId )
  {
    Consumer = -1073741254;
    v31 = -1073741254;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(83, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v5 = 0;
    goto LABEL_78;
  }
  v15 = *(_QWORD *)(RequestFromId + 24);
  if ( *(_BYTE *)(*(_QWORD *)(v15 + 960) + 1568LL) )
  {
    v56[1] = *(unsigned __int64 *)(v15 + 960);
    v56[0] = (unsigned __int64)(RequestFromId + 72);
    McTemplateK0xx_UlEtwWriteEventWrapper(v15, v14, v56, *(_QWORD *)(RequestFromId + 56), *(_QWORD *)(v15 + 24));
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
    WPP_SF_ii(v15, v14, *(_QWORD *)(v4 + 56), *(_QWORD *)(*(_QWORD *)(v4 + 24) + 24LL));
  if ( *(_QWORD *)(v4 + 2472) )
  {
    v16 = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(*(_QWORD *)(v4 + 24) + 464LL, 0);
    v17 = *(_QWORD *)(v4 + 2496);
    if ( v17 && !*(_DWORD *)(v17 + 136) )
      v16 = *(_DWORD *)(v17 + 256) == 1;
    ExReleasePushLockSharedEx(*(_QWORD *)(v4 + 24) + 464LL, 0);
    KeLeaveCriticalRegion();
    v35 = v16;
    if ( v16 )
      goto LABEL_37;
  }
  else
  {
    v16 = 0;
    v35 = 0;
  }
  if ( *(_DWORD *)(v4 + 2192)
    || (v11 & 4) != 0
    || !UxTpIsFastSendPossible(*(_QWORD *)(v4 + 24) + 840LL)
    || LOWORD(v44[2]) != 1 )
  {
LABEL_37:
    LOBYTE(v18) = v34;
    goto LABEL_38;
  }
  LOBYTE(v18) = v34;
  if ( !*(_DWORD *)P )
  {
    v18 = (unsigned __int8)v34;
    if ( (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF )
      v18 = 1;
    v34 = v18;
    v36 = v18;
  }
LABEL_38:
  v19 = v32 || (v11 & 1) != 0;
  if ( (_BYTE)v18
    || (Consumer = UlCaptureHttpResponse(
                     v39,
                     0,
                     v4,
                     Irp,
                     v44[2],
                     (IRP *)P,
                     Irp->RequestorMode,
                     v11,
                     0,
                     0,
                     v47,
                     0,
                     v19,
                     &v37,
                     &v38),
        v31 = Consumer,
        Consumer >= 0) )
  {
    if ( *(_DWORD *)(v4 + 2192) == 1 )
    {
      Consumer = 0;
      v31 = 0;
      Irp->IoStatus.Information = *(_QWORD *)(v38 + 328);
      v5 = 0;
      goto LABEL_78;
    }
    Consumer = UlCheckSendEntityBodyFlags(v4, v11);
    v31 = Consumer;
    if ( Consumer >= 0 )
    {
      Consumer = UlCheckForZombieConnection(v4, *(_QWORD *)(v4 + 24), v11, v47, Irp->RequestorMode);
      v31 = Consumer;
      if ( Consumer >= 0 )
      {
        if ( !v38
          || !v47
          || *(_DWORD *)(v4 + 2204) != 1
          || (Consumer = UlCaptureUserLogData(v47, v4, v38 + 320), v31 = Consumer, Consumer >= 0) )
        {
          if ( (v11 & 0x100) != 0 )
          {
            v20 = *(_QWORD *)(v4 + 24);
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
              WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v20 + 384, 47, 0, 0, 0, 0);
            HIDWORD(v30) = 0;
            *(_QWORD *)v29 = 0;
            Consumer = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(v20 + 392) + 120LL))(
                         *(_QWORD *)(v20 + 384),
                         47,
                         0);
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
              WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
            v31 = Consumer;
            if ( Consumer < 0 )
            {
              v5 = 1;
              goto LABEL_78;
            }
          }
          if ( (_BYTE)v34 )
          {
            Consumer = UlFastSendHttpResponse(
                         0,
                         v47,
                         (_DWORD)P,
                         1,
                         *((_DWORD *)P + 4),
                         0,
                         0,
                         v11,
                         v4,
                         *(_DWORD *)(*(_QWORD *)(v39 + 8) + 276LL),
                         (__int64)Irp,
                         Irp->RequestorMode,
                         0);
            v31 = Consumer;
          }
          else if ( (unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(v4 + 24), Irp) )
          {
            *(_QWORD *)(v38 + 400) = Irp;
            v21 = v38;
            v38 = 0;
            *(_BYTE *)(v21 + 51) = v16;
            v22 = UlSendHttpResponse(v4, v21, (unsigned int)UlpRestartSendHttpResponseIoctl, v21, 0);
            Consumer = v22;
            v31 = v22;
            if ( v22 != 259 )
            {
              UlpRestartSendHttpResponseIoctl(v21, v22, 0);
              v5 = 1;
              Consumer = 259;
              v31 = 259;
              goto LABEL_78;
            }
          }
          else
          {
            Consumer = -1073741536;
            v31 = -1073741536;
          }
          v5 = 0;
          goto LABEL_78;
        }
        if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
          WPP_SF_D(88, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
        v5 = 0;
      }
      else
      {
        if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
          WPP_SF_D(87, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
        v5 = 0;
      }
    }
    else
    {
      if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
        WPP_SF_D(86, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
      v5 = 0;
    }
  }
  else
  {
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(85, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v5 = 0;
  }
LABEL_78:
  if ( v33 )
    ExFreePoolWithTag(P, 0);
  if ( v4 )
  {
    if ( ((Consumer + 0x80000000) & 0x80000000) == 0 && Consumer != -1073741766 || v5 )
      UlCloseConnection(*(_QWORD *)(v4 + 24));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 48), 0xFFFFFFFF) == 1 )
      UlpQueueFreeHttpRequest(v42);
    Consumer = v31;
  }
  v23 = (_QWORD *)v38;
  if ( v38 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 20), 0xFFFFFFFF) == 1 )
    {
      v24 = *(_QWORD *)(*(_QWORD *)(v23[3] + 24LL) + 952LL);
      v25 = v23 + 52;
      v43 = 0;
      if ( v23[52] || v23[54] || v23[56] )
        UlBugCheckEx(1u, (ULONG_PTR)(v23 + 52), (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x317u);
      if ( KeGetCurrentIrql() )
      {
        LODWORD(v30) = -1;
        LOBYTE(v8) = 1;
        UlThreadPoolEnqueueWorkItem(0, v23 + 52, UlDestroyCapturedResponse, v8, v24, v30);
      }
      else
      {
        UxPodAttachThread(v24, (__int64)&v43);
        UlDestroyCapturedResponse(v25);
        UxPodDetachThread((__int64)&v43);
      }
    }
    Consumer = v31;
  }
  if ( v32 && ((Consumer + 0x80000000) & 0x80000000) == 0 && Consumer != -1073741766 )
  {
    v26 = *(_QWORD *)(v39 + 8);
    v27 = *(_QWORD *)(v26 + 328);
    if ( *(_BYTE *)(v27 + 1568) )
    {
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v49[2] = v27;
      v49[0] = &v57;
      v49[1] = 0;
      v50 = 0;
      LOWORD(v29[0]) = v37;
      McTemplateK0xh_UlEtwWriteEventWrapper(v26, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, v49, v41, *(_QWORD *)v29);
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
    {
      LOWORD(v29[0]) = v37;
      WPP_SF_diH(89, v23, (unsigned int)Consumer, v41, *(_QWORD *)v29);
    }
  }
  if ( Consumer != 259 )
  {
    Irp->IoStatus.Status = Consumer;
    IofCompleteRequest(Irp, 0);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(90, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
  return (unsigned int)Consumer;
}

```

## disassembly

```asm
0x1c011bcd0  mov     r11, rsp
0x1c011bcd3  mov     [r11+18h], rbx
0x1c011bcd7  mov     [r11+20h], rsi
0x1c011bcdb  push    rdi
0x1c011bcdc  push    r12
0x1c011bcde  push    r13
0x1c011bce0  push    r14
0x1c011bce2  push    r15
0x1c011bce4  sub     rsp, 360h
0x1c011bceb  mov     rax, cs:__security_cookie
0x1c011bcf2  xor     rax, rsp
0x1c011bcf5  mov     [rsp+388h+var_38], rax
0x1c011bcfd  mov     r15, rdx
0x1c011bd00  mov     r13, rcx
0x1c011bd03  mov     qword ptr [rsp+388h+var_2C8], rcx
0x1c011bd0b  xorps   xmm0, xmm0
0x1c011bd0e  xor     eax, eax
0x1c011bd10  movups  xmmword ptr [rsp+388h+var_2B8], xmm0
0x1c011bd18  movups  [rsp+388h+var_2A8], xmm0
0x1c011bd20  movups  [rsp+388h+var_298], xmm0
0x1c011bd28  mov     [r11-288h], rax
0x1c011bd2f  xor     edi, edi
0x1c011bd31  mov     [r11-2F0h], rdi
0x1c011bd38  mov     esi, edi
0x1c011bd3a  mov     [r11-2D0h], rdi
0x1c011bd41  mov     [r11-2E8h], rdi
0x1c011bd48  mov     r12b, dil
0x1c011bd4b  mov     [rsp+388h+var_308], dil
0x1c011bd53  mov     [rsp+388h+var_300], dil
0x1c011bd5b  mov     [rsp+388h+var_2FE], dil
0x1c011bd63  mov     dword ptr [rsp+388h+var_2FD+1], eax
0x1c011bd6a  mov     byte ptr [rsp+388h+var_2FD+6], al
0x1c011bd71  mov     [r11-2D8h], rdi
0x1c011bd78  mov     [r11-2E0h], rdi
0x1c011bd7f  mov     byte ptr [rsp+388h+var_2FD], dil
0x1c011bd87  xor     edx, edx; Val
0x1c011bd89  mov     r8d, 90h; Size
0x1c011bd8f  lea     rcx, [r11-278h]; void *
0x1c011bd96  call    memset
0x1c011bd9b  mov     [rsp+388h+var_2F4], di
0x1c011bda3  xorps   xmm0, xmm0
0x1c011bda6  movups  [rsp+388h+var_188], xmm0
0x1c011bdae  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c011bdb8  jz      short loc_1C011BDCF
0x1c011bdba  lea     ecx, [rdi+50h]
0x1c011bdbd  mov     r9, r15
0x1c011bdc0  mov     r8, r13
0x1c011bdc3  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c011bdca  call    WPP_SF_qq
0x1c011bdcf  lea     r8, [rsp+388h+var_2E8]
0x1c011bdd7  mov     r14d, 1
0x1c011bddd  mov     edx, r14d
0x1c011bde0  mov     rcx, [r15+30h]
0x1c011bde4  call    UlGetConsumer
0x1c011bde9  mov     ebx, eax
0x1c011bdeb  mov     [rsp+388h+var_304], eax
0x1c011bdf2  test    eax, eax
0x1c011bdf4  js      loc_1C011C590
0x1c011bdfa  lea     rax, [rsp+388h+var_2B8]
0x1c011be02  mov     qword ptr [rsp+388h+var_368], rax; int
0x1c011be07  mov     r9d, [r15+10h]
0x1c011be0b  mov     r8, [r15+20h]
0x1c011be0f  mov     dl, [r13+40h]
0x1c011be13  mov     rcx, r13
0x1c011be16  call    UlpGetSendInfo
0x1c011be1b  mov     ebx, eax
0x1c011be1d  mov     [rsp+388h+var_304], eax
0x1c011be24  test    eax, eax
0x1c011be26  js      loc_1C011C590
0x1c011be2c  lea     rax, [rsp+388h+var_2FD]
0x1c011be34  mov     [rsp+388h+var_350], rax; __int64
0x1c011be39  lea     rax, [rsp+388h+P]
0x1c011be41  mov     [rsp+388h+var_358], rax; __int64
0x1c011be46  lea     rax, [rsp+388h+var_178]
0x1c011be4e  mov     [rsp+388h+var_360], rax; P
0x1c011be53  mov     r9, qword ptr [rsp+388h+var_2A8]
0x1c011be5b  movzx   r8d, word ptr [rsp+388h+var_2B8+8]
0x1c011be64  mov     dl, [r13+40h]
0x1c011be68  mov     rcx, r13; Irp
0x1c011be6b  call    UlpGetChunkInfo
0x1c011be70  mov     ebx, eax
0x1c011be72  mov     [rsp+388h+var_304], eax
0x1c011be79  test    eax, eax
0x1c011be7b  jns     short loc_1C011BEA0
0x1c011be7d  mov     eax, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c011be83  test    al, 20h
0x1c011be85  jz      short loc_1C011BE9B
0x1c011be87  mov     ecx, 51h ; 'Q'
0x1c011be8c  mov     r8d, ebx
0x1c011be8f  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c011be96  call    WPP_SF_D
0x1c011be9b  jmp     loc_1C011C590
0x1c011bea0  lea     r9, [rsp+388h+var_278]
0x1c011bea8  lea     r8, [rsp+388h+var_2B8]
0x1c011beb0  mov     dl, [r13+40h]
0x1c011beb4  mov     rcx, r13
0x1c011beb7  call    UlpGetLogInfo
0x1c011bebc  mov     ebx, eax
0x1c011bebe  mov     [rsp+388h+var_304], eax
0x1c011bec5  test    eax, eax
0x1c011bec7  js      loc_1C011C590
0x1c011becd  mov     r12d, dword ptr [rsp+388h+var_298+8]
0x1c011bed5  mov     eax, r12d
0x1c011bed8  shr     eax, 1
0x1c011beda  not     al
0x1c011bedc  and     al, r14b
0x1c011bedf  mov     [rsp+388h+var_300], al
0x1c011bee6  jz      loc_1C011BF7F
0x1c011beec  mov     r9, qword ptr [rsp+388h+var_298]
0x1c011bef4  mov     [rsp+388h+var_2D8], r9
0x1c011befc  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1c011bf03  movdqu  [rsp+388h+var_188], xmm0
0x1c011bf0c  mov     qword ptr [rsp+388h+var_188], r9
0x1c011bf14  mov     rax, [rsp+388h+var_2E8]
0x1c011bf1c  mov     rcx, [rax+8]
0x1c011bf20  mov     rax, [rcx+148h]
0x1c011bf27  cmp     [rax+620h], dil
0x1c011bf2e  jz      short loc_1C011BF7F
0x1c011bf30  xorps   xmm0, xmm0
0x1c011bf33  movups  [rsp+388h+var_1C8], xmm0
0x1c011bf3b  movups  [rsp+388h+var_1B8], xmm0
0x1c011bf43  mov     qword ptr [rsp+388h+var_1B8], rax
0x1c011bf4b  lea     rax, [rsp+388h+var_188]
0x1c011bf53  mov     qword ptr [rsp+388h+var_1C8], rax
0x1c011bf5b  mov     qword ptr [rsp+388h+var_1C8+8], rdi
0x1c011bf63  mov     byte ptr [rsp+388h+var_1B8+8], dil
0x1c011bf6b  lea     r8, [rsp+388h+var_1C8]
0x1c011bf73  lea     rdx, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY
0x1c011bf7a  call    McTemplateK0p_UlEtwWriteEventWrapper
0x1c011bf7f  test    dword ptr cs:WPP_MAIN_CB.Queue, 8000h
0x1c011bf89  jz      short loc_1C011BFA0
0x1c011bf8b  mov     ecx, 52h ; 'R'
0x1c011bf90  mov     r9d, r12d
0x1c011bf93  mov     r8, [rsp+388h+var_2D8]
0x1c011bf9b  call    WPP_SF_iD
0x1c011bfa0  mov     rdx, [rsp+388h+var_2E8]
0x1c011bfa8  mov     rcx, qword ptr [rsp+388h+var_298]
0x1c011bfb0  call    UlGetRequestFromId
0x1c011bfb5  mov     rsi, rax
0x1c011bfb8  mov     [rsp+388h+var_2D0], rax
0x1c011bfc0  test    rax, rax
0x1c011bfc3  jnz     short loc_1C011BFFB
0x1c011bfc5  mov     ebx, 0C000023Ah
0x1c011bfca  mov     [rsp+388h+var_304], ebx
0x1c011bfd1  mov     ecx, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c011bfd7  test    cl, 20h
0x1c011bfda  jz      short loc_1C011BFEE
0x1c011bfdc  lea     ecx, [rax+53h]
0x1c011bfdf  mov     r8d, ebx
0x1c011bfe2  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c011bfe9  call    WPP_SF_D
0x1c011bfee  mov     r12b, [rsp+388h+var_308]
0x1c011bff6  jmp     loc_1C011C590
0x1c011bffb  mov     rcx, [rax+18h]
0x1c011bfff  mov     rax, [rcx+3C0h]
0x1c011c006  cmp     [rax+620h], dil
0x1c011c00d  jz      short loc_1C011C060
0x1c011c00f  xorps   xmm0, xmm0
0x1c011c012  movups  [rsp+388h+var_1A8], xmm0
0x1c011c01a  movups  [rsp+388h+var_198], xmm0
0x1c011c022  mov     qword ptr [rsp+388h+var_198], rax
0x1c011c02a  lea     rax, [rsi+48h]
0x1c011c02e  mov     qword ptr [rsp+388h+var_1A8], rax
0x1c011c036  mov     qword ptr [rsp+388h+var_1A8+8], rdi
0x1c011c03e  mov     byte ptr [rsp+388h+var_198+8], dil
0x1c011c046  mov     rax, [rcx+18h]
0x1c011c04a  mov     qword ptr [rsp+388h+var_368], rax
0x1c011c04f  mov     r9, [rsi+38h]
0x1c011c053  lea     r8, [rsp+388h+var_1A8]
0x1c011c05b  call    McTemplateK0xx_UlEtwWriteEventWrapper
0x1c011c060  test    dword ptr cs:WPP_MAIN_CB.Queue, 8000h
0x1c011c06a  jz      short loc_1C011C07D
0x1c011c06c  mov     r9, [rsi+18h]
0x1c011c070  mov     r9, [r9+18h]
0x1c011c074  mov     r8, [rsi+38h]
0x1c011c078  call    WPP_SF_ii
0x1c011c07d  mov     [rsp+388h+var_2FF], dil
0x1c011c085  cmp     [rsi+9A8h], rdi
0x1c011c08c  jnz     short loc_1C011C09E
0x1c011c08e  mov     r15b, dil
0x1c011c091  mov     byte ptr [rsp+388h+var_2FD+5], dil
0x1c011c099  jmp     loc_1C011C125
0x1c011c09e  movzx   r15d, dil
0x1c011c0a2  mov     [rsp+388h+var_2FF], r15b
0x1c011c0aa  call    cs:__imp_KeEnterCriticalRegion
0x1c011c0b1  nop     dword ptr [rax+rax+00h]
0x1c011c0b6  mov     rcx, [rsi+18h]
0x1c011c0ba  mov     ebx, 1D0h
0x1c011c0bf  add     rcx, rbx
0x1c011c0c2  xor     edx, edx
0x1c011c0c4  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c011c0cb  nop     dword ptr [rax+rax+00h]
0x1c011c0d0  mov     rax, [rsi+9C0h]
0x1c011c0d7  test    rax, rax
0x1c011c0da  jz      short loc_1C011C0F7
0x1c011c0dc  cmp     [rax+88h], edi
0x1c011c0e2  jnz     short loc_1C011C0F7
0x1c011c0e4  cmp     [rax+100h], r14d
0x1c011c0eb  cmovz   r15d, r14d
0x1c011c0ef  mov     [rsp+388h+var_2FF], r15b
0x1c011c0f7  mov     rcx, [rsi+18h]
0x1c011c0fb  add     rcx, rbx
0x1c011c0fe  xor     edx, edx
0x1c011c100  call    cs:__imp_ExReleasePushLockSharedEx
0x1c011c107  nop     dword ptr [rax+rax+00h]
0x1c011c10c  call    cs:__imp_KeLeaveCriticalRegion
0x1c011c113  nop     dword ptr [rax+rax+00h]
0x1c011c118  mov     byte ptr [rsp+388h+var_2FD+5], r15b
0x1c011c120  test    r15b, r15b
0x1c011c123  jnz     short loc_1C011C189
0x1c011c125  cmp     [rsi+890h], edi
0x1c011c12b  jnz     short loc_1C011C189
0x1c011c12d  test    r12b, 4
0x1c011c131  jnz     short loc_1C011C189
0x1c011c133  mov     rcx, [rsi+18h]
0x1c011c137  add     rcx, 348h
0x1c011c13e  call    UxTpIsFastSendPossible
0x1c011c143  test    al, al
0x1c011c145  jz      short loc_1C011C189
0x1c011c147  cmp     word ptr [rsp+388h+var_2B8+8], r14w
0x1c011c150  jnz     short loc_1C011C189
0x1c011c152  mov     r8, [rsp+388h+P]
0x1c011c15a  mov     ecx, dword ptr [rsp+388h+var_2FD+1]
0x1c011c161  cmp     [r8], edi
0x1c011c164  jnz     short loc_1C011C190
0x1c011c166  mov     eax, [r8+10h]
0x1c011c16a  sub     eax, r14d
0x1c011c16d  movzx   ecx, cl
0x1c011c170  cmp     eax, 0FFFFh
0x1c011c175  cmovbe  ecx, r14d
0x1c011c179  mov     dword ptr [rsp+388h+var_2FD+1], ecx
0x1c011c180  mov     byte ptr [rsp+388h+var_2FD+6], cl
0x1c011c187  jmp     short loc_1C011C190
0x1c011c189  mov     ecx, dword ptr [rsp+388h+var_2FD+1]
0x1c011c190  cmp     [rsp+388h+var_300], dil
0x1c011c198  jnz     short loc_1C011C19F
0x1c011c19a  test    r14b, r12b
0x1c011c19d  jz      short loc_1C011C1AB
0x1c011c19f  mov     al, r14b
0x1c011c1a2  mov     [rsp+388h+var_2FE], al
0x1c011c1a9  jmp     short loc_1C011C1B2
0x1c011c1ab  mov     al, [rsp+388h+var_2FE]
0x1c011c1b2  test    cl, cl
0x1c011c1b4  jnz     loc_1C011C268
0x1c011c1ba  lea     rcx, [rsp+388h+var_2F0]
0x1c011c1c2  mov     [rsp+388h+var_318], rcx
0x1c011c1c7  lea     rcx, [rsp+388h+var_2F4]
0x1c011c1cf  mov     [rsp+388h+var_320], rcx
0x1c011c1d4  mov     byte ptr [rsp+388h+var_328], al
0x1c011c1d8  mov     [rsp+388h+var_330], dil
0x1c011c1dd  mov     rax, [rsp+388h+var_288]
0x1c011c1e5  mov     [rsp+388h+var_338], rax
0x1c011c1ea  mov     byte ptr [rsp+388h+var_340], dil
0x1c011c1ef  mov     byte ptr [rsp+388h+var_348], dil
0x1c011c1f4  mov     dword ptr [rsp+388h+var_350], r12d
0x1c011c1f9  mov     al, [r13+40h]
0x1c011c1fd  mov     byte ptr [rsp+388h+var_358], al
0x1c011c201  mov     rax, [rsp+388h+P]
0x1c011c209  mov     [rsp+388h+var_360], rax
0x1c011c20e  movzx   eax, word ptr [rsp+388h+var_2B8+8]
0x1c011c216  mov     word ptr [rsp+388h+var_368], ax
0x1c011c21b  mov     r9, r13
0x1c011c21e  mov     r8, rsi
0x1c011c221  xor     edx, edx
0x1c011c223  mov     rcx, [rsp+388h+var_2E8]
0x1c011c22b  call    UlCaptureHttpResponse
0x1c011c230  mov     ebx, eax
0x1c011c232  mov     [rsp+388h+var_304], eax
0x1c011c239  test    eax, eax
0x1c011c23b  jns     short loc_1C011C268
0x1c011c23d  mov     eax, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c011c243  test    al, 20h
0x1c011c245  jz      short loc_1C011C25B
0x1c011c247  mov     ecx, 55h ; 'U'
0x1c011c24c  mov     r8d, ebx
0x1c011c24f  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c011c256  call    WPP_SF_D
0x1c011c25b  mov     r12b, [rsp+388h+var_308]
0x1c011c263  jmp     loc_1C011C590
0x1c011c268  cmp     [rsi+890h], r14d
0x1c011c26f  jnz     short loc_1C011C295
0x1c011c271  mov     ebx, edi
0x1c011c273  mov     [rsp+388h+var_304], ebx
0x1c011c27a  mov     rax, [rsp+388h+var_2F0]
0x1c011c282  mov     rcx, [rax+148h]
0x1c011c289  mov     [r13+38h], rcx
0x1c011c28d  mov     r12b, bl
0x1c011c290  jmp     loc_1C011C590
0x1c011c295  mov     edx, r12d
0x1c011c298  mov     rcx, rsi
0x1c011c29b  call    UlCheckSendEntityBodyFlags
0x1c011c2a0  mov     ebx, eax
0x1c011c2a2  mov     [rsp+388h+var_304], eax
0x1c011c2a9  test    eax, eax
0x1c011c2ab  jns     short loc_1C011C2D8
0x1c011c2ad  mov     eax, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c011c2b3  test    al, 20h
0x1c011c2b5  jz      short loc_1C011C2CB
0x1c011c2b7  mov     ecx, 56h ; 'V'
0x1c011c2bc  mov     r8d, ebx
  ... truncated ...
```
