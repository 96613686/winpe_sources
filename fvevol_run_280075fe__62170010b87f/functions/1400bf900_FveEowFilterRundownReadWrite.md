# FveEowFilterRundownReadWrite

- ea: `0x1400bf900`
- end: `0x1400c0371`
- name: `FveEowFilterRundownReadWrite`
- size: `2673`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400281d8`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x14000bc1c`
- `0x14000f364`
- `0x14001105c`
- `0x1400111d8`
- `0x1400292a0`
- `0x14002bac0`
- `0x1400bf900`
- `0x1400d9450`
- `0x1400dc058`
- `0x1400dc2b0`
- `0x1400dda5c`
- `0x1400ddd14`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400c02a5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c02a5`
- `ntoskrnl!ObfReferenceObject` at `0x1400bfdff`
- `ntoskrnl!ObfReferenceObject` at `0x1400bfdff`
- `ntoskrnl!RtlAreBitsClear` at `0x1400bfc58`
- `ntoskrnl!RtlAreBitsClear` at `0x1400bfc58`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bfd02`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bff32`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bfd02`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bff32`
- `ntoskrnl!RtlAreBitsSet` at `0x1400bfbda`
- `ntoskrnl!RtlAreBitsSet` at `0x1400bfbda`
- `ntoskrnl!IoBoostThreadIo` at `0x1400c0285`
- `ntoskrnl!IoBoostThreadIo` at `0x1400c0285`
- `ntoskrnl!KeSetEvent` at `0x1400c02ce`
- `ntoskrnl!KeSetEvent` at `0x1400c02ce`
- `ntoskrnl!KeBugCheckEx` at `0x1400c0174`
- `ntoskrnl!KeBugCheckEx` at `0x1400c0195`
- `ntoskrnl!KeBugCheckEx` at `0x1400c030b`
- `ntoskrnl!KeBugCheckEx` at `0x1400c0174`
- `ntoskrnl!KeBugCheckEx` at `0x1400c0195`
- `ntoskrnl!KeBugCheckEx` at `0x1400c030b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c02e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c02e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfd78`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfd78`

## string_xrefs

- `0x1400bf9f7`: `Write`
- `0x1400c0134`: `write`

## pseudocode

```c
__int64 __fastcall FveEowFilterRundownReadWrite(__int64 a1, IRP *a2, char a3, unsigned __int64 a4, unsigned int a5)
{
  _QWORD *v5; // rdi
  unsigned int v6; // r12d
  IRP *v7; // r15
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rsi
  char v14; // cl
  const char *v15; // r9
  unsigned __int64 v16; // rax
  PDEVICE_OBJECT *v17; // rdx
  __int128 *v18; // r12
  char v19; // si
  unsigned __int64 v20; // rax
  char v21; // bl
  char v22; // di
  ULONG_PTR v23; // r14
  int v24; // r10d
  int v25; // r11d
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  struct _LIST_ENTRY *v28; // rdx
  struct _LIST_ENTRY *Flink; // rbx
  char IsPagingRequest; // si
  IO_PRIORITY_HINT IoPriorityHint; // edi
  int PriorityFromIrp; // eax
  int v33; // edx
  __int64 Pool2; // rax
  PVOID *v35; // rbx
  int v36; // ecx
  void *v37; // rcx
  PVOID *v38; // rax
  struct _LIST_ENTRY *v39; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v41; // r15
  char v42; // bl
  IO_PRIORITY_HINT v43; // edi
  ULONG_PTR v44; // rbx
  __int64 v45; // r9
  ULONG_PTR v46; // rcx
  char v47; // dl
  const char *v48; // r9
  unsigned int *v49; // rbx
  __int64 v50; // rax
  int v51; // eax
  void *v52; // rcx
  int v53; // ecx
  char v55; // [rsp+30h] [rbp-79h]
  char v56; // [rsp+48h] [rbp-61h]
  int v57; // [rsp+50h] [rbp-59h]
  unsigned int v58; // [rsp+68h] [rbp-41h]
  char v59; // [rsp+6Ch] [rbp-3Dh]
  char v60; // [rsp+6Ch] [rbp-3Dh]
  char v61; // [rsp+6Dh] [rbp-3Ch]
  char v62; // [rsp+6Fh] [rbp-3Ah]
  int v63; // [rsp+74h] [rbp-35h]
  PVOID P; // [rsp+78h] [rbp-31h] BYREF
  PVOID *p_P; // [rsp+80h] [rbp-29h]
  int v66; // [rsp+88h] [rbp-21h]
  int v67; // [rsp+8Ch] [rbp-1Dh]
  void *v68; // [rsp+90h] [rbp-19h]
  __int128 v69; // [rsp+98h] [rbp-11h] BYREF
  ULONG_PTR BugCheckParameter3; // [rsp+A8h] [rbp-1h]

  v5 = *(_QWORD **)(a1 + 736);
  v6 = 0;
  v63 = 0;
  v7 = a2;
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(a1) )
  {
    if ( (*(_BYTE *)(a1 + 4403) & 8) != 0 || (v11 = *(_QWORD *)(a1 + 976), *(_WORD *)(v11 + 10) == 1) )
    {
      v10 = 0;
    }
    else
    {
      v10 = *(_DWORD *)(v11 + 28);
      if ( !v10 )
        v10 = 1;
    }
    v9 = *(_QWORD *)(a1 + 976);
  }
  else
  {
    v9 = *(_QWORD *)(a1 + 976);
    if ( *(_WORD *)(v9 + 10) == 1 )
    {
      v10 = 0;
    }
    else
    {
      v10 = *(_DWORD *)(v9 + 28);
      if ( !v10 )
        v10 = 1;
    }
  }
  v12 = *(_QWORD *)(v9 + 56);
  v13 = *(unsigned int *)(a1 + 1308);
  v14 = *(_BYTE *)(*v5 + 48LL);
  p_P = &P;
  P = &P;
  v59 = v14;
  v69 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v15 = "Write";
    if ( !a3 )
      v15 = "Read";
    WPP_SF_sii(WPP_GLOBAL_Control->AttachedDevice, a4, (unsigned int)"Read", (_DWORD)v15, a4, a4 + a5);
  }
  if ( a5 )
  {
    v16 = a5 + a4;
    if ( v16 < a4 )
    {
      v6 = -1073741675;
      goto LABEL_115;
    }
    if ( v16 > v5[3] )
    {
      v6 = -1073741811;
LABEL_115:
      v63 = v6;
      goto LABEL_116;
    }
    v63 = FveEowOverlappedRegionsAcquire(v5, v12, v10 * v13, a4, a5);
    v6 = v63;
    if ( v63 < 0 )
      goto LABEL_116;
    v18 = (__int128 *)v69;
    v19 = v59 & 2;
    v20 = 0;
    v60 = v59 & 2;
    v21 = 0;
    v58 = 0;
    v22 = 0;
    v61 = 0;
    v62 = 0;
    if ( (__int128 *)v69 == &v69 )
      v68 = 0;
    else
      v68 = *(void **)(v69 + 136);
    while ( 1 )
    {
      if ( v18 == &v69 )
      {
        if ( v22 || v21 )
        {
LABEL_112:
          v6 = 259;
          v63 = 259;
          v7->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        }
        else
        {
          v6 = v63;
          v7->Tail.Overlay.DriverContext[2] = (PVOID)v20;
          v7->Tail.Overlay.DriverContext[3] = v68;
        }
        LOBYTE(v17) = 0;
        FveEowOverlappedRegionsRelease(&v69, v17);
        goto LABEL_116;
      }
      v23 = *((_QWORD *)v18 + 17);
      v24 = *((_DWORD *)v18 + 10);
      v25 = *((_DWORD *)v18 + 12);
      BugCheckParameter3 = v23;
      v67 = v24;
      v66 = v25;
      v17 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_iiiiiLLL(WPP_GLOBAL_Control->AttachedDevice, 95);
          v24 = v67;
          v17 = &WPP_GLOBAL_Control;
          v25 = v66;
        }
        v20 = v58;
      }
      if ( !v19 )
        break;
      if ( !*(_BYTE *)(v23 + 13) )
      {
        if ( RtlAreBitsClear((PRTL_BITMAP)(*(_QWORD *)v23 + 16 * (*(unsigned int *)(v23 + 20) + 5LL)), v24, v25) )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            goto LABEL_39;
          }
          v27 = 99;
          goto LABEL_38;
        }
        goto LABEL_56;
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          goto LABEL_39;
        v27 = 97;
        goto LABEL_38;
      }
LABEL_40:
      v18 = *(__int128 **)v18;
    }
    if ( *(_BYTE *)(v23 + 12) )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_40;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_39;
      v27 = 96;
LABEL_38:
      WPP_SF_(v26->AttachedDevice, v27, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
      goto LABEL_39;
    }
    if ( RtlAreBitsSet((PRTL_BITMAP)(*(_QWORD *)v23 + 16 * (*(unsigned int *)(v23 + 20) + 5LL)), v24, v25) )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_39;
      }
      v27 = 98;
      goto LABEL_38;
    }
LABEL_56:
    if ( *((_DWORD *)v18 + 16) )
    {
      if ( !v22 && !v21 )
      {
        v28 = (struct _LIST_ENTRY *)*((_QWORD *)v18 + 15);
        if ( (__int128 *)v28->Flink != v18 + 7 )
          goto LABEL_131;
        v7->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(v18 + 7);
        v7->Tail.Overlay.ListEntry.Blink = v28;
        v28->Flink = &v7->Tail.Overlay.ListEntry;
        *((_QWORD *)v18 + 15) = &v7->Tail.Overlay.ListEntry;
        Flink = v7->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
        IsPagingRequest = FveIsPagingRequest(a1, v7, a4, a5);
        IoPriorityHint = IoGetIoPriorityHint(v7);
        PriorityFromIrp = GetPriorityFromIrpEx(a1, (__int64)v7, 0xFFFFFFFF);
        LOBYTE(v33) = (_BYTE)Flink;
        if ( (unsigned __int8)FveEowUpdatePriority(v23, v33, PriorityFromIrp, IoPriorityHint, IsPagingRequest, 0) )
        {
          if ( *((_QWORD *)v18 + 22) )
          {
            if ( *((_DWORD *)v18 + 57) != 5 )
            {
              Pool2 = ExAllocatePool2(64, 48, 1699042886);
              v35 = (PVOID *)Pool2;
              if ( Pool2 )
              {
                *(_OWORD *)Pool2 = 0;
                *(_OWORD *)(Pool2 + 16) = 0;
                *(_OWORD *)(Pool2 + 32) = 0;
                *(_DWORD *)(Pool2 + 40) = 1;
                v36 = *((_DWORD *)v18 + 57);
                *(_DWORD *)(Pool2 + 44) = v36;
                *((_DWORD *)v18 + 56) = v36;
                ++*((_DWORD *)v18 + 53);
                if ( _InterlockedIncrement((volatile signed __int32 *)v18 + 52) <= 1 )
                  goto LABEL_130;
                *(_QWORD *)(Pool2 + 24) = v18 + 13;
                *(_QWORD *)(Pool2 + 32) = (char *)v18 + 184;
                v37 = (void *)*((_QWORD *)v18 + 22);
                *(_QWORD *)(Pool2 + 16) = v37;
                ObfReferenceObject(v37);
                v38 = p_P;
                if ( *p_P != &P )
                  goto LABEL_131;
                v35[1] = p_P;
                *v35 = &P;
                *v38 = v35;
                p_P = v35;
              }
            }
          }
        }
        v21 = 1;
        v61 = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
        }
        if ( !a3 )
          goto LABEL_112;
        v22 = v62;
LABEL_73:
        v19 = v60;
      }
LABEL_39:
      v20 = v58;
      goto LABEL_40;
    }
    if ( !v19 && a3 )
    {
      if ( v21 )
      {
        v39 = v7->Tail.Overlay.ListEntry.Flink;
        if ( (PVOID *)v39->Blink != &v7->Tail.CompletionKey + 6 )
          goto LABEL_131;
        Blink = v7->Tail.Overlay.ListEntry.Blink;
        if ( (PVOID *)Blink->Flink != &v7->Tail.CompletionKey + 6 )
          goto LABEL_131;
        Blink->Flink = v39;
        v39->Blink = Blink;
        v61 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
        }
      }
      v41 = v7->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
      v42 = FveIsPagingRequest(a1, a2, a4, a5);
      v43 = IoGetIoPriorityHint(a2);
      GetPriorityFromIrpEx(a1, (__int64)a2, 8u);
      v57 = BYTE1(v41);
      v56 = v42;
      v44 = BugCheckParameter3;
      v55 = (char)v41;
      v7 = a2;
      FveEowRegionSetRequest(BugCheckParameter3, (ULONG_PTR)a2, v43, v55, v67, v66, v56, v57);
      if ( _InterlockedIncrement((volatile signed __int32 *)&a2->Tail.Overlay.DeviceQueueEntry.SortKey) <= 0 )
        KeBugCheckEx(0x120u, 8u, 0, v44, (ULONG_PTR)a2);
      v45 = *((unsigned int *)v18 + 18);
      if ( (_DWORD)v45 )
      {
        *((_DWORD *)v18 + 16) = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids, v45);
        }
      }
      else
      {
        *((_DWORD *)v18 + 16) = 2;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            103,
            WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids,
            *((unsigned int *)v18 + 19));
        }
        v46 = *((_QWORD *)v18 + 18);
        if ( *(int *)(v46 + 744) <= 0 )
          KeBugCheckEx(0x120u, 0xBu, v46, 0, 0);
        v47 = *((_BYTE *)v18 + 232) || *((int *)v18 + 73) <= 1;
        FvepQueueWorkItem(
          *(PVOID *)(v46 + 8),
          *((_QWORD *)v18 + 20),
          *((_DWORD *)v18 + 57),
          v47,
          (__int64)FveEowConvStepIssueWorker,
          *((_QWORD *)v18 + 17),
          0,
          *((_DWORD *)v18 + 19),
          0);
      }
      v21 = v61;
      v22 = 1;
      v62 = 1;
      goto LABEL_73;
    }
    ++*((_DWORD *)v18 + 18);
    v20 = ++v58;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v48 = "write";
        if ( !a3 )
          v48 = "read";
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          104,
          (unsigned int)WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids,
          (_DWORD)v48,
          *((_DWORD *)v18 + 18));
        goto LABEL_39;
      }
      v20 = (unsigned int)v20;
    }
    goto LABEL_40;
  }
LABEL_116:
  while ( 1 )
  {
    v49 = (unsigned int *)P;
    if ( P == &P )
      break;
    if ( *((PVOID **)P + 1) != &P || (v50 = *(_QWORD *)P, *(PVOID *)(*(_QWORD *)P + 8LL) != P) )
LABEL_131:
      __fastfail(3u);
    P = *(PVOID *)P;
    *(_QWORD *)(v50 + 8) = &P;
    v51 = v49[10];
    if ( v51 > 0 )
    {
      do
      {
        v49[10] = v51 - 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_Lq(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids,
            v49[11],
            *((_QWORD *)v49 + 2));
        }
        IoBoostThreadIo(*((_QWORD *)v49 + 2), v49[11], 0);
        v51 = v49[10];
      }
      while ( v51 > 0 );
      v6 = v63;
    }
    v52 = (void *)*((_QWORD *)v49 + 2);
    v49[10] = v51 - 1;
    ObfDereferenceObject(v52);
    v53 = _InterlockedDecrement(*((volatile signed __int32 **)v49 + 3));
    if ( v53 < 0 )
LABEL_130:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    if ( !v53 )
      KeSetEvent(*((PRKEVENT *)v49 + 4), 0, 0);
    ExFreePoolWithTag(v49, 0x65455646u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1400bf900  mov     rax, rsp
0x1400bf903  mov     [rax+20h], r9
0x1400bf907  mov     [rax+18h], r8b
0x1400bf90b  mov     [rax+10h], rdx
0x1400bf90f  mov     [rax+8], rcx
0x1400bf913  push    rbp
0x1400bf914  push    rbx
0x1400bf915  push    rsi
0x1400bf916  push    rdi
0x1400bf917  push    r12
0x1400bf919  push    r13
0x1400bf91b  push    r14
0x1400bf91d  push    r15
0x1400bf91f  lea     rbp, [rax-57h]
0x1400bf923  sub     rsp, 0B8h
0x1400bf92a  mov     rdi, [rcx+2E0h]
0x1400bf931  xor     r12d, r12d
0x1400bf934  mov     [rbp+4Fh+var_84], r12d
0x1400bf938  mov     r15, rdx
0x1400bf93b  mov     rsi, rcx
0x1400bf93e  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400bf943  lea     r13d, [r12+1]
0x1400bf948  test    eax, eax
0x1400bf94a  jnz     short loc_1400BF96A
0x1400bf94c  mov     rax, [rsi+3D0h]
0x1400bf953  cmp     [rax+0Ah], r13w
0x1400bf958  jnz     short loc_1400BF95E
0x1400bf95a  xor     ebx, ebx
0x1400bf95c  jmp     short loc_1400BF995
0x1400bf95e  mov     ebx, [rax+1Ch]
0x1400bf961  test    ebx, ebx
0x1400bf963  jnz     short loc_1400BF995
0x1400bf965  mov     ebx, r13d
0x1400bf968  jmp     short loc_1400BF995
0x1400bf96a  test    byte ptr [rsi+1133h], 8
0x1400bf971  jnz     short loc_1400BF981
0x1400bf973  mov     rbx, [rsi+3D0h]
0x1400bf97a  cmp     [rbx+0Ah], r13w
0x1400bf97f  jnz     short loc_1400BF985
0x1400bf981  xor     ebx, ebx
0x1400bf983  jmp     short loc_1400BF98E
0x1400bf985  mov     ebx, [rbx+1Ch]
0x1400bf988  test    ebx, ebx
0x1400bf98a  cmovz   ebx, r13d
0x1400bf98e  mov     rax, [rsi+3D0h]
0x1400bf995  mov     r14, [rax+38h]
0x1400bf999  xorps   xmm0, xmm0
0x1400bf99c  mov     rax, [rdi]
0x1400bf99f  mov     esi, [rsi+51Ch]
0x1400bf9a5  mov     [rbp+4Fh+var_88], r12b
0x1400bf9a9  mov     [rbp+4Fh+var_8A], r12b
0x1400bf9ad  mov     cl, [rax+30h]
0x1400bf9b0  lea     rax, [rbp+4Fh+P]
0x1400bf9b4  mov     [rbp+4Fh+var_78], rax
0x1400bf9b8  lea     rax, [rbp+4Fh+P]
0x1400bf9bc  mov     [rbp+4Fh+P], rax
0x1400bf9c0  mov     [rbp+4Fh+var_8C], cl
0x1400bf9c3  movups  [rbp+4Fh+var_60], xmm0
0x1400bf9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf9ce  lea     rax, WPP_GLOBAL_Control
0x1400bf9d5  cmp     rcx, rax
0x1400bf9d8  jz      short loc_1400BFA1C
0x1400bf9da  test    dword ptr [rcx+2Ch], 100h
0x1400bf9e1  jz      short loc_1400BFA1C
0x1400bf9e3  cmp     byte ptr [rcx+29h], 5
0x1400bf9e7  jb      short loc_1400BFA1C
0x1400bf9e9  mov     rdx, [rbp+4Fh+arg_18]
0x1400bf9ed  lea     r8, aRead; "Read"
0x1400bf9f4  mov     eax, [rbp+4Fh+arg_20]
0x1400bf9f7  lea     r9, aWrite_0; "Write"
0x1400bf9fe  mov     rcx, [rcx+18h]
0x1400bfa02  add     rax, rdx
0x1400bfa05  cmp     [rbp+4Fh+arg_10], r12b
0x1400bfa09  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400bfa0e  cmovz   r9, r8
0x1400bfa12  mov     [rsp+0F0h+BugCheckParameter4], rdx
0x1400bfa17  call    WPP_SF_sii
0x1400bfa1c  cmp     [rbp+4Fh+arg_20], r12d
0x1400bfa20  jz      loc_1400C01F0
0x1400bfa26  mov     rdx, [rbp+4Fh+arg_18]
0x1400bfa2a  mov     ecx, [rbp+4Fh+arg_20]
0x1400bfa2d  lea     rax, [rcx+rdx]
0x1400bfa31  cmp     rax, rdx
0x1400bfa34  jb      loc_1400C01E6
0x1400bfa3a  cmp     rax, [rdi+18h]
0x1400bfa3e  jbe     short loc_1400BFA4B
0x1400bfa40  mov     r12d, 0C000000Dh
0x1400bfa46  jmp     loc_1400C01EC
0x1400bfa4b  mov     eax, ebx
0x1400bfa4d  mov     r9, rdx
0x1400bfa50  mov     r8, rsi
0x1400bfa53  mov     rdx, r14
0x1400bfa56  imul    r8, rax
0x1400bfa5a  lea     rax, [rbp+4Fh+var_88]
0x1400bfa5e  mov     qword ptr [rsp+0F0h+var_B0], rax
0x1400bfa63  lea     rax, [rbp+4Fh+var_8A]
0x1400bfa67  mov     [rsp+0F0h+var_B8], rax
0x1400bfa6c  lea     rax, [rbp+4Fh+var_60]
0x1400bfa70  mov     [rsp+0F0h+var_C0], rax
0x1400bfa75  mov     [rsp+0F0h+BugCheckParameter4], rcx
0x1400bfa7a  mov     rcx, rdi
0x1400bfa7d  call    FveEowOverlappedRegionsAcquire
0x1400bfa82  mov     [rbp+4Fh+var_84], eax
0x1400bfa85  mov     r12d, eax
0x1400bfa88  test    eax, eax
0x1400bfa8a  js      loc_1400C01F0
0x1400bfa90  mov     sil, [rbp+4Fh+var_8C]
0x1400bfa94  lea     rcx, [rbp+4Fh+var_60]
0x1400bfa98  mov     r12, qword ptr [rbp+4Fh+var_60]
0x1400bfa9c  and     sil, 2
0x1400bfaa0  xor     eax, eax
0x1400bfaa2  mov     [rbp+4Fh+var_8C], sil
0x1400bfaa6  xor     bl, bl
0x1400bfaa8  mov     [rbp+4Fh+var_90], eax
0x1400bfaab  xor     dil, dil
0x1400bfaae  mov     [rbp+4Fh+var_8B], bl
0x1400bfab1  mov     [rbp+4Fh+var_89], dil
0x1400bfab5  cmp     r12, rcx
0x1400bfab8  jnz     short loc_1400BFAC0
0x1400bfaba  mov     [rbp+4Fh+var_68], rax
0x1400bfabe  jmp     short loc_1400BFACC
0x1400bfac0  mov     rcx, [r12+88h]
0x1400bfac8  mov     [rbp+4Fh+var_68], rcx
0x1400bfacc  lea     rcx, [rbp+4Fh+var_60]
0x1400bfad0  cmp     r12, rcx
0x1400bfad3  jz      loc_1400C01A2
0x1400bfad9  mov     r14, [r12+88h]
0x1400bfae1  mov     r10d, [r12+28h]
0x1400bfae6  mov     r11d, [r12+30h]
0x1400bfaeb  mov     [rbp+4Fh+BugCheckParameter3], r14
0x1400bfaef  mov     [rbp+4Fh+var_6C], r10d
0x1400bfaf3  mov     [rbp+4Fh+var_70], r11d
0x1400bfaf7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfafe  lea     rdx, WPP_GLOBAL_Control
0x1400bfb05  cmp     rcx, rdx
0x1400bfb08  jz      short loc_1400BFB7A
0x1400bfb0a  test    dword ptr [rcx+2Ch], 100h
0x1400bfb11  jz      short loc_1400BFB77
0x1400bfb13  cmp     byte ptr [rcx+29h], 5
0x1400bfb17  jb      short loc_1400BFB77
0x1400bfb19  mov     eax, [r12+2Ch]
0x1400bfb1e  mov     edx, 5Fh ; '_'
0x1400bfb23  mov     r9, [r14+54h]
0x1400bfb27  mov     r8, [r14+5Ch]
0x1400bfb2b  mov     rcx, [rcx+18h]
0x1400bfb2f  add     r8, r9
0x1400bfb32  mov     [rsp+50h], r11d
0x1400bfb37  mov     [rsp+0F0h+var_A8], eax
0x1400bfb3b  mov     rax, [r12+20h]
0x1400bfb40  mov     dword ptr [rsp+0F0h+var_B0], r10d
0x1400bfb45  mov     [rsp+0F0h+var_B8], rax
0x1400bfb4a  mov     rax, [r12+18h]
0x1400bfb4f  mov     [rsp+0F0h+var_C0], rax
0x1400bfb54  mov     rax, [r12+10h]
0x1400bfb59  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400bfb5e  mov     [rsp+0F0h+BugCheckParameter4], r8
0x1400bfb63  call    WPP_SF_iiiiiLLL
0x1400bfb68  mov     r10d, [rbp+4Fh+var_6C]
0x1400bfb6c  lea     rdx, WPP_GLOBAL_Control
0x1400bfb73  mov     r11d, [rbp+4Fh+var_70]
0x1400bfb77  mov     eax, [rbp+4Fh+var_90]
0x1400bfb7a  test    sil, sil
0x1400bfb7d  jnz     loc_1400BFC17
0x1400bfb83  cmp     [r14+0Ch], sil
0x1400bfb87  jz      short loc_1400BFBC5
0x1400bfb89  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfb90  cmp     rcx, rdx
0x1400bfb93  jz      short loc_1400BFBBC
0x1400bfb95  test    dword ptr [rcx+2Ch], 100h
0x1400bfb9c  jz      short loc_1400BFBB9
0x1400bfb9e  cmp     byte ptr [rcx+29h], 5
0x1400bfba2  jb      short loc_1400BFBB9
0x1400bfba4  mov     edx, 60h ; '`'
0x1400bfba9  mov     rcx, [rcx+18h]
0x1400bfbad  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400bfbb4  call    WPP_SF_
0x1400bfbb9  mov     eax, [rbp+4Fh+var_90]
0x1400bfbbc  mov     r12, [r12]
0x1400bfbc0  jmp     loc_1400BFACC
0x1400bfbc5  mov     ecx, [r14+14h]
0x1400bfbc9  mov     r8d, r11d; Length
0x1400bfbcc  add     rcx, 5
0x1400bfbd0  mov     edx, r10d; StartingIndex
0x1400bfbd3  shl     rcx, 4
0x1400bfbd7  add     rcx, [r14]; BitMapHeader
0x1400bfbda  call    cs:__imp_RtlAreBitsSet
0x1400bfbe1  nop     dword ptr [rax+rax+00h]
0x1400bfbe6  test    al, al
0x1400bfbe8  jz      loc_1400BFCA0
0x1400bfbee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfbf5  lea     r9, WPP_GLOBAL_Control
0x1400bfbfc  cmp     rcx, r9
0x1400bfbff  jz      short loc_1400BFBB9
0x1400bfc01  test    dword ptr [rcx+2Ch], 100h
0x1400bfc08  jz      short loc_1400BFBB9
0x1400bfc0a  cmp     byte ptr [rcx+29h], 5
0x1400bfc0e  jb      short loc_1400BFBB9
0x1400bfc10  mov     edx, 62h ; 'b'
0x1400bfc15  jmp     short loc_1400BFBA9
0x1400bfc17  cmp     byte ptr [r14+0Dh], 0
0x1400bfc1c  jz      short loc_1400BFC43
0x1400bfc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfc25  cmp     rcx, rdx
0x1400bfc28  jz      short loc_1400BFBBC
0x1400bfc2a  test    dword ptr [rcx+2Ch], 100h
0x1400bfc31  jz      short loc_1400BFBB9
0x1400bfc33  cmp     byte ptr [rcx+29h], 5
0x1400bfc37  jb      short loc_1400BFBB9
0x1400bfc39  mov     edx, 61h ; 'a'
0x1400bfc3e  jmp     loc_1400BFBA9
0x1400bfc43  mov     ecx, [r14+14h]
0x1400bfc47  mov     r8d, r11d; Length
0x1400bfc4a  add     rcx, 5
0x1400bfc4e  mov     edx, r10d; StartingIndex
0x1400bfc51  shl     rcx, 4
0x1400bfc55  add     rcx, [r14]; BitMapHeader
0x1400bfc58  call    cs:__imp_RtlAreBitsClear
0x1400bfc5f  nop     dword ptr [rax+rax+00h]
0x1400bfc64  test    al, al
0x1400bfc66  jz      short loc_1400BFCA0
0x1400bfc68  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfc6f  lea     r9, WPP_GLOBAL_Control
0x1400bfc76  cmp     rcx, r9
0x1400bfc79  jz      loc_1400BFBB9
0x1400bfc7f  test    dword ptr [rcx+2Ch], 100h
0x1400bfc86  jz      loc_1400BFBB9
0x1400bfc8c  cmp     byte ptr [rcx+29h], 5
0x1400bfc90  jb      loc_1400BFBB9
0x1400bfc96  mov     edx, 63h ; 'c'
0x1400bfc9b  jmp     loc_1400BFBA9
0x1400bfca0  cmp     dword ptr [r12+40h], 0
0x1400bfca6  jz      loc_1400BFE82
0x1400bfcac  test    dil, dil
0x1400bfcaf  jnz     loc_1400BFBB9
0x1400bfcb5  test    bl, bl
0x1400bfcb7  jnz     loc_1400BFBB9
0x1400bfcbd  lea     rcx, [r12+70h]
0x1400bfcc2  mov     rdx, [rcx+8]
0x1400bfcc6  cmp     [rdx], rcx
0x1400bfcc9  jnz     loc_1400C0318
0x1400bfccf  mov     r9d, [rbp+4Fh+arg_20]
0x1400bfcd3  lea     rax, [r15+0A8h]
0x1400bfcda  mov     r8, [rbp+4Fh+arg_18]
0x1400bfcde  mov     [rax], rcx
0x1400bfce1  mov     [rax+8], rdx
0x1400bfce5  mov     [rdx], rax
0x1400bfce8  mov     rdx, r15
0x1400bfceb  mov     [rcx+8], rax
0x1400bfcef  mov     rcx, [rbp+4Fh+arg_0]
0x1400bfcf3  mov     rbx, [r15+78h]
0x1400bfcf7  call    FveIsPagingRequest
0x1400bfcfc  mov     rcx, r15; Irp
0x1400bfcff  mov     sil, al
0x1400bfd02  call    cs:__imp_IoGetIoPriorityHint
0x1400bfd09  nop     dword ptr [rax+rax+00h]
0x1400bfd0e  mov     rcx, [rbp+4Fh+arg_0]
0x1400bfd12  or      r8d, 0FFFFFFFFh
0x1400bfd16  mov     rdx, r15
0x1400bfd19  mov     edi, eax
0x1400bfd1b  call    GetPriorityFromIrpEx
0x1400bfd20  mov     r8d, eax
0x1400bfd23  mov     [rsp+0F0h+var_C8], 0
0x1400bfd28  mov     r9d, edi
0x1400bfd2b  mov     byte ptr [rsp+0F0h+BugCheckParameter4], sil
0x1400bfd30  mov     dl, bl
0x1400bfd32  mov     rcx, r14
0x1400bfd35  call    FveEowUpdatePriority
0x1400bfd3a  test    al, al
0x1400bfd3c  jz      loc_1400BFE2E
0x1400bfd42  cmp     [rbp+4Fh+var_8A], r13b
0x1400bfd46  ja      loc_1400BFE2E
0x1400bfd4c  cmp     qword ptr [r12+0B0h], 0
0x1400bfd55  jz      loc_1400BFE2E
0x1400bfd5b  cmp     dword ptr [r12+0E4h], 5
0x1400bfd64  jz      loc_1400BFE2E
0x1400bfd6a  mov     edx, 30h ; '0'
0x1400bfd6f  mov     r8d, 65455646h
0x1400bfd75  lea     ecx, [rdx+10h]
0x1400bfd78  call    cs:__imp_ExAllocatePool2
0x1400bfd7f  nop     dword ptr [rax+rax+00h]
0x1400bfd84  mov     rbx, rax
0x1400bfd87  test    rax, rax
0x1400bfd8a  jz      loc_1400BFE2E
0x1400bfd90  xorps   xmm0, xmm0
0x1400bfd93  movups  xmmword ptr [rax], xmm0
0x1400bfd96  movups  xmmword ptr [rax+10h], xmm0
0x1400bfd9a  movups  xmmword ptr [rax+20h], xmm0
0x1400bfd9e  mov     [rax+28h], r13d
0x1400bfda2  mov     ecx, [r12+0E4h]
0x1400bfdaa  mov     [rax+2Ch], ecx
0x1400bfdad  mov     eax, r13d
0x1400bfdb0  mov     [r12+0E0h], ecx
0x1400bfdb8  mov     ecx, [r12+0D4h]
0x1400bfdc0  add     ecx, r13d
0x1400bfdc3  mov     [r12+0D4h], ecx
0x1400bfdcb  lea     rcx, [r12+0D0h]
0x1400bfdd3  lock xadd [rcx], eax
0x1400bfdd7  add     eax, r13d
0x1400bfdda  cmp     eax, r13d
0x1400bfddd  jle     loc_1400C02F3
  ... truncated ...
```
