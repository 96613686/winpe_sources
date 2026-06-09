# AllocateTapiProvider

- ea: `0x1400062c0`
- end: `0x140006b5f`
- name: `AllocateTapiProvider`
- size: `2207`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002fd0`

## callees

- `0x140001b54`
- `0x140001bc8`
- `0x140001c0c`
- `0x140004554`
- `0x140005ca4`
- `0x1400062c0`
- `0x140006c1c`
- `0x140006cac`
- `0x140007040`
- `0x140007fc0`
- `0x1400081c0`
- `0x1400084c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000659f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400067ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400069e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ade`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006b2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000659f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400067ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400069e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ade`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006b2e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000642e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000642e`
- `ntoskrnl!ExAllocatePool2` at `0x14000640f`
- `ntoskrnl!ExAllocatePool2` at `0x14000686b`
- `ntoskrnl!ExAllocatePool2` at `0x14000640f`
- `ntoskrnl!ExAllocatePool2` at `0x14000686b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400068bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400068bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006797`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400069a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006a16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006aa6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006af9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006b47`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006797`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400069a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006a16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006aa6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006af9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006b47`
- `NDIS!NdisAcquireRWLockWrite` at `0x140006839`
- `NDIS!NdisAcquireRWLockWrite` at `0x140006839`
- `NDIS!NdisReleaseRWLock` at `0x14000688b`
- `NDIS!NdisReleaseRWLock` at `0x14000697f`
- `NDIS!NdisReleaseRWLock` at `0x140006b1f`
- `NDIS!NdisReleaseRWLock` at `0x14000688b`
- `NDIS!NdisReleaseRWLock` at `0x14000697f`
- `NDIS!NdisReleaseRWLock` at `0x140006b1f`
- `NDIS!NdisAcquireRWLockRead` at `0x140006a31`
- `NDIS!NdisAcquireRWLockRead` at `0x140006a31`
- `NDIS!NdisInitializeEvent` at `0x14000636b`
- `NDIS!NdisInitializeEvent` at `0x14000636b`
- `NDIS!NdisCoOidRequest` at `0x1400063a8`
- `NDIS!NdisCoOidRequest` at `0x1400063a8`
- `NDIS!NdisWaitEvent` at `0x1400063c4`
- `NDIS!NdisWaitEvent` at `0x1400063c4`

## pseudocode

```c
struct _SINGLE_LIST_ENTRY *__fastcall AllocateTapiProvider(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // r15
  char v4; // r13
  void *v5; // rdx
  void *v6; // rcx
  NDIS_STATUS v7; // eax
  struct _SINGLE_LIST_ENTRY *v8; // r12
  int v9; // eax
  __int64 Pool2; // rax
  struct _SINGLE_LIST_ENTRY *v11; // rbx
  unsigned int v12; // edi
  struct _SINGLE_LIST_ENTRY *TapiLine; // rax
  struct _SINGLE_LIST_ENTRY *Next; // rcx
  KIRQL v15; // al
  ULONG *v16; // r13
  char v18; // r8
  char v19; // r9
  char v20; // al
  char v21; // r10
  char v22; // r11
  char v23; // bl
  char v24; // di
  char v25; // si
  __int16 v26; // r14
  struct _SINGLE_LIST_ENTRY *SecurityDescriptor; // rax
  struct _SINGLE_LIST_ENTRY *v28; // rdi
  struct _SINGLE_LIST_ENTRY *v29; // rbx
  struct _SINGLE_LIST_ENTRY *v30; // rax
  struct _SINGLE_LIST_ENTRY *v31; // rcx
  unsigned int v32; // ecx
  struct _SINGLE_LIST_ENTRY *v33; // rax
  struct _SINGLE_LIST_ENTRY *v34; // rsi
  __int64 TargetInfoAsUlong; // rdx
  unsigned int v36; // esi
  __int64 v37; // r8
  KIRQL v38; // dl
  unsigned int i; // edi
  struct _SINGLE_LIST_ENTRY *v40; // rbx
  KIRQL v41; // al
  char OidRequest; // [rsp+20h] [rbp-E0h]
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  _QWORD v46[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _SINGLE_LIST_ENTRY *Src; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 Next_low; // [rsp+B8h] [rbp-48h]
  __int64 v52; // [rsp+C0h] [rbp-40h]
  _BYTE v53[280]; // [rsp+D0h] [rbp-30h] BYREF

  v45 = a2;
  v2 = a2;
  v44 = a1;
  v3 = a1;
  memset(v46, 0, 12);
  v4 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  memset(v53, 0, sizeof(v53));
  *(_DWORD *)v53 = 15729046;
  memset(v46, 0, 12);
  *(_QWORD *)&v53[8] = 0;
  NdisInitializeEvent((PNDIS_EVENT)&v53[248]);
  v5 = *(void **)(v2 + 24);
  v6 = *(void **)(v3 + 32);
  *(_QWORD *)&v53[40] = v46;
  *(_DWORD *)&v53[4] = 0;
  *(_DWORD *)&v53[32] = -33550335;
  *(_DWORD *)&v53[48] = 12;
  v7 = NdisCoOidRequest(v6, v5, 0, 0, (PNDIS_OID_REQUEST)v53);
  if ( v7 == 259 )
  {
    NdisWaitEvent((PNDIS_EVENT)&v53[248], 0);
    v7 = *(_DWORD *)&v53[272];
  }
  if ( v7 )
  {
    v8 = 0;
    if ( v7 != -1073741637 )
      goto LABEL_20;
    v9 = 1;
    LODWORD(v46[0]) = 196608;
    *(_QWORD *)((char *)v46 + 4) = 1;
    v4 = 0;
  }
  else
  {
    v9 = HIDWORD(v46[0]);
  }
  Pool2 = ExAllocatePool2(64, (unsigned int)(8 * v9 + 160), 3758160);
  v8 = (struct _SINGLE_LIST_ENTRY *)Pool2;
  if ( !Pool2 )
    goto LABEL_20;
  KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 136));
  LODWORD(v8[2].Next) = 1;
  v8[3].Next = (struct _SINGLE_LIST_ENTRY *)v3;
  v8[4].Next = (struct _SINGLE_LIST_ENTRY *)v2;
  LODWORD(v8[9].Next) = HIDWORD(v46[0]);
  *(_OWORD *)&v8[13].Next = *(_OWORD *)(v3 + 152);
  v8[15].Next = *(struct _SINGLE_LIST_ENTRY **)(v2 + 140);
  LODWORD(v8[16].Next) = *(_DWORD *)(v2 + 148);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDDDDDDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      141,
      (unsigned int)WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
      v8[13].Next,
      WORD2(v8[13].Next),
      HIWORD(v8[13].Next),
      (char)v8[14].Next,
      BYTE1(v8[14].Next),
      BYTE2(v8[14].Next),
      BYTE3(v8[14].Next),
      BYTE4(v8[14].Next),
      BYTE5(v8[14].Next),
      BYTE6(v8[14].Next),
      HIBYTE(v8[14].Next));
    v3 = v44;
    v2 = v45;
  }
  BYTE4(v8[12].Next) = v4;
  v11 = v8 + 7;
  v12 = 0;
  HIDWORD(v8[11].Next) |= LODWORD(v46[1]);
  LODWORD(v8[12].Next) = v46[0];
  v8[6].Next = v8 + 5;
  v8[5].Next = v8 + 5;
  v8[8].Next = v8 + 7;
  v8[7].Next = v8 + 7;
  if ( LODWORD(v8[9].Next) )
  {
    while ( 1 )
    {
      TapiLine = (struct _SINGLE_LIST_ENTRY *)AllocateTapiLine(v8, v12);
      if ( !TapiLine )
      {
        FreeTapiProvider(v8);
        v8 = 0;
        goto LABEL_20;
      }
      Next = v8[8].Next;
      if ( Next->Next != v11 )
        break;
      TapiLine->Next = v11;
      ++v12;
      TapiLine[1].Next = Next;
      Next->Next = TapiLine;
      v8[8].Next = TapiLine;
      if ( v12 >= LODWORD(v8[9].Next) )
        goto LABEL_18;
    }
LABEL_68:
    __fastfail(3u);
  }
LABEL_18:
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
  v16 = *(ULONG **)&WPP_MAIN_CB.ActiveThreadCount;
  LOBYTE(WPP_MAIN_CB.SectorSize) = v15;
  while ( 1 )
  {
    if ( v16 == &WPP_MAIN_CB.ActiveThreadCount )
      goto LABEL_37;
    if ( v16[4] == 1
      && (struct _SINGLE_LIST_ENTRY *)*((_QWORD *)v16 + 13) == v8[13].Next
      && (struct _SINGLE_LIST_ENTRY *)*((_QWORD *)v16 + 14) == v8[14].Next
      && *(_DWORD *)(v2 + 140) == v16[30] )
    {
      break;
    }
    v16 = *(ULONG **)v16;
  }
  if ( v16[18] == LODWORD(v8[9].Next) )
  {
    FreeTapiProvider(v8);
    v8 = (struct _SINGLE_LIST_ENTRY *)v16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v18 = *(_BYTE *)(v3 + 166);
    v19 = *(_BYTE *)(v3 + 165);
    v20 = *(_BYTE *)(v3 + 167);
    v21 = *(_BYTE *)(v3 + 164);
    v22 = *(_BYTE *)(v3 + 163);
    v23 = *(_BYTE *)(v3 + 162);
    v24 = *(_BYTE *)(v3 + 161);
    v25 = *(_BYTE *)(v3 + 160);
    v26 = *(_WORD *)(v3 + 158);
    OidRequest = *(_WORD *)(v3 + 156);
    v3 = v44;
    WPP_SF_DDDDDDDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      142,
      (unsigned int)WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
      *(_DWORD *)(v44 + 152),
      OidRequest,
      v26,
      v25,
      v24,
      v23,
      v22,
      v21,
      v19,
      v18,
      v20);
    v2 = v45;
  }
  if ( v16 == &WPP_MAIN_CB.ActiveThreadCount )
  {
LABEL_37:
    SecurityDescriptor = (struct _SINGLE_LIST_ENTRY *)WPP_MAIN_CB.SecurityDescriptor;
    if ( *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.SecurityDescriptor != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.ActiveThreadCount )
      goto LABEL_68;
    v8->Next = (struct _SINGLE_LIST_ENTRY *)&WPP_MAIN_CB.ActiveThreadCount;
    v8[1].Next = SecurityDescriptor;
    SecurityDescriptor->Next = v8;
    WPP_MAIN_CB.SecurityDescriptor = v8;
    WPP_MAIN_CB.DeviceLock.Header.LockNV += LODWORD(v8[9].Next);
  }
  if ( !LODWORD(WPP_MAIN_CB.Dpc.DpcData) )
    LODWORD(v8[2].Next) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, WPP_MAIN_CB.SectorSize);
  LOBYTE(v8[18].Next) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v8[17]);
  v28 = v8 + 7;
  *(_QWORD *)(v2 + 104) = v8;
  v8[4].Next = (struct _SINGLE_LIST_ENTRY *)v2;
  v8[3].Next = (struct _SINGLE_LIST_ENTRY *)v3;
  while ( 1 )
  {
    v29 = v28->Next;
    if ( v28->Next == v28 )
      break;
    if ( v29[1].Next != v28 )
      goto LABEL_68;
    v30 = v29->Next;
    if ( v29->Next[1].Next != v29 )
      goto LABEL_68;
    v28->Next = v30;
    v30[1].Next = v28;
    v31 = v8[6].Next;
    if ( v31->Next != &v8[5] )
      goto LABEL_68;
    v29->Next = v8 + 5;
    v29[1].Next = v31;
    v31->Next = v29;
    v8[6].Next = v29;
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState, 0);
    v32 = *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1);
    if ( *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy == *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) )
    {
      v33 = (struct _SINGLE_LIST_ENTRY *)ExAllocatePool2(
                                           64,
                                           (unsigned int)(8
                                                        * (*((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1)
                                                         + (*((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) >> 1))),
                                           7100496);
      v34 = v33;
      if ( !v33 )
      {
        NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
        goto LABEL_58;
      }
      memmove(v33, WPP_MAIN_CB.Dpc.DpcListEntry.Next, 8LL * *((unsigned int *)&WPP_MAIN_CB.DeviceQueue.1 + 1));
      ExFreePoolWithTag(WPP_MAIN_CB.Dpc.DpcListEntry.Next, 0);
      v32 = (*((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) >> 1) + *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1);
      WPP_MAIN_CB.Dpc.DpcListEntry.Next = v34;
      *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1) = v32;
    }
    TargetInfoAsUlong = WPP_MAIN_CB.Dpc.TargetInfoAsUlong;
    v36 = v32;
    v37 = WPP_MAIN_CB.Dpc.TargetInfoAsUlong;
    while ( WPP_MAIN_CB.Dpc.DpcListEntry.Next[TargetInfoAsUlong].Next )
    {
      if ( !--v36 )
        goto LABEL_57;
      TargetInfoAsUlong = ((int)TargetInfoAsUlong + 1) % v32;
      v37 = (unsigned int)TargetInfoAsUlong;
    }
    HIDWORD(v29[4].Next) |= 1u;
    LODWORD(v29[6].Next) = TargetInfoAsUlong;
    WPP_MAIN_CB.Dpc.DpcListEntry.Next[v37].Next = v29;
    ++*(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy;
    WPP_MAIN_CB.Dpc.TargetInfoAsUlong = (WPP_MAIN_CB.Dpc.TargetInfoAsUlong + 1)
                                      % *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        154,
        WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
        v29,
        v29[6].Next);
LABEL_57:
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
    if ( v36 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)&v8[17], (KIRQL)v8[18].Next);
      Src = v29[5].Next;
      Next_low = LODWORD(v29[6].Next);
      v49 = 19;
      v48 = 0;
      v50 = 0;
      v52 = 0;
      PxIndicateStatus(&Src);
      LOBYTE(v8[18].Next) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v8[17]);
    }
    else
    {
LABEL_58:
      FreeTapiLine(v29);
    }
  }
  v38 = (KIRQL)v8[18].Next;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  LODWORD(v8[2].Next) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&v8[17], v38);
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState, 0);
  for ( i = 0; i < *((_DWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 1); ++i )
  {
    v40 = WPP_MAIN_CB.Dpc.DpcListEntry.Next[i].Next;
    if ( v40 )
    {
      LOBYTE(v40[16].Next) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v40[15]);
      if ( v40[3].Next == v8 )
      {
        LODWORD(v40[10].Next[7].Next) |= 4u;
        v40[7].Next = v8[4].Next;
        if ( HIDWORD(v40[10].Next[1].Next) )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)&v40[15], (KIRQL)v40[16].Next);
          Src = v40[5].Next;
          v49 = 3;
          v48 = 0;
          v50 = 0;
          Next_low = 0;
          v52 = 0;
          PxIndicateStatus(&Src);
          LOBYTE(v40[16].Next) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v40[15]);
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)&v40[15], (KIRQL)v40[16].Next);
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
  v41 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v8[17]);
  LOBYTE(v8[18].Next) = v41;
  KeReleaseSpinLock((PKSPIN_LOCK)&v8[17], v41);
LABEL_20:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1400062c0  mov     [rsp-8+arg_10], rbx
0x1400062c5  push    rbp
0x1400062c6  push    rsi
0x1400062c7  push    rdi
0x1400062c8  push    r12
0x1400062ca  push    r13
0x1400062cc  push    r14
0x1400062ce  push    r15
0x1400062d0  lea     rbp, [rsp-100h]
0x1400062d8  sub     rsp, 200h
0x1400062df  mov     rax, cs:__security_cookie
0x1400062e6  xor     rax, rsp
0x1400062e9  mov     [rbp+130h+var_40], rax
0x1400062f0  xor     eax, eax
0x1400062f2  mov     [rbp+130h+var_1B0], rdx
0x1400062f6  mov     rsi, rdx
0x1400062f9  mov     [rsp+230h+var_1B8], rcx
0x1400062fe  mov     r15, rcx
0x140006301  mov     [rbp+130h+var_1A8], rax
0x140006305  mov     [rbp+130h+var_1A0], eax
0x140006308  lea     ebx, [rax+1]
0x14000630b  mov     r13b, bl
0x14000630e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006315  lea     rax, WPP_GLOBAL_Control
0x14000631c  cmp     rcx, rax
0x14000631f  jz      short loc_14000633C
0x140006321  cmp     byte ptr [rcx+29h], 4
0x140006325  jb      short loc_14000633C
0x140006327  mov     rcx, [rcx+18h]
0x14000632b  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140006332  mov     edx, 8Ch
0x140006337  call    WPP_SF_
0x14000633c  xor     edx, edx; Val
0x14000633e  lea     rcx, [rbp+130h+var_160]; void *
0x140006342  mov     r8d, 118h; Size
0x140006348  call    memset
0x14000634d  xor     eax, eax
0x14000634f  mov     dword ptr [rbp+130h+var_160.Header.Type], 0F00196h
0x140006356  xor     r14d, r14d
0x140006359  mov     [rbp+130h+var_1A8], rax
0x14000635d  lea     rcx, [rbp+130h+Event]; Event
0x140006364  mov     [rbp+130h+var_1A0], eax
0x140006367  mov     qword ptr [rbp+130h+var_160.PortNumber], r14
0x14000636b  call    cs:__imp_NdisInitializeEvent
0x140006372  nop     dword ptr [rax+rax+00h]
0x140006377  mov     rdx, [rsi+18h]; NdisAfHandle
0x14000637b  lea     rax, [rbp+130h+var_1A8]
0x14000637f  mov     rcx, [r15+20h]; NdisBindingHandle
0x140006383  xor     r9d, r9d; NdisPartyHandle
0x140006386  mov     qword ptr [rbp+130h+var_160.DATA+8], rax
0x14000638a  xor     r8d, r8d; NdisVcHandle
0x14000638d  lea     rax, [rbp+130h+var_160]
0x140006391  mov     [rbp+130h+var_160.RequestType], r14d
0x140006395  mov     [rsp+230h+OidRequest], rax; OidRequest
0x14000639a  mov     dword ptr [rbp+130h+var_160.DATA], 0FE001001h
0x1400063a1  mov     dword ptr [rbp+130h+var_160.DATA+10h], 0Ch
0x1400063a8  call    cs:__imp_NdisCoOidRequest
0x1400063af  nop     dword ptr [rax+rax+00h]
0x1400063b4  cmp     eax, 103h
0x1400063b9  jnz     short loc_1400063D6
0x1400063bb  xor     edx, edx; MsToWait
0x1400063bd  lea     rcx, [rbp+130h+Event]; Event
0x1400063c4  call    cs:__imp_NdisWaitEvent
0x1400063cb  nop     dword ptr [rax+rax+00h]
0x1400063d0  mov     eax, [rbp+130h+var_50]
0x1400063d6  test    eax, eax
0x1400063d8  jz      short loc_1400063FA
0x1400063da  mov     r12, r14
0x1400063dd  cmp     eax, 0C00000BBh
0x1400063e2  jnz     loc_1400065CF
0x1400063e8  mov     eax, ebx
0x1400063ea  mov     dword ptr [rbp+130h+var_1A8], 30000h
0x1400063f1  mov     [rbp+130h+var_1A8+4], rax
0x1400063f5  mov     r13b, r14b
0x1400063f8  jmp     short loc_1400063FD
0x1400063fa  mov     eax, dword ptr [rbp+130h+var_1A8+4]
0x1400063fd  lea     edx, ds:0A0h[rax*8]
0x140006404  mov     ecx, 40h ; '@'
0x140006409  mov     r8d, 395850h
0x14000640f  call    cs:__imp_ExAllocatePool2
0x140006416  nop     dword ptr [rax+rax+00h]
0x14000641b  mov     r12, rax
0x14000641e  test    rax, rax
0x140006421  jz      loc_1400065CF
0x140006427  lea     rcx, [rax+88h]; SpinLock
0x14000642e  call    cs:__imp_KeInitializeSpinLock
0x140006435  nop     dword ptr [rax+rax+00h]
0x14000643a  mov     [r12+10h], ebx
0x14000643f  mov     [r12+18h], r15
0x140006444  mov     [r12+20h], rsi
0x140006449  mov     ecx, dword ptr [rbp+130h+var_1A8+4]
0x14000644c  mov     [r12+48h], ecx
0x140006451  movups  xmm0, xmmword ptr [r15+98h]
0x140006459  movdqu  xmmword ptr [r12+68h], xmm0
0x140006460  movsd   xmm0, qword ptr [rsi+8Ch]
0x140006468  movsd   qword ptr [r12+78h], xmm0
0x14000646f  mov     eax, [rsi+94h]
0x140006475  mov     [r12+80h], eax
0x14000647d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006484  lea     rax, WPP_GLOBAL_Control
0x14000648b  cmp     rcx, rax
0x14000648e  jz      loc_14000652E
0x140006494  cmp     byte ptr [rcx+29h], 4
0x140006498  jb      loc_14000652E
0x14000649e  movzx   r8d, byte ptr [r12+76h]
0x1400064a4  mov     edx, 8Dh
0x1400064a9  movzx   r9d, byte ptr [r12+75h]
0x1400064af  movzx   eax, byte ptr [r12+77h]
0x1400064b5  movzx   r10d, byte ptr [r12+74h]
0x1400064bb  movzx   r11d, byte ptr [r12+73h]
0x1400064c1  movzx   ebx, byte ptr [r12+72h]
0x1400064c7  movzx   edi, byte ptr [r12+71h]
0x1400064cd  movzx   esi, byte ptr [r12+70h]
0x1400064d3  movzx   r14d, word ptr [r12+6Eh]
0x1400064d9  movzx   r15d, word ptr [r12+6Ch]
0x1400064df  mov     rcx, [rcx+18h]
0x1400064e3  mov     [rsp+230h+var_1C8], eax
0x1400064e7  mov     [rsp+230h+var_1D0], r8d
0x1400064ec  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400064f3  mov     [rsp+230h+var_1D8], r9d
0x1400064f8  mov     r9d, [r12+68h]
0x1400064fd  mov     [rsp+230h+var_1E0], r10d
0x140006502  mov     [rsp+230h+var_1E8], r11d
0x140006507  mov     [rsp+230h+var_1F0], ebx
0x14000650b  mov     [rsp+230h+var_1F8], edi
0x14000650f  mov     [rsp+230h+var_200], esi
0x140006513  mov     [rsp+230h+var_208], r14d
0x140006518  mov     dword ptr [rsp+230h+OidRequest], r15d
0x14000651d  call    WPP_SF_DDDDDDDDDDD
0x140006522  mov     r15, [rsp+230h+var_1B8]
0x140006527  xor     r14d, r14d
0x14000652a  mov     rsi, [rbp+130h+var_1B0]
0x14000652e  mov     [r12+64h], r13b
0x140006533  lea     rbx, [r12+38h]
0x140006538  mov     eax, [rbp+130h+var_1A0]
0x14000653b  mov     edi, r14d
0x14000653e  or      [r12+5Ch], eax
0x140006543  mov     eax, dword ptr [rbp+130h+var_1A8]
0x140006546  mov     [r12+60h], eax
0x14000654b  lea     rax, [r12+28h]
0x140006550  mov     [rax+8], rax
0x140006554  mov     [rax], rax
0x140006557  mov     [rbx+8], rbx
0x14000655b  mov     [rbx], rbx
0x14000655e  cmp     [r12+48h], r14d
0x140006563  jbe     short loc_140006598
0x140006565  mov     edx, edi
0x140006567  mov     rcx, r12
0x14000656a  call    AllocateTapiLine
0x14000656f  test    rax, rax
0x140006572  jz      short loc_1400065C4
0x140006574  mov     rcx, [rbx+8]
0x140006578  cmp     [rcx], rbx
0x14000657b  jnz     loc_140006B58
0x140006581  mov     [rax], rbx
0x140006584  inc     edi
0x140006586  mov     [rax+8], rcx
0x14000658a  mov     [rcx], rax
0x14000658d  mov     [rbx+8], rax
0x140006591  cmp     edi, [r12+48h]
0x140006596  jb      short loc_140006565
0x140006598  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; SpinLock
0x14000659f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400065a6  nop     dword ptr [rax+rax+00h]
0x1400065ab  mov     r13, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x1400065b2  lea     rbx, WPP_MAIN_CB.ActiveThreadCount
0x1400065b9  mov     byte ptr cs:WPP_MAIN_CB.SectorSize, al
0x1400065bf  jmp     loc_14000665B
0x1400065c4  mov     rcx, r12; P
0x1400065c7  call    FreeTapiProvider
0x1400065cc  mov     r12, r14
0x1400065cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065d6  lea     rax, WPP_GLOBAL_Control
0x1400065dd  cmp     rcx, rax
0x1400065e0  jz      short loc_140006600
0x1400065e2  cmp     byte ptr [rcx+29h], 4
0x1400065e6  jb      short loc_140006600
0x1400065e8  mov     rcx, [rcx+18h]
0x1400065ec  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400065f3  mov     edx, 8Fh
0x1400065f8  mov     r9, r12
0x1400065fb  call    WPP_SF_q
0x140006600  mov     rax, r12
0x140006603  mov     rcx, [rbp+130h+var_40]
0x14000660a  xor     rcx, rsp; StackCookie
0x14000660d  call    __security_check_cookie
0x140006612  mov     rbx, [rsp+230h+arg_10]
0x14000661a  add     rsp, 200h
0x140006621  pop     r15
0x140006623  pop     r14
0x140006625  pop     r13
0x140006627  pop     r12
0x140006629  pop     rdi
0x14000662a  pop     rsi
0x14000662b  pop     rbp
0x14000662c  retn
0x14000662e  cmp     dword ptr [r13+10h], 1
0x140006633  jnz     short loc_140006657
0x140006635  mov     rax, [r13+68h]
0x140006639  cmp     rax, [r12+68h]
0x14000663e  jnz     short loc_140006657
0x140006640  mov     rax, [r13+70h]
0x140006644  cmp     rax, [r12+70h]
0x140006649  jnz     short loc_140006657
0x14000664b  mov     eax, [r13+78h]
0x14000664f  cmp     [rsi+8Ch], eax
0x140006655  jz      short loc_140006665
0x140006657  mov     r13, [r13+0]
0x14000665b  cmp     r13, rbx
0x14000665e  jnz     short loc_14000662E
0x140006660  jmp     loc_14000674B
0x140006665  mov     eax, [r12+48h]
0x14000666a  cmp     [r13+48h], eax
0x14000666e  jnz     short loc_14000667B
0x140006670  mov     rcx, r12; P
0x140006673  call    FreeTapiProvider
0x140006678  mov     r12, r13
0x14000667b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006682  lea     rax, WPP_GLOBAL_Control
0x140006689  cmp     rcx, rax
0x14000668c  jz      loc_140006746
0x140006692  cmp     byte ptr [rcx+29h], 4
0x140006696  jb      loc_140006746
0x14000669c  movzx   r8d, byte ptr [r15+0A6h]
0x1400066a4  mov     edx, 8Eh
0x1400066a9  movzx   r9d, byte ptr [r15+0A5h]
0x1400066b1  movzx   eax, byte ptr [r15+0A7h]
0x1400066b9  movzx   r10d, byte ptr [r15+0A4h]
0x1400066c1  movzx   r11d, byte ptr [r15+0A3h]
0x1400066c9  movzx   ebx, byte ptr [r15+0A2h]
0x1400066d1  movzx   edi, byte ptr [r15+0A1h]
0x1400066d9  movzx   esi, byte ptr [r15+0A0h]
0x1400066e1  movzx   r14d, word ptr [r15+9Eh]
0x1400066e9  movzx   r15d, word ptr [r15+9Ch]
0x1400066f1  mov     rcx, [rcx+18h]
0x1400066f5  mov     [rsp+230h+var_1C8], eax
0x1400066f9  mov     [rsp+230h+var_1D0], r8d
0x1400066fe  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140006705  mov     [rsp+230h+var_1D8], r9d
0x14000670a  mov     [rsp+230h+var_1E0], r10d
0x14000670f  mov     [rsp+230h+var_1E8], r11d
0x140006714  mov     [rsp+230h+var_1F0], ebx
0x140006718  mov     [rsp+230h+var_1F8], edi
0x14000671c  mov     [rsp+230h+var_200], esi
0x140006720  mov     [rsp+230h+var_208], r14d
0x140006725  mov     dword ptr [rsp+230h+OidRequest], r15d
0x14000672a  mov     r15, [rsp+230h+var_1B8]
0x14000672f  mov     r9d, [r15+98h]
0x140006736  call    WPP_SF_DDDDDDDDDDD
0x14000673b  mov     rsi, [rbp+130h+var_1B0]
0x14000673f  lea     rbx, WPP_MAIN_CB.ActiveThreadCount
0x140006746  cmp     r13, rbx
0x140006749  jnz     short loc_140006779
0x14000674b  mov     rax, cs:WPP_MAIN_CB.SecurityDescriptor
0x140006752  cmp     [rax], rbx
0x140006755  jnz     loc_140006B58
0x14000675b  mov     [r12], rbx
0x14000675f  mov     [r12+8], rax
0x140006764  mov     [rax], r12
0x140006767  mov     cs:WPP_MAIN_CB.SecurityDescriptor, r12
0x14000676e  mov     eax, [r12+48h]
0x140006773  add     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header, eax
0x140006779  xor     r13d, r13d
0x14000677c  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, r13d
0x140006783  jnz     short loc_14000678A
0x140006785  mov     [r12+10h], r13d
0x14000678a  mov     dl, byte ptr cs:WPP_MAIN_CB.SectorSize; NewIrql
0x140006790  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; SpinLock
0x140006797  call    cs:__imp_KeReleaseSpinLock
0x14000679e  nop     dword ptr [rax+rax+00h]
0x1400067a3  lea     r14, [r12+88h]
0x1400067ab  mov     rcx, r14; SpinLock
0x1400067ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400067b5  nop     dword ptr [rax+rax+00h]
0x1400067ba  mov     [r12+90h], al
0x1400067c2  lea     rdi, [r12+38h]
0x1400067c7  mov     [rsi+68h], r12
0x1400067cb  mov     [r12+20h], rsi
0x1400067d0  mov     [r12+18h], r15
0x1400067d5  mov     rbx, [rdi]
0x1400067d8  cmp     rbx, rdi
0x1400067db  jz      loc_1400069FB
0x1400067e1  cmp     [rbx+8], rdi
0x1400067e5  jnz     loc_140006B58
0x1400067eb  mov     rax, [rbx]
0x1400067ee  cmp     [rax+8], rbx
0x1400067f2  jnz     loc_140006B58
0x1400067f8  mov     [rdi], rax
0x1400067fb  mov     [rax+8], rdi
0x1400067ff  lea     rax, [r12+28h]
0x140006804  mov     rcx, [rax+8]
0x140006808  cmp     [rcx], rax
0x14000680b  jnz     loc_140006B58
0x140006811  mov     [rbx], rax
0x140006814  lea     rdx, [rsp+230h+LockState]; LockState
0x140006819  mov     [rbx+8], rcx
0x14000681d  xor     r8d, r8d; Flags
0x140006820  mov     [rcx], rbx
0x140006823  mov     [rax+8], rbx
0x140006827  xor     eax, eax
  ... truncated ...
```
