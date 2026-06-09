# FveFilterReadWrite

- ea: `0x1400ebc00`
- end: `0x1400ec573`
- name: `FveFilterReadWrite`
- size: `2419`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x140029c84`

## callees

- `0x140003620`
- `0x140008130`
- `0x140008348`
- `0x1400084e8`
- `0x140008e80`
- `0x140008f04`
- `0x140008fe0`
- `0x14000b998`
- `0x14000fef0`
- `0x14002a3a0`
- `0x14002d140`
- `0x1400bc8fc`
- `0x1400bcc54`
- `0x1400be464`
- `0x1400bf48c`
- `0x1400d8588`
- `0x1400da830`
- `0x1400db250`
- `0x1400db940`
- `0x1400dff88`
- `0x1400e2608`
- `0x1400eb300`
- `0x1400ebc00`
- `0x1400ec57c`
- `0x1400ecce0`
- `0x1400ed8f8`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x1400ec532`
- `ntoskrnl!KeLowerIrql` at `0x1400ec532`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ebca1`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ebca1`
- `ntoskrnl!IoGetPagingIoPriority` at `0x1400ebd28`
- `ntoskrnl!IoGetPagingIoPriority` at `0x1400ebd28`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x1400ebcf1`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x1400ebcf1`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400ebd0c`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400ebd0c`
- `ntoskrnl!KfRaiseIrql` at `0x1400ec502`
- `ntoskrnl!KfRaiseIrql` at `0x1400ec502`
- `ntoskrnl!KeBugCheckEx` at `0x1400ec256`
- `ntoskrnl!KeBugCheckEx` at `0x1400ec256`

## string_xrefs

- `0x1400ebd53`: `WRITE`
- `0x1400ec4cf`: `WRITE`

## pseudocode

```c
__int64 __fastcall FveFilterReadWrite(__int64 a1, IRP *a2, char a3, unsigned __int64 a4, ULONG a5)
{
  unsigned int v8; // ebx
  int v9; // r14d
  char IsIrpWithEfsOffload; // al
  ULONG v12; // r12d
  PETHREAD Thread; // rcx
  char PriorityThread; // bp
  char EffectivePriorityThread; // r14
  struct _KTHREAD *v16; // rcx
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  const char *v18; // rdx
  unsigned __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // r8
  bool v22; // zf
  __int64 *v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r8
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  char v31; // r15
  __int64 v32; // rdx
  char ShouldTryInlineOffload; // r12
  char v34; // dl
  char v35; // r14
  int v37; // r8d
  __int64 v38; // rdx
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rax
  PDEVICE_OBJECT v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rbx
  KIRQL v45; // bp
  PVOID v46; // r14
  ULONG SortKey; // r15d
  _QWORD *v48; // rax
  __int64 v49; // rax
  int v50; // r8d
  char v51; // cl
  char v52; // r14
  const char *v53; // rax
  char PagingIoPriority; // [rsp+60h] [rbp-68h]
  char IsPagingRequest; // [rsp+70h] [rbp-58h]
  char v56; // [rsp+71h] [rbp-57h]
  IO_PRIORITY_HINT IoPriorityHint; // [rsp+74h] [rbp-54h]
  struct _LIST_ENTRY *Flink; // [rsp+88h] [rbp-40h]
  char v59; // [rsp+D0h] [rbp+8h]
  char v60; // [rsp+D8h] [rbp+10h] BYREF
  char v61; // [rsp+E0h] [rbp+18h]

  v61 = a3;
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v8 = BYTE1(Flink);
  v9 = 0;
  v60 = 0;
  IsIrpWithEfsOffload = FveIsIrpWithEfsOffload(a2, 0, 0);
  v12 = a5;
  v59 = IsIrpWithEfsOffload;
  IsPagingRequest = FveIsPagingRequest(a1, a2, a4, a5);
  if ( !*(_QWORD *)(a1 + 5144) || *(_DWORD *)(a1 + 836) != 3 || (v56 = 1, (*(_DWORD *)(a1 + 808) & 1) == 0) )
    v56 = 0;
  IoPriorityHint = IoGetIoPriorityHint(a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    Thread = a2->Tail.Overlay.Thread;
    PriorityThread = -1;
    if ( Thread )
      EffectivePriorityThread = KeQueryEffectivePriorityThread(Thread);
    else
      EffectivePriorityThread = -1;
    v16 = a2->Tail.Overlay.Thread;
    if ( v16 )
      PriorityThread = KeQueryPriorityThread(v16);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    PagingIoPriority = IoGetPagingIoPriority(a2);
    v18 = "WRITE";
    if ( !a3 )
      v18 = "READ";
    WPP_SF_qsqiiDdddd(
      (_DWORD)AttachedDevice,
      (_DWORD)v18,
      v12 + a4,
      a1,
      (__int64)v18,
      (char)a2,
      a4,
      v12 + a4,
      v12,
      PriorityThread,
      EffectivePriorityThread,
      IoPriorityHint,
      PagingIoPriority);
    v8 = BYTE1(Flink);
    v9 = 0;
  }
  v19 = *(unsigned int *)(a1 + 1308);
  if ( (((_DWORD)v19 - 1) & (unsigned int)v19) != 0 || !(_DWORD)v19 )
    v20 = v12 % (unsigned int)v19 == 0;
  else
    v20 = (((_DWORD)v19 - 1) & v12) == 0;
  if ( v20 )
  {
    v21 = *(unsigned int *)(a1 + 1308);
    if ( ((v19 - 1) & v19) != 0 || !(_DWORD)v19 )
      v22 = a4 % v19 == 0;
    else
      v22 = ((v19 - 1) & a4) == 0;
    if ( v22 )
    {
      LOBYTE(v21) = a3;
      FveCollectIoStats(a1, a2, v21);
      v23 = FVE_PERF_WRITE_REQUEST_START;
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      if ( !a3 )
        v23 = (__int64 *)&FVE_PERF_READ_REQUEST_START;
      FvePerfTraceDevPtr(a1, v23, a2);
      v26 = *(_QWORD *)(a1 + 8);
      if ( !*(_BYTE *)(v26 + 104) || *(_QWORD *)(v26 + 112) )
      {
        if ( a3 )
          _InterlockedIncrement64((volatile signed __int64 *)(a1 + 664));
        else
          _InterlockedIncrement64((volatile signed __int64 *)(a1 + 648));
      }
      if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v25, v24) )
      {
        if ( (*(_DWORD *)(a1 + 808) & 0x19) != 0 )
        {
          v27 = *(_QWORD *)(a1 + 4752);
          if ( v27 )
          {
            if ( *(_DWORD *)(v27 + 88) && *(_QWORD *)(a1 + 1008) )
              goto LABEL_103;
          }
        }
      }
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9928LL) & 4) == 0 )
      {
        if ( (unsigned __int8)FveShouldTryInlineIceIrp(a1, (_DWORD)a2, a4, v12, a3, 0) )
        {
          LOBYTE(v28) = a3;
          if ( (unsigned __int8)FveTryIssueIceIrp(a1, a2, v28, a4, v12) )
          {
            v29 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            {
              return 259;
            }
            v30 = 68;
LABEL_86:
            WPP_SF_(v29->AttachedDevice, v30, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids);
            return 259;
          }
        }
      }
      if ( !(unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        v31 = 0;
        goto LABEL_81;
      }
      ShouldTryInlineOffload = FveHwAccelShouldTryInlineOffload(a1, a2, a4, v12);
      if ( ShouldTryInlineOffload )
      {
        v34 = v59;
        if ( v59 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
LABEL_53:
            if ( v56
              && (!ShouldTryInlineOffload || v9 == -1073741670 || v9 == -1073741801 || v9 == -2147483631)
              && !IsPagingRequest
              && !v34 )
            {
              v31 = 1;
            }
            else
            {
              v31 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_ddDdd(WPP_GLOBAL_Control->AttachedDevice);
              }
            }
            v12 = a5;
LABEL_81:
            v35 = v61;
            if ( FveTryFastPathIo(a1, a2, v61, a4, v12) )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              {
                return 259;
              }
              v30 = 74;
              goto LABEL_86;
            }
            if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
            {
              if ( v35
                && !(unsigned __int8)FveWriteUsingWorkerQueues2(
                                       a1,
                                       a2->Tail.Overlay.Thread,
                                       a4,
                                       v12,
                                       (char)Flink,
                                       IoPriorityHint) )
              {
                if ( FveTryInlineWriteEncrypt(a1, a2, a4, v12, &v60) )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  {
                    v40 = 75;
LABEL_96:
                    WPP_SF_(v39->AttachedDevice, v40, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids);
                    goto LABEL_97;
                  }
                  goto LABEL_97;
                }
                v42 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                {
                  v43 = 76;
LABEL_119:
                  WPP_SF_(v42->AttachedDevice, v43, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids);
                }
              }
            }
            else if ( v35
                   && !(unsigned __int8)FveWriteUsingWorkerQueues(
                                          a1,
                                          a2->Tail.Overlay.Thread,
                                          a4,
                                          v12,
                                          (char)Flink,
                                          IoPriorityHint) )
            {
              if ( FveTryInlineWriteEncrypt(a1, a2, a4, v12, &v60) )
              {
                v39 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                {
                  v40 = 77;
                  goto LABEL_96;
                }
LABEL_97:
                if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                      v39,
                                      v38) )
                  return 259;
                v41 = *(_QWORD *)(a1 + 4752);
                if ( !v41
                  || !*(_DWORD *)(v41 + 88)
                  || (*(_DWORD *)(a1 + 808) & 0x19) == 0
                  || !*(_QWORD *)(a1 + 1008) && v60 )
                {
                  return 259;
                }
LABEL_103:
                KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
              }
              v42 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v43 = 78;
                goto LABEL_119;
              }
            }
            LOBYTE(v37) = v35;
            v44 = AcquireRequestResources(a1, (_DWORD)a2, v37, a4, v12, v31);
            if ( v44 )
            {
              v45 = 0;
              v46 = 0;
              SortKey = 0;
              if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
              {
                v48 = *(_QWORD **)(a1 + 736);
                if ( v48 )
                {
                  if ( *v48 )
                  {
                    v46 = a2->Tail.Overlay.DriverContext[3];
                    SortKey = a2->Tail.Overlay.DeviceQueueEntry.SortKey;
                    a2->Tail.Overlay.DriverContext[3] = 0;
                    a2->Tail.Overlay.DriverContext[2] = 0;
                  }
                }
              }
              *(_QWORD *)v44 = a2;
              *(_QWORD *)(v44 + 8) = MEMORY[0xFFFFF78000000008];
              *(_QWORD *)(v44 + 16) = 0;
              *(_QWORD *)(v44 + 24) = 0;
              *(_QWORD *)(v44 + 32) = 0;
              *(_QWORD *)(v44 + 40) = 0;
              if ( *(_QWORD *)(a1 + 4752) )
                v49 = 0;
              else
                v49 = FveTestResolveRwStorageRequest(a1, a2, v46);
              *(_QWORD *)(v44 + 192) = v49;
              *(_BYTE *)(v44 + 274) = v61;
              *(_QWORD *)(v44 + 48) = a1;
              *(_QWORD *)(v44 + 64) = a4;
              *(_DWORD *)(v44 + 72) = v12;
              if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
                v51 = IsPagingRequest;
              else
                v51 = FveIsPagingRequest(a1, a2, a4, v12);
              *(_BYTE *)(v44 + 273) = v51;
              *(_DWORD *)(v44 + 76) = IoPriorityHint;
              *(_DWORD *)(v44 + 84) = BYTE1(Flink);
              *(_BYTE *)(v44 + 80) = (_BYTE)Flink;
              if ( *(_BYTE *)(a1 + 1477) )
                *(_DWORD *)(v44 + 136) = (unsigned __int8)HIBYTE(LODWORD(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
              *(_QWORD *)(v44 + 56) = v46;
              *(_DWORD *)(v44 + 88) = SortKey;
              if ( v51 )
              {
                v52 = v61;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v53 = "WRITE";
                  if ( !v61 )
                    v53 = "READ";
                  WPP_SF_qsq(WPP_GLOBAL_Control->AttachedDevice, 79, v50, a1, (__int64)v53, (char)a2);
                }
              }
              else
              {
                v52 = v61;
              }
              a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)v44;
              if ( !(_BYTE)Flink )
                v45 = KfRaiseIrql(1u);
              if ( v52 )
                ProcessResourcedWriteRequest(v44);
              else
                ProcessResourcedReadRequest(v44);
              if ( !(_BYTE)Flink )
                KeLowerIrql(v45);
            }
            else
            {
              PutIrpOnResourceWaitQueue(a1, a2);
            }
            return 259;
          }
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids);
LABEL_52:
          v34 = v59;
          goto LABEL_53;
        }
        LOBYTE(v32) = a3;
        v9 = FveHwAccelTryInlineOffload(a1, v32, a2, a4, a5);
        if ( v9 >= 0 )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            return 259;
          }
          v30 = 71;
          goto LABEL_86;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              72,
              WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids,
              (unsigned int)v9);
          goto LABEL_52;
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids, 0);
        goto LABEL_52;
      }
      v34 = v59;
      goto LABEL_53;
    }
  }
  return FveFailRundownReadWriteIrp(a1, a2, 3221225485LL, v8);
}

```

## disassembly

```asm
0x1400ebc00  mov     r11, rsp
0x1400ebc03  mov     [r11+20h], rbx
0x1400ebc07  mov     [r11+18h], r8b
0x1400ebc0b  push    rbp
0x1400ebc0c  push    rsi
0x1400ebc0d  push    rdi
0x1400ebc0e  push    r12
0x1400ebc10  push    r13
0x1400ebc12  push    r14
0x1400ebc14  push    r15
0x1400ebc16  sub     rsp, 90h
0x1400ebc1d  mov     rax, [rdx+78h]
0x1400ebc21  mov     rsi, rdx
0x1400ebc24  mov     [rsp+0C8h+var_40], rax
0x1400ebc2c  mov     r15b, r8b
0x1400ebc2f  sar     rax, 8
0x1400ebc33  mov     rdi, rcx
0x1400ebc36  movzx   ebx, al
0x1400ebc39  xor     r14d, r14d
0x1400ebc3c  xor     r8d, r8d
0x1400ebc3f  mov     [rsp+0C8h+var_50], ebx
0x1400ebc43  xor     edx, edx
0x1400ebc45  mov     [r11+10h], r14b
0x1400ebc49  mov     rcx, rsi
0x1400ebc4c  mov     r13, r9
0x1400ebc4f  call    FveIsIrpWithEfsOffload
0x1400ebc54  mov     r12d, [rsp+0C8h+arg_20]
0x1400ebc5c  mov     r8, r13
0x1400ebc5f  mov     r9d, r12d
0x1400ebc62  mov     [rsp+0C8h+arg_0], al
0x1400ebc69  mov     rdx, rsi
0x1400ebc6c  mov     rcx, rdi
0x1400ebc6f  call    FveIsPagingRequest
0x1400ebc74  mov     [rsp+0C8h+var_58], al
0x1400ebc78  cmp     [rdi+1418h], r14
0x1400ebc7f  jz      short loc_1400EBC99
0x1400ebc81  cmp     dword ptr [rdi+344h], 3
0x1400ebc88  jnz     short loc_1400EBC99
0x1400ebc8a  mov     eax, [rdi+328h]
0x1400ebc90  mov     [rsp+0C8h+var_57], 1
0x1400ebc95  test    al, 1
0x1400ebc97  jnz     short loc_1400EBC9E
0x1400ebc99  mov     [rsp+0C8h+var_57], r14b
0x1400ebc9e  mov     rcx, rsi; Irp
0x1400ebca1  call    cs:__imp_IoGetIoPriorityHint
0x1400ebca8  nop     dword ptr [rax+rax+00h]
0x1400ebcad  mov     [rsp+0C8h+var_54], eax
0x1400ebcb1  mov     rdx, cs:WPP_GLOBAL_Control
0x1400ebcb8  lea     rbp, WPP_GLOBAL_Control
0x1400ebcbf  cmp     rdx, rbp
0x1400ebcc2  jz      loc_1400EBD94
0x1400ebcc8  mov     ecx, [rdx+2Ch]
0x1400ebccb  test    cl, cl
0x1400ebccd  jns     loc_1400EBD94
0x1400ebcd3  cmp     byte ptr [rdx+29h], 4
0x1400ebcd7  jb      loc_1400EBD94
0x1400ebcdd  mov     rcx, [rsi+98h]
0x1400ebce4  or      ebp, 0FFFFFFFFh
0x1400ebce7  test    rcx, rcx
0x1400ebcea  jnz     short loc_1400EBCF1
0x1400ebcec  mov     r14d, ebp
0x1400ebcef  jmp     short loc_1400EBD00
0x1400ebcf1  call    cs:__imp_KeQueryEffectivePriorityThread
0x1400ebcf8  nop     dword ptr [rax+rax+00h]
0x1400ebcfd  mov     r14d, eax
0x1400ebd00  mov     rcx, [rsi+98h]; Thread
0x1400ebd07  test    rcx, rcx
0x1400ebd0a  jz      short loc_1400EBD1A
0x1400ebd0c  call    cs:__imp_KeQueryPriorityThread
0x1400ebd13  nop     dword ptr [rax+rax+00h]
0x1400ebd18  mov     ebp, eax
0x1400ebd1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ebd21  mov     rbx, [rcx+18h]
0x1400ebd25  mov     rcx, rsi; Irp
0x1400ebd28  call    cs:__imp_IoGetPagingIoPriority
0x1400ebd2f  nop     dword ptr [rax+rax+00h]
0x1400ebd34  mov     dword ptr [rsp+0C8h+var_68], eax
0x1400ebd38  lea     r8, [r12+r13]
0x1400ebd3c  mov     eax, [rsp+0C8h+var_54]
0x1400ebd40  test    r15b, r15b
0x1400ebd43  mov     [rsp+0C8h+var_70], eax
0x1400ebd47  lea     rcx, aRead_1; "READ"
0x1400ebd4e  mov     [rsp+0C8h+var_78], r14d
0x1400ebd53  lea     rdx, aWrite; "WRITE"
0x1400ebd5a  mov     [rsp+0C8h+var_80], ebp
0x1400ebd5e  cmovz   rdx, rcx
0x1400ebd62  mov     [rsp+0C8h+var_88], r12d
0x1400ebd67  mov     r9, rdi
0x1400ebd6a  mov     [rsp+0C8h+var_90], r8
0x1400ebd6f  mov     rcx, rbx
0x1400ebd72  mov     [rsp+0C8h+var_98], r13
0x1400ebd77  mov     [rsp+0C8h+var_A0], rsi
0x1400ebd7c  mov     [rsp+0C8h+BugCheckParameter4], rdx
0x1400ebd81  call    WPP_SF_qsqiiDdddd
0x1400ebd86  mov     ebx, [rsp+0C8h+var_50]
0x1400ebd8a  lea     rbp, WPP_GLOBAL_Control
0x1400ebd91  xor     r14d, r14d
0x1400ebd94  mov     ecx, [rdi+51Ch]
0x1400ebd9a  lea     eax, [rcx-1]
0x1400ebd9d  test    ecx, eax
0x1400ebd9f  jnz     short loc_1400EBDAA
0x1400ebda1  test    ecx, ecx
0x1400ebda3  jz      short loc_1400EBDAA
0x1400ebda5  test    r12d, eax
0x1400ebda8  jmp     short loc_1400EBDB3
0x1400ebdaa  xor     edx, edx
0x1400ebdac  mov     eax, r12d
0x1400ebdaf  div     ecx
0x1400ebdb1  test    edx, edx
0x1400ebdb3  jnz     loc_1400EC543
0x1400ebdb9  lea     rax, [rcx-1]
0x1400ebdbd  mov     r8, rcx
0x1400ebdc0  test    rcx, rax
0x1400ebdc3  jnz     short loc_1400EBDCE
0x1400ebdc5  test    ecx, ecx
0x1400ebdc7  jz      short loc_1400EBDCE
0x1400ebdc9  test    r13, rax
0x1400ebdcc  jmp     short loc_1400EBDD9
0x1400ebdce  xor     edx, edx
0x1400ebdd0  mov     rax, r13
0x1400ebdd3  div     r8
0x1400ebdd6  test    rdx, rdx
0x1400ebdd9  jnz     loc_1400EC543
0x1400ebddf  mov     r8b, r15b
0x1400ebde2  mov     rdx, rsi
0x1400ebde5  mov     rcx, rdi
0x1400ebde8  call    FveCollectIoStats
0x1400ebded  mov     rax, [rsi+0B8h]
0x1400ebdf4  lea     rdx, FVE_PERF_WRITE_REQUEST_START
0x1400ebdfb  mov     r8, rsi
0x1400ebdfe  mov     rcx, rdi
0x1400ebe01  or      byte ptr [rax+3], 1
0x1400ebe05  lea     rax, FVE_PERF_READ_REQUEST_START
0x1400ebe0c  test    r15b, r15b
0x1400ebe0f  cmovz   rdx, rax
0x1400ebe13  call    FvePerfTraceDevPtr
0x1400ebe18  mov     rax, [rdi+8]
0x1400ebe1c  cmp     [rax+68h], r14b
0x1400ebe20  jz      short loc_1400EBE2B
0x1400ebe22  mov     rax, [rax+70h]
0x1400ebe26  test    rax, rax
0x1400ebe29  jz      short loc_1400EBE42
0x1400ebe2b  test    r15b, r15b
0x1400ebe2e  jz      short loc_1400EBE3A
0x1400ebe30  lock inc qword ptr [rdi+298h]
0x1400ebe38  jmp     short loc_1400EBE42
0x1400ebe3a  lock inc qword ptr [rdi+288h]
0x1400ebe42  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ebe47  test    eax, eax
0x1400ebe49  jz      short loc_1400EBE74
0x1400ebe4b  mov     eax, [rdi+328h]
0x1400ebe51  test    al, 19h
0x1400ebe53  jz      short loc_1400EBE74
0x1400ebe55  mov     rax, [rdi+1290h]
0x1400ebe5c  test    rax, rax
0x1400ebe5f  jz      short loc_1400EBE74
0x1400ebe61  cmp     [rax+58h], r14d
0x1400ebe65  jz      short loc_1400EBE74
0x1400ebe67  cmp     [rdi+3F0h], r14
0x1400ebe6e  jnz     loc_1400EC242
0x1400ebe74  mov     rax, [rdi+8]
0x1400ebe78  mov     ecx, [rax+26C8h]
0x1400ebe7e  test    cl, 4
0x1400ebe81  jnz     short loc_1400EBEEC
0x1400ebe83  mov     byte ptr [rsp+0C8h+var_A0], r14b
0x1400ebe88  mov     r9d, r12d
0x1400ebe8b  mov     r8, r13
0x1400ebe8e  mov     byte ptr [rsp+0C8h+BugCheckParameter4], r15b
0x1400ebe93  mov     rdx, rsi
0x1400ebe96  mov     rcx, rdi
0x1400ebe99  call    FveShouldTryInlineIceIrp
0x1400ebe9e  test    al, al
0x1400ebea0  jz      short loc_1400EBEEC
0x1400ebea2  mov     r9, r13
0x1400ebea5  mov     dword ptr [rsp+0C8h+BugCheckParameter4], r12d
0x1400ebeaa  mov     r8b, r15b
0x1400ebead  mov     rdx, rsi
0x1400ebeb0  mov     rcx, rdi
0x1400ebeb3  call    FveTryIssueIceIrp
0x1400ebeb8  test    al, al
0x1400ebeba  jz      short loc_1400EBEEC
0x1400ebebc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ebec3  cmp     rcx, rbp
0x1400ebec6  jz      loc_1400EC14C
0x1400ebecc  mov     eax, [rcx+2Ch]
0x1400ebecf  test    al, al
0x1400ebed1  jns     loc_1400EC14C
0x1400ebed7  mov     bl, 5
0x1400ebed9  cmp     [rcx+29h], bl
0x1400ebedc  jb      loc_1400EC14C
0x1400ebee2  mov     edx, 44h ; 'D'
0x1400ebee7  jmp     loc_1400EC058
0x1400ebeec  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400ebef1  lea     rbp, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids
0x1400ebef8  mov     bl, 5
0x1400ebefa  test    eax, eax
0x1400ebefc  jnz     short loc_1400EBF06
0x1400ebefe  mov     r15b, r14b
0x1400ebf01  jmp     loc_1400EC0FA
0x1400ebf06  mov     r9d, r12d
0x1400ebf09  mov     r8, r13
0x1400ebf0c  mov     rdx, rsi
0x1400ebf0f  mov     rcx, rdi
0x1400ebf12  call    FveHwAccelShouldTryInlineOffload
0x1400ebf17  movzx   r12d, al
0x1400ebf1b  test    al, al
0x1400ebf1d  jnz     loc_1400EBFC1
0x1400ebf23  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ebf2a  lea     rax, WPP_GLOBAL_Control
0x1400ebf31  cmp     rcx, rax
0x1400ebf34  jz      loc_1400EC0A4
0x1400ebf3a  mov     edx, [rcx+2Ch]
0x1400ebf3d  test    dl, dl
0x1400ebf3f  jns     loc_1400EC0A4
0x1400ebf45  cmp     [rcx+29h], bl
0x1400ebf48  jb      loc_1400EC0A4
0x1400ebf4e  mov     rcx, [rcx+18h]
0x1400ebf52  mov     edx, 45h ; 'E'
0x1400ebf57  xor     r9d, r9d
0x1400ebf5a  mov     r8, rbp
0x1400ebf5d  call    WPP_SF_d
0x1400ebf62  mov     dl, [rsp+0C8h+arg_0]
0x1400ebf69  lea     rax, WPP_GLOBAL_Control
0x1400ebf70  movzx   r9d, [rsp+0C8h+var_57]
0x1400ebf76  test    r9b, r9b
0x1400ebf79  jz      loc_1400EC0B0
0x1400ebf7f  test    r12b, r12b
0x1400ebf82  jz      short loc_1400EBFA3
0x1400ebf84  cmp     r14d, 0C000009Ah
0x1400ebf8b  jz      short loc_1400EBFA3
0x1400ebf8d  cmp     r14d, 0C0000017h
0x1400ebf94  jz      short loc_1400EBFA3
0x1400ebf96  cmp     r14d, 80000011h
0x1400ebf9d  jnz     loc_1400EC0B0
0x1400ebfa3  mov     r8b, [rsp+0C8h+var_58]
0x1400ebfa8  test    r8b, r8b
0x1400ebfab  jnz     loc_1400EC0B5
0x1400ebfb1  test    dl, dl
0x1400ebfb3  jnz     loc_1400EC0B5
0x1400ebfb9  mov     r15b, 1
0x1400ebfbc  jmp     loc_1400EC0F2
0x1400ebfc1  mov     dl, [rsp+0C8h+arg_0]
0x1400ebfc8  test    dl, dl
0x1400ebfca  jz      short loc_1400EC005
0x1400ebfcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ebfd3  lea     rax, WPP_GLOBAL_Control
0x1400ebfda  cmp     rcx, rax
0x1400ebfdd  jz      short loc_1400EBF70
0x1400ebfdf  mov     eax, [rcx+2Ch]
0x1400ebfe2  test    al, al
0x1400ebfe4  jns     short loc_1400EBF69
0x1400ebfe6  cmp     [rcx+29h], bl
0x1400ebfe9  jb      loc_1400EBF69
0x1400ebfef  mov     rcx, [rcx+18h]
0x1400ebff3  mov     edx, 46h ; 'F'
0x1400ebff8  mov     r8, rbp
0x1400ebffb  call    WPP_SF_
0x1400ec000  jmp     loc_1400EBF62
0x1400ec005  mov     eax, [rsp+0C8h+arg_20]
0x1400ec00c  mov     r9, r13
0x1400ec00f  mov     r8, rsi
0x1400ec012  mov     dword ptr [rsp+0C8h+BugCheckParameter4], eax
0x1400ec016  mov     dl, r15b
0x1400ec019  mov     rcx, rdi
0x1400ec01c  call    FveHwAccelTryInlineOffload
0x1400ec021  mov     r14d, eax
0x1400ec024  test    eax, eax
0x1400ec026  js      short loc_1400EC064
0x1400ec028  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec02f  lea     rax, WPP_GLOBAL_Control
0x1400ec036  cmp     rcx, rax
0x1400ec039  jz      loc_1400EC14C
0x1400ec03f  mov     eax, [rcx+2Ch]
0x1400ec042  test    al, al
0x1400ec044  jns     loc_1400EC14C
0x1400ec04a  cmp     [rcx+29h], bl
0x1400ec04d  jb      loc_1400EC14C
0x1400ec053  mov     edx, 47h ; 'G'
0x1400ec058  lea     r8, WPP_4db624899e243eeb5b055379b0b9ae22_Traceguids
0x1400ec05f  jmp     loc_1400EC143
0x1400ec064  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec06b  lea     rax, WPP_GLOBAL_Control
0x1400ec072  cmp     rcx, rax
0x1400ec075  jz      short loc_1400EC0A4
0x1400ec077  mov     eax, [rcx+2Ch]
0x1400ec07a  test    al, al
0x1400ec07c  jns     loc_1400EBF62
0x1400ec082  cmp     [rcx+29h], bl
0x1400ec085  jb      loc_1400EBF62
0x1400ec08b  mov     rcx, [rcx+18h]
0x1400ec08f  mov     edx, 48h ; 'H'
0x1400ec094  mov     r9d, r14d
0x1400ec097  mov     r8, rbp
0x1400ec09a  call    WPP_SF_d
0x1400ec09f  jmp     loc_1400EBF62
0x1400ec0a4  mov     dl, [rsp+0C8h+arg_0]
0x1400ec0ab  jmp     loc_1400EBF70
0x1400ec0b0  mov     r8b, [rsp+0C8h+var_58]
0x1400ec0b5  xor     r15b, r15b
0x1400ec0b8  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
