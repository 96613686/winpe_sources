# FveEowFilterRundownReadWrite

- ea: `0x1400c3370`
- end: `0x1400c3de1`
- name: `FveEowFilterRundownReadWrite`
- size: `2673`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400291d8`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x14000bda8`
- `0x14000f624`
- `0x1400113fc`
- `0x140011578`
- `0x14002a2a0`
- `0x14002cac0`
- `0x1400c3370`
- `0x1400da8c4`
- `0x1400dab7c`
- `0x1400db940`
- `0x1400deee8`
- `0x1400df140`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400c3d15`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c3d15`
- `ntoskrnl!ObfReferenceObject` at `0x1400c386f`
- `ntoskrnl!ObfReferenceObject` at `0x1400c386f`
- `ntoskrnl!RtlAreBitsClear` at `0x1400c36c8`
- `ntoskrnl!RtlAreBitsClear` at `0x1400c36c8`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400c3772`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400c39a2`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400c3772`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400c39a2`
- `ntoskrnl!RtlAreBitsSet` at `0x1400c364a`
- `ntoskrnl!RtlAreBitsSet` at `0x1400c364a`
- `ntoskrnl!IoBoostThreadIo` at `0x1400c3cf5`
- `ntoskrnl!IoBoostThreadIo` at `0x1400c3cf5`
- `ntoskrnl!KeSetEvent` at `0x1400c3d3e`
- `ntoskrnl!KeSetEvent` at `0x1400c3d3e`
- `ntoskrnl!KeBugCheckEx` at `0x1400c3be4`
- `ntoskrnl!KeBugCheckEx` at `0x1400c3c05`
- `ntoskrnl!KeBugCheckEx` at `0x1400c3d7b`
- `ntoskrnl!KeBugCheckEx` at `0x1400c3be4`
- `ntoskrnl!KeBugCheckEx` at `0x1400c3c05`
- `ntoskrnl!KeBugCheckEx` at `0x1400c3d7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3d52`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3d52`
- `ntoskrnl!ExAllocatePool2` at `0x1400c37e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400c37e8`

## string_xrefs

- `0x1400c3467`: `Write`
- `0x1400c3ba4`: `write`

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
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(a1, a2) )
  {
    if ( (*(_BYTE *)(a1 + 4419) & 8) != 0 || (v11 = *(_QWORD *)(a1 + 976), *(_WORD *)(v11 + 10) == 1) )
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
0x1400c3370  mov     rax, rsp
0x1400c3373  mov     [rax+20h], r9
0x1400c3377  mov     [rax+18h], r8b
0x1400c337b  mov     [rax+10h], rdx
0x1400c337f  mov     [rax+8], rcx
0x1400c3383  push    rbp
0x1400c3384  push    rbx
0x1400c3385  push    rsi
0x1400c3386  push    rdi
0x1400c3387  push    r12
0x1400c3389  push    r13
0x1400c338b  push    r14
0x1400c338d  push    r15
0x1400c338f  lea     rbp, [rax-57h]
0x1400c3393  sub     rsp, 0B8h
0x1400c339a  mov     rdi, [rcx+2E0h]
0x1400c33a1  xor     r12d, r12d
0x1400c33a4  mov     [rbp+4Fh+var_84], r12d
0x1400c33a8  mov     r15, rdx
0x1400c33ab  mov     rsi, rcx
0x1400c33ae  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400c33b3  lea     r13d, [r12+1]
0x1400c33b8  test    eax, eax
0x1400c33ba  jnz     short loc_1400C33DA
0x1400c33bc  mov     rax, [rsi+3D0h]
0x1400c33c3  cmp     [rax+0Ah], r13w
0x1400c33c8  jnz     short loc_1400C33CE
0x1400c33ca  xor     ebx, ebx
0x1400c33cc  jmp     short loc_1400C3405
0x1400c33ce  mov     ebx, [rax+1Ch]
0x1400c33d1  test    ebx, ebx
0x1400c33d3  jnz     short loc_1400C3405
0x1400c33d5  mov     ebx, r13d
0x1400c33d8  jmp     short loc_1400C3405
0x1400c33da  test    byte ptr [rsi+1143h], 8
0x1400c33e1  jnz     short loc_1400C33F1
0x1400c33e3  mov     rbx, [rsi+3D0h]
0x1400c33ea  cmp     [rbx+0Ah], r13w
0x1400c33ef  jnz     short loc_1400C33F5
0x1400c33f1  xor     ebx, ebx
0x1400c33f3  jmp     short loc_1400C33FE
0x1400c33f5  mov     ebx, [rbx+1Ch]
0x1400c33f8  test    ebx, ebx
0x1400c33fa  cmovz   ebx, r13d
0x1400c33fe  mov     rax, [rsi+3D0h]
0x1400c3405  mov     r14, [rax+38h]
0x1400c3409  xorps   xmm0, xmm0
0x1400c340c  mov     rax, [rdi]
0x1400c340f  mov     esi, [rsi+51Ch]
0x1400c3415  mov     [rbp+4Fh+var_88], r12b
0x1400c3419  mov     [rbp+4Fh+var_8A], r12b
0x1400c341d  mov     cl, [rax+30h]
0x1400c3420  lea     rax, [rbp+4Fh+P]
0x1400c3424  mov     [rbp+4Fh+var_78], rax
0x1400c3428  lea     rax, [rbp+4Fh+P]
0x1400c342c  mov     [rbp+4Fh+P], rax
0x1400c3430  mov     [rbp+4Fh+var_8C], cl
0x1400c3433  movups  [rbp+4Fh+var_60], xmm0
0x1400c3437  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c343e  lea     rax, WPP_GLOBAL_Control
0x1400c3445  cmp     rcx, rax
0x1400c3448  jz      short loc_1400C348C
0x1400c344a  test    dword ptr [rcx+2Ch], 100h
0x1400c3451  jz      short loc_1400C348C
0x1400c3453  cmp     byte ptr [rcx+29h], 5
0x1400c3457  jb      short loc_1400C348C
0x1400c3459  mov     rdx, [rbp+4Fh+arg_18]
0x1400c345d  lea     r8, aRead; "Read"
0x1400c3464  mov     eax, [rbp+4Fh+arg_20]
0x1400c3467  lea     r9, aWrite_0; "Write"
0x1400c346e  mov     rcx, [rcx+18h]
0x1400c3472  add     rax, rdx
0x1400c3475  cmp     [rbp+4Fh+arg_10], r12b
0x1400c3479  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400c347e  cmovz   r9, r8
0x1400c3482  mov     [rsp+0F0h+BugCheckParameter4], rdx
0x1400c3487  call    WPP_SF_sii
0x1400c348c  cmp     [rbp+4Fh+arg_20], r12d
0x1400c3490  jz      loc_1400C3C60
0x1400c3496  mov     rdx, [rbp+4Fh+arg_18]
0x1400c349a  mov     ecx, [rbp+4Fh+arg_20]
0x1400c349d  lea     rax, [rcx+rdx]
0x1400c34a1  cmp     rax, rdx
0x1400c34a4  jb      loc_1400C3C56
0x1400c34aa  cmp     rax, [rdi+18h]
0x1400c34ae  jbe     short loc_1400C34BB
0x1400c34b0  mov     r12d, 0C000000Dh
0x1400c34b6  jmp     loc_1400C3C5C
0x1400c34bb  mov     eax, ebx
0x1400c34bd  mov     r9, rdx
0x1400c34c0  mov     r8, rsi
0x1400c34c3  mov     rdx, r14
0x1400c34c6  imul    r8, rax
0x1400c34ca  lea     rax, [rbp+4Fh+var_88]
0x1400c34ce  mov     qword ptr [rsp+0F0h+var_B0], rax
0x1400c34d3  lea     rax, [rbp+4Fh+var_8A]
0x1400c34d7  mov     [rsp+0F0h+var_B8], rax
0x1400c34dc  lea     rax, [rbp+4Fh+var_60]
0x1400c34e0  mov     [rsp+0F0h+var_C0], rax
0x1400c34e5  mov     [rsp+0F0h+BugCheckParameter4], rcx
0x1400c34ea  mov     rcx, rdi
0x1400c34ed  call    FveEowOverlappedRegionsAcquire
0x1400c34f2  mov     [rbp+4Fh+var_84], eax
0x1400c34f5  mov     r12d, eax
0x1400c34f8  test    eax, eax
0x1400c34fa  js      loc_1400C3C60
0x1400c3500  mov     sil, [rbp+4Fh+var_8C]
0x1400c3504  lea     rcx, [rbp+4Fh+var_60]
0x1400c3508  mov     r12, qword ptr [rbp+4Fh+var_60]
0x1400c350c  and     sil, 2
0x1400c3510  xor     eax, eax
0x1400c3512  mov     [rbp+4Fh+var_8C], sil
0x1400c3516  xor     bl, bl
0x1400c3518  mov     [rbp+4Fh+var_90], eax
0x1400c351b  xor     dil, dil
0x1400c351e  mov     [rbp+4Fh+var_8B], bl
0x1400c3521  mov     [rbp+4Fh+var_89], dil
0x1400c3525  cmp     r12, rcx
0x1400c3528  jnz     short loc_1400C3530
0x1400c352a  mov     [rbp+4Fh+var_68], rax
0x1400c352e  jmp     short loc_1400C353C
0x1400c3530  mov     rcx, [r12+88h]
0x1400c3538  mov     [rbp+4Fh+var_68], rcx
0x1400c353c  lea     rcx, [rbp+4Fh+var_60]
0x1400c3540  cmp     r12, rcx
0x1400c3543  jz      loc_1400C3C12
0x1400c3549  mov     r14, [r12+88h]
0x1400c3551  mov     r10d, [r12+28h]
0x1400c3556  mov     r11d, [r12+30h]
0x1400c355b  mov     [rbp+4Fh+BugCheckParameter3], r14
0x1400c355f  mov     [rbp+4Fh+var_6C], r10d
0x1400c3563  mov     [rbp+4Fh+var_70], r11d
0x1400c3567  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c356e  lea     rdx, WPP_GLOBAL_Control
0x1400c3575  cmp     rcx, rdx
0x1400c3578  jz      short loc_1400C35EA
0x1400c357a  test    dword ptr [rcx+2Ch], 100h
0x1400c3581  jz      short loc_1400C35E7
0x1400c3583  cmp     byte ptr [rcx+29h], 5
0x1400c3587  jb      short loc_1400C35E7
0x1400c3589  mov     eax, [r12+2Ch]
0x1400c358e  mov     edx, 5Fh ; '_'
0x1400c3593  mov     r9, [r14+54h]
0x1400c3597  mov     r8, [r14+5Ch]
0x1400c359b  mov     rcx, [rcx+18h]
0x1400c359f  add     r8, r9
0x1400c35a2  mov     [rsp+50h], r11d
0x1400c35a7  mov     [rsp+0F0h+var_A8], eax
0x1400c35ab  mov     rax, [r12+20h]
0x1400c35b0  mov     dword ptr [rsp+0F0h+var_B0], r10d
0x1400c35b5  mov     [rsp+0F0h+var_B8], rax
0x1400c35ba  mov     rax, [r12+18h]
0x1400c35bf  mov     [rsp+0F0h+var_C0], rax
0x1400c35c4  mov     rax, [r12+10h]
0x1400c35c9  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400c35ce  mov     [rsp+0F0h+BugCheckParameter4], r8
0x1400c35d3  call    WPP_SF_iiiiiLLL
0x1400c35d8  mov     r10d, [rbp+4Fh+var_6C]
0x1400c35dc  lea     rdx, WPP_GLOBAL_Control
0x1400c35e3  mov     r11d, [rbp+4Fh+var_70]
0x1400c35e7  mov     eax, [rbp+4Fh+var_90]
0x1400c35ea  test    sil, sil
0x1400c35ed  jnz     loc_1400C3687
0x1400c35f3  cmp     [r14+0Ch], sil
0x1400c35f7  jz      short loc_1400C3635
0x1400c35f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3600  cmp     rcx, rdx
0x1400c3603  jz      short loc_1400C362C
0x1400c3605  test    dword ptr [rcx+2Ch], 100h
0x1400c360c  jz      short loc_1400C3629
0x1400c360e  cmp     byte ptr [rcx+29h], 5
0x1400c3612  jb      short loc_1400C3629
0x1400c3614  mov     edx, 60h ; '`'
0x1400c3619  mov     rcx, [rcx+18h]
0x1400c361d  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x1400c3624  call    WPP_SF_
0x1400c3629  mov     eax, [rbp+4Fh+var_90]
0x1400c362c  mov     r12, [r12]
0x1400c3630  jmp     loc_1400C353C
0x1400c3635  mov     ecx, [r14+14h]
0x1400c3639  mov     r8d, r11d; Length
0x1400c363c  add     rcx, 5
0x1400c3640  mov     edx, r10d; StartingIndex
0x1400c3643  shl     rcx, 4
0x1400c3647  add     rcx, [r14]; BitMapHeader
0x1400c364a  call    cs:__imp_RtlAreBitsSet
0x1400c3651  nop     dword ptr [rax+rax+00h]
0x1400c3656  test    al, al
0x1400c3658  jz      loc_1400C3710
0x1400c365e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3665  lea     r9, WPP_GLOBAL_Control
0x1400c366c  cmp     rcx, r9
0x1400c366f  jz      short loc_1400C3629
0x1400c3671  test    dword ptr [rcx+2Ch], 100h
0x1400c3678  jz      short loc_1400C3629
0x1400c367a  cmp     byte ptr [rcx+29h], 5
0x1400c367e  jb      short loc_1400C3629
0x1400c3680  mov     edx, 62h ; 'b'
0x1400c3685  jmp     short loc_1400C3619
0x1400c3687  cmp     byte ptr [r14+0Dh], 0
0x1400c368c  jz      short loc_1400C36B3
0x1400c368e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c3695  cmp     rcx, rdx
0x1400c3698  jz      short loc_1400C362C
0x1400c369a  test    dword ptr [rcx+2Ch], 100h
0x1400c36a1  jz      short loc_1400C3629
0x1400c36a3  cmp     byte ptr [rcx+29h], 5
0x1400c36a7  jb      short loc_1400C3629
0x1400c36a9  mov     edx, 61h ; 'a'
0x1400c36ae  jmp     loc_1400C3619
0x1400c36b3  mov     ecx, [r14+14h]
0x1400c36b7  mov     r8d, r11d; Length
0x1400c36ba  add     rcx, 5
0x1400c36be  mov     edx, r10d; StartingIndex
0x1400c36c1  shl     rcx, 4
0x1400c36c5  add     rcx, [r14]; BitMapHeader
0x1400c36c8  call    cs:__imp_RtlAreBitsClear
0x1400c36cf  nop     dword ptr [rax+rax+00h]
0x1400c36d4  test    al, al
0x1400c36d6  jz      short loc_1400C3710
0x1400c36d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c36df  lea     r9, WPP_GLOBAL_Control
0x1400c36e6  cmp     rcx, r9
0x1400c36e9  jz      loc_1400C3629
0x1400c36ef  test    dword ptr [rcx+2Ch], 100h
0x1400c36f6  jz      loc_1400C3629
0x1400c36fc  cmp     byte ptr [rcx+29h], 5
0x1400c3700  jb      loc_1400C3629
0x1400c3706  mov     edx, 63h ; 'c'
0x1400c370b  jmp     loc_1400C3619
0x1400c3710  cmp     dword ptr [r12+40h], 0
0x1400c3716  jz      loc_1400C38F2
0x1400c371c  test    dil, dil
0x1400c371f  jnz     loc_1400C3629
0x1400c3725  test    bl, bl
0x1400c3727  jnz     loc_1400C3629
0x1400c372d  lea     rcx, [r12+70h]
0x1400c3732  mov     rdx, [rcx+8]
0x1400c3736  cmp     [rdx], rcx
0x1400c3739  jnz     loc_1400C3D88
0x1400c373f  mov     r9d, [rbp+4Fh+arg_20]
0x1400c3743  lea     rax, [r15+0A8h]
0x1400c374a  mov     r8, [rbp+4Fh+arg_18]
0x1400c374e  mov     [rax], rcx
0x1400c3751  mov     [rax+8], rdx
0x1400c3755  mov     [rdx], rax
0x1400c3758  mov     rdx, r15
0x1400c375b  mov     [rcx+8], rax
0x1400c375f  mov     rcx, [rbp+4Fh+arg_0]
0x1400c3763  mov     rbx, [r15+78h]
0x1400c3767  call    FveIsPagingRequest
0x1400c376c  mov     rcx, r15; Irp
0x1400c376f  mov     sil, al
0x1400c3772  call    cs:__imp_IoGetIoPriorityHint
0x1400c3779  nop     dword ptr [rax+rax+00h]
0x1400c377e  mov     rcx, [rbp+4Fh+arg_0]
0x1400c3782  or      r8d, 0FFFFFFFFh
0x1400c3786  mov     rdx, r15
0x1400c3789  mov     edi, eax
0x1400c378b  call    GetPriorityFromIrpEx
0x1400c3790  mov     r8d, eax
0x1400c3793  mov     [rsp+0F0h+var_C8], 0
0x1400c3798  mov     r9d, edi
0x1400c379b  mov     byte ptr [rsp+0F0h+BugCheckParameter4], sil
0x1400c37a0  mov     dl, bl
0x1400c37a2  mov     rcx, r14
0x1400c37a5  call    FveEowUpdatePriority
0x1400c37aa  test    al, al
0x1400c37ac  jz      loc_1400C389E
0x1400c37b2  cmp     [rbp+4Fh+var_8A], r13b
0x1400c37b6  ja      loc_1400C389E
0x1400c37bc  cmp     qword ptr [r12+0B0h], 0
0x1400c37c5  jz      loc_1400C389E
0x1400c37cb  cmp     dword ptr [r12+0E4h], 5
0x1400c37d4  jz      loc_1400C389E
0x1400c37da  mov     edx, 30h ; '0'
0x1400c37df  mov     r8d, 65455646h
0x1400c37e5  lea     ecx, [rdx+10h]
0x1400c37e8  call    cs:__imp_ExAllocatePool2
0x1400c37ef  nop     dword ptr [rax+rax+00h]
0x1400c37f4  mov     rbx, rax
0x1400c37f7  test    rax, rax
0x1400c37fa  jz      loc_1400C389E
0x1400c3800  xorps   xmm0, xmm0
0x1400c3803  movups  xmmword ptr [rax], xmm0
0x1400c3806  movups  xmmword ptr [rax+10h], xmm0
0x1400c380a  movups  xmmword ptr [rax+20h], xmm0
0x1400c380e  mov     [rax+28h], r13d
0x1400c3812  mov     ecx, [r12+0E4h]
0x1400c381a  mov     [rax+2Ch], ecx
0x1400c381d  mov     eax, r13d
0x1400c3820  mov     [r12+0E0h], ecx
0x1400c3828  mov     ecx, [r12+0D4h]
0x1400c3830  add     ecx, r13d
0x1400c3833  mov     [r12+0D4h], ecx
0x1400c383b  lea     rcx, [r12+0D0h]
0x1400c3843  lock xadd [rcx], eax
0x1400c3847  add     eax, r13d
0x1400c384a  cmp     eax, r13d
0x1400c384d  jle     loc_1400C3D63
  ... truncated ...
```
