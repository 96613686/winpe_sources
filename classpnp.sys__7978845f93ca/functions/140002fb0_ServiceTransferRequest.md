# ServiceTransferRequest

- ea: `0x140002fb0`
- end: `0x140003905`
- name: `ServiceTransferRequest`
- size: `2389`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400029d0`
- `0x140002d30`
- `0x14001ccb0`
- `0x1400381d0`

## callees

- `0x140001e40`
- `0x140002230`
- `0x140002844`
- `0x140002fb0`
- `0x140003910`
- `0x140004950`
- `0x140015ae0`
- `0x140016780`
- `0x140016880`
- `0x1400188b4`
- `0x14001fc38`
- `0x14001fc7c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400037ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400037f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ef92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400037ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400037f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ef92`
- `ntoskrnl!IoGetPagingIoPriority` at `0x140002fe3`
- `ntoskrnl!IoGetPagingIoPriority` at `0x140002fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003827`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ee6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f002`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003827`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ee6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f002`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400037a5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400037a5`

## pseudocode

```c
__int64 __fastcall ServiceTransferRequest(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rbp
  __int64 v5; // r14
  IO_PAGING_PRIORITY PagingIoPriority; // ecx
  __int64 v7; // rdi
  int v8; // eax
  __int64 v9; // r10
  unsigned int v10; // esi
  __int64 v11; // rbx
  __int64 v12; // r15
  _QWORD *v13; // rax
  __int64 v14; // r10
  char v15; // cl
  unsigned int v16; // r11d
  unsigned int v17; // r12d
  __int64 v18; // rbp
  unsigned int v19; // r8d
  __int64 v20; // rax
  _QWORD *v21; // rcx
  unsigned int v22; // edi
  _QWORD *v24; // rcx
  __int64 v25; // r10
  char v26; // al
  unsigned int v27; // r11d
  _QWORD *v28; // rcx
  __int64 v29; // r12
  char v30; // al
  unsigned int v31; // ebp
  unsigned int v32; // edi
  _QWORD *v33; // r14
  unsigned int v34; // ecx
  _DWORD *v35; // r12
  __int64 v36; // rdi
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rax
  _QWORD *v40; // rcx
  _DWORD *v41; // r12
  __int64 v42; // rdi
  __int64 v43; // rcx
  unsigned int v44; // eax
  __int64 v45; // rcx
  unsigned int v46; // eax
  __int64 v47; // r10
  _DWORD *v48; // r11
  __int64 v49; // r10
  __int64 v50; // rcx
  unsigned int v51; // eax
  __int64 v52; // rcx
  unsigned int v53; // eax
  __int64 v54; // r10
  __int64 v55; // rcx
  __int64 v56; // rcx
  unsigned int v57; // eax
  __int64 v58; // rcx
  unsigned int v59; // eax
  __int64 v60; // r10
  _QWORD *v61; // rcx
  char v62; // al
  _DWORD *v63; // r10
  __int64 v64; // r11
  __int64 v65; // rcx
  unsigned int v66; // eax
  __int64 v67; // r10
  __int64 v68; // rcx
  unsigned int v69; // eax
  __int64 v70; // rcx
  __int64 v71; // rcx
  unsigned int v72; // eax
  unsigned int v73; // eax
  PVOID v74; // rax
  KIRQL v75; // dl
  int v76; // eax
  KSPIN_LOCK *v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rdi
  KIRQL v81; // al
  unsigned int v82; // r8d
  unsigned int v83; // edx
  KIRQL v84; // r9
  bool v85; // zf
  __int64 v86; // rdx
  __int64 v87; // rax
  __int64 v88; // rdx
  _QWORD *v89; // [rsp+30h] [rbp-78h]
  __int64 v90; // [rsp+40h] [rbp-68h]
  __int128 v91; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v93; // [rsp+B8h] [rbp+10h]
  IO_PAGING_PRIORITY v95; // [rsp+C8h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(v3 + 1144);
  if ( (*(_DWORD *)(a2 + 16) & 2) != 0 )
    PagingIoPriority = IoGetPagingIoPriority((PIRP)a2);
  else
    PagingIoPriority = IoPagingPriorityInvalid;
  v7 = *(_QWORD *)(a2 + 184);
  v95 = PagingIoPriority;
  v90 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 384LL);
  if ( *(_BYTE *)v7 == 3 && (*(_BYTE *)(v7 + 2) & 1) != 0 && (*(_DWORD *)(v7 + 16) & 0xFFFFFE00) == 0x52434E00 )
    v8 = 1073741877;
  else
    v8 = 0;
  *(_DWORD *)(a2 + 48) = v8;
  if ( PagingIoPriority == IoPagingPriorityHigh )
  {
    v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1560));
    if ( !*(_DWORD *)(v5 + 648) )
      *(_QWORD *)(v5 + 3648) = MEMORY[0xFFFFF78000000014];
    ++*(_DWORD *)(v5 + 648);
    *(_DWORD *)(v5 + 3640) += 4;
  }
  else
  {
    if ( !*(_DWORD *)(v5 + 648) )
      goto LABEL_7;
    v75 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1560));
    if ( *(_DWORD *)(v5 + 648) )
    {
      v76 = *(_DWORD *)(v5 + 3640);
      v77 = (KSPIN_LOCK *)(v5 + 1560);
      if ( !v76 )
      {
        KeReleaseSpinLock(v77, v75);
        v18 = a1;
        goto LABEL_20;
      }
      *(_DWORD *)(v5 + 3640) = v76 - 1;
      goto LABEL_169;
    }
  }
  v77 = (KSPIN_LOCK *)(v5 + 1560);
LABEL_169:
  KeReleaseSpinLock(v77, v75);
LABEL_7:
  v9 = *(_QWORD *)(a2 + 8);
  v10 = *(_DWORD *)(v7 + 8);
  v11 = *(_QWORD *)(v7 + 24);
  v91 = 0;
  v12 = *(_QWORD *)(v9 + 32) + *(unsigned int *)(v9 + 44);
  if ( *(_QWORD *)(v5 + 672)
    && *(_DWORD *)(v3 + 168)
    && *(_BYTE *)v7 == 4
    && (*(_DWORD *)(a2 + 16) & 0x42) != 0
    && (v10 & 0xFFF) == 0 )
  {
    v74 = (*(_BYTE *)(v9 + 10) & 5) != 0
        ? *(PVOID *)(v9 + 24)
        : MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000020u);
    if ( v74 )
      ComputePageWriteHashes(v5, v11, v10, (_DWORD)v74, 1, *(_QWORD *)(a2 + 8));
  }
  if ( (v12 & 0xFFF) != 0 || *(_DWORD *)(v5 + 652) > 0xFFFFEFFF )
  {
    v13 = *(_QWORD **)(v3 + 24);
    v14 = v13[66];
    v15 = *(_BYTE *)(v14 + 24);
    if ( v15 == 19 )
    {
      v16 = *(_DWORD *)(v14 + 8);
    }
    else
    {
      v35 = (_DWORD *)v13[144];
      v36 = v13[143];
      if ( v15 == 20 || v15 == 17 )
      {
        if ( (*(_DWORD *)(v36 + 664) & 0x40) == 0 && (v35[4] & 1) != 0 && (v45 = (unsigned int)v35[16], (_DWORD)v45) )
        {
          v46 = ClasspCalculateTransferLengthInBytes(v45, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
          v16 = *(_DWORD *)(v47 + 8);
          if ( v46 < v16 )
            v16 = v46;
        }
        else
        {
          v16 = *(_DWORD *)(v14 + 8);
        }
        if ( **(_BYTE **)(a2 + 184) != 4 )
          goto LABEL_11;
      }
      else if ( (*(_DWORD *)(v36 + 664) & 0x40) == 0 && (v35[4] & 1) != 0 && (v58 = (unsigned int)v35[16], (_DWORD)v58) )
      {
        v59 = ClasspCalculateTransferLengthInBytes(v58, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
        v16 = *(_DWORD *)(v60 + 8);
        if ( v59 < v16 )
          v16 = v59;
      }
      else
      {
        v16 = *(_DWORD *)(v14 + 8);
      }
      if ( (*(_DWORD *)(v36 + 664) & 0x40) == 0 && (v35[4] & 1) != 0 )
      {
        v37 = (unsigned int)v35[17];
        if ( (_DWORD)v37 )
        {
          v38 = ClasspCalculateTransferLengthInBytes(v37, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
          if ( v16 >= v38 )
            v16 = v38;
        }
      }
    }
LABEL_11:
    v17 = *(_DWORD *)(v5 + 652);
    if ( v17 < v16 )
      goto LABEL_12;
    v61 = *(_QWORD **)(v3 + 24);
    v29 = v61[66];
    v62 = *(_BYTE *)(v29 + 24);
    if ( v62 == 19 )
    {
LABEL_28:
      v17 = *(_DWORD *)(v29 + 8);
      goto LABEL_12;
    }
    v63 = (_DWORD *)v61[144];
    v64 = v61[143];
    if ( v62 == 20 || v62 == 17 )
    {
      if ( (*(_DWORD *)(v64 + 664) & 0x40) == 0 && (v63[4] & 1) != 0 && (v71 = (unsigned int)v63[16], (_DWORD)v71) )
      {
        v72 = ClasspCalculateTransferLengthInBytes(v71, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
        v17 = *(_DWORD *)(v29 + 8);
        if ( v72 < v17 )
          v17 = v72;
      }
      else
      {
        v17 = *(_DWORD *)(v29 + 8);
      }
      if ( **(_BYTE **)(a2 + 184) != 4 )
        goto LABEL_12;
    }
    else if ( (*(_DWORD *)(v64 + 664) & 0x40) == 0 && (v63[4] & 1) != 0 && (v70 = (unsigned int)v63[16], (_DWORD)v70) )
    {
      v73 = ClasspCalculateTransferLengthInBytes(v70, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
      v17 = *(_DWORD *)(v29 + 8);
      if ( v73 < v17 )
        v17 = v73;
    }
    else
    {
      v17 = *(_DWORD *)(v29 + 8);
    }
    if ( (*(_DWORD *)(v64 + 664) & 0x40) != 0 || (v63[4] & 1) == 0 )
      goto LABEL_12;
    v55 = (unsigned int)v63[17];
    goto LABEL_171;
  }
  v24 = *(_QWORD **)(v3 + 24);
  v25 = v24[66];
  v26 = *(_BYTE *)(v25 + 24);
  if ( v26 == 19 )
  {
    v27 = *(_DWORD *)(v25 + 8);
  }
  else
  {
    v41 = (_DWORD *)v24[144];
    v42 = v24[143];
    if ( v26 == 20 || v26 == 17 )
    {
      if ( (*(_DWORD *)(v42 + 664) & 0x40) == 0 && (v41[4] & 1) != 0 && (v52 = (unsigned int)v41[16], (_DWORD)v52) )
      {
        v53 = ClasspCalculateTransferLengthInBytes(v52, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
        v27 = *(_DWORD *)(v54 + 8);
        if ( v53 < v27 )
          v27 = v53;
      }
      else
      {
        v27 = *(_DWORD *)(v25 + 8);
      }
      if ( **(_BYTE **)(a2 + 184) != 4 )
        goto LABEL_26;
    }
    else if ( (*(_DWORD *)(v42 + 664) & 0x40) == 0 && (v41[4] & 1) != 0 && (v65 = (unsigned int)v41[16], (_DWORD)v65) )
    {
      v66 = ClasspCalculateTransferLengthInBytes(v65, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
      v27 = *(_DWORD *)(v67 + 8);
      if ( v66 < v27 )
        v27 = v66;
    }
    else
    {
      v27 = *(_DWORD *)(v25 + 8);
    }
    if ( (*(_DWORD *)(v42 + 664) & 0x40) == 0 && (v41[4] & 1) != 0 )
    {
      v43 = (unsigned int)v41[17];
      if ( (_DWORD)v43 )
      {
        v44 = ClasspCalculateTransferLengthInBytes(v43, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
        if ( v27 >= v44 )
          v27 = v44;
      }
    }
  }
LABEL_26:
  v17 = *(_DWORD *)(v5 + 652) + 4096;
  if ( v17 < v27 )
    goto LABEL_12;
  v28 = *(_QWORD **)(v3 + 24);
  v29 = v28[66];
  v30 = *(_BYTE *)(v29 + 24);
  if ( v30 == 19 )
    goto LABEL_28;
  v48 = (_DWORD *)v28[144];
  v49 = v28[143];
  if ( v30 == 20 || v30 == 17 )
  {
    if ( (*(_DWORD *)(v49 + 664) & 0x40) == 0 && (v48[4] & 1) != 0 && (v56 = (unsigned int)v48[16], (_DWORD)v56) )
    {
      v57 = ClasspCalculateTransferLengthInBytes(v56, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
      v17 = *(_DWORD *)(v29 + 8);
      if ( v57 < v17 )
        v17 = v57;
    }
    else
    {
      v17 = *(_DWORD *)(v29 + 8);
    }
    if ( **(_BYTE **)(a2 + 184) == 4 && (*(_DWORD *)(v49 + 664) & 0x40) == 0 && (v48[4] & 1) != 0 )
    {
      v50 = (unsigned int)v48[17];
      if ( (_DWORD)v50 )
      {
        v51 = ClasspCalculateTransferLengthInBytes(v50, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
        if ( v17 >= v51 )
          goto LABEL_173;
      }
    }
    goto LABEL_12;
  }
  if ( (*(_DWORD *)(v49 + 664) & 0x40) == 0 && (v48[4] & 1) != 0 && (v68 = (unsigned int)v48[16], (_DWORD)v68) )
  {
    v69 = ClasspCalculateTransferLengthInBytes(v68, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
    v17 = *(_DWORD *)(v29 + 8);
    if ( v69 < v17 )
      v17 = v69;
  }
  else
  {
    v17 = *(_DWORD *)(v29 + 8);
  }
  if ( (*(_DWORD *)(v49 + 664) & 0x40) != 0 || (v48[4] & 1) == 0 )
    goto LABEL_12;
  v55 = (unsigned int)v48[17];
LABEL_171:
  if ( (_DWORD)v55 )
  {
    v51 = ClasspCalculateTransferLengthInBytes(v55, *(unsigned int *)(*(_QWORD *)(v3 + 24) + 572LL));
    if ( v17 >= v51 )
LABEL_173:
      v17 = v51;
  }
LABEL_12:
  v18 = a1;
  v19 = v10 / v17 + 1;
  if ( !(v10 % v17) )
    v19 = v10 / v17;
  v20 = v90;
  v21 = 0;
  v93 = v19;
  v22 = 0;
  v89 = 0;
  *(_QWORD *)&v91 = 0;
  if ( v90 )
  {
    v78 = DequeueFreeTransferPacket(a1);
    v19 = v93;
    if ( v78 )
    {
      v21 = (_QWORD *)(v78 + 16);
      *(_QWORD *)(v78 + 16) = 0;
      v22 = 1;
      v89 = (_QWORD *)(v78 + 16);
      *(_QWORD *)&v91 = v78 + 16;
    }
    else
    {
      v21 = 0;
    }
LABEL_160:
    v20 = v90;
  }
  else if ( v19 )
  {
    while ( 1 )
    {
      v39 = DequeueFreeTransferPacket(a1);
      if ( !v39 )
        goto LABEL_17;
      v40 = v89;
      v19 = v93;
      ++v22;
      v89 = (_QWORD *)(v39 + 16);
      *(_QWORD *)&v91 = v39 + 16;
      *(_QWORD *)(v39 + 16) = v40;
      v21 = (_QWORD *)(v39 + 16);
      if ( v22 >= v93 )
        goto LABEL_160;
    }
  }
  if ( v22 != v19 || v20 )
  {
LABEL_17:
    if ( v22 )
    {
      while ( v22 > 1 )
      {
        --v22;
        v79 = SimplePopSlist(&v91);
        EnqueueFreeTransferPacket(a1, v79 - 16);
      }
      v80 = SimplePopSlist(&v91) - 16;
      if ( !v90
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v80);
      }
      *(_QWORD *)(a2 + 56) = 0;
      *(_QWORD *)(a2 + 120) = 1;
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
      SetupReadWriteTransferPacket(v80, v12, v10, v11, a2);
      *(_BYTE *)(v80 + 209) = *(_BYTE *)(v80 + 208) == 0;
      *(_QWORD *)(v80 + 216) = v12;
      *(_DWORD *)(v80 + 224) = v10;
      *(_QWORD *)(v80 + 232) = v11;
      StepLowMemRetry((PVOID)v80);
      return 259;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a2);
    }
    if ( v95 == IoPagingPriorityHigh )
    {
      v81 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1560));
      v82 = *(_DWORD *)(v5 + 3640);
      v83 = 0;
      v84 = v81;
      if ( v82 >= 4 )
        v83 = v82 - 4;
      v85 = (*(_DWORD *)(v5 + 648))-- == 1;
      *(_DWORD *)(v5 + 3640) = v83;
      if ( v85 )
      {
        v86 = MEMORY[0xFFFFF78000000014];
        v87 = *(_QWORD *)(v5 + 3664);
        *(_QWORD *)(v5 + 3656) = MEMORY[0xFFFFF78000000014];
        v88 = v86 - *(_QWORD *)(v5 + 3648);
        if ( v87 <= v88 )
          v87 = v88;
        *(_QWORD *)(v5 + 3664) = v87;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1560), v84);
    }
LABEL_20:
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    EnqueueDeferredClientIrp(v18, a2);
    return 259;
  }
  *(_QWORD *)(a2 + 56) = 0;
  *(_QWORD *)(a2 + 120) = (int)v19;
  if ( v19 > 1 )
  {
    v31 = 259;
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  }
  else
  {
    v31 = 0;
  }
  v32 = v10;
  if ( v17 < v10 )
    v32 = v17;
  while ( v10 )
  {
    if ( v21 )
    {
      v89 = (_QWORD *)*v21;
      *v21 = 0;
    }
    v33 = v21 - 2;
    if ( v19 > 1 )
      *((_BYTE *)v33 + 296) = 1;
    SetupReadWriteTransferPacket((_DWORD)v21 - 16, v12, v32, v11, a2);
    if ( a3 )
    {
      v33[24] = 0;
      TransferPacketQueueRetryDpc(v33);
      v31 = 259;
    }
    else if ( (unsigned int)SubmitTransferPacket(v33) )
    {
      v31 = 259;
    }
    v19 = v93;
    v10 -= v32;
    v34 = v32;
    v32 = v10;
    LODWORD(v12) = v34 + v12;
    LODWORD(v11) = v34 + v11;
    v21 = v89;
    if ( v17 < v10 )
      v32 = v17;
  }
  return v31;
}

```

## disassembly

```asm
0x140002fb0  mov     [rsp+arg_10], r8b
0x140002fb5  mov     [rsp+arg_0], rcx
0x140002fba  push    rbp
0x140002fbb  push    rdi
0x140002fbc  push    r13
0x140002fbe  push    r14
0x140002fc0  sub     rsp, 88h
0x140002fc7  mov     rbp, [rcx+40h]
0x140002fcb  mov     r13, rdx
0x140002fce  mov     eax, [rdx+10h]
0x140002fd1  mov     r14, [rbp+478h]
0x140002fd8  test    al, 2
0x140002fda  jz      loc_14000338E
0x140002fe0  mov     rcx, rdx; Irp
0x140002fe3  call    cs:__imp_IoGetPagingIoPriority
0x140002fea  nop     dword ptr [rax+rax+00h]
0x140002fef  mov     ecx, eax
0x140002ff1  mov     rax, [rbp+20h]
0x140002ff5  mov     rdi, [r13+0B8h]
0x140002ffc  mov     [rsp+0A8h+arg_18], ecx
0x140003003  mov     rax, [rax+180h]
0x14000300a  cmp     byte ptr [rdi], 3
0x14000300d  mov     [rsp+0A8h+var_68], rax
0x140003012  jz      loc_14000328C
0x140003018  xor     eax, eax
0x14000301a  mov     [rsp+0A8h+var_28], rbx
0x140003022  mov     [rsp+0A8h+var_30], rsi
0x140003027  mov     [rsp+0A8h+var_38], r12
0x14000302c  mov     [rsp+0A8h+var_40], r15
0x140003031  mov     [r13+30h], eax
0x140003035  cmp     ecx, 2
0x140003038  jz      loc_1400037B3
0x14000303e  cmp     dword ptr [r14+288h], 0
0x140003046  jnz     loc_1400037ED
0x14000304c  mov     r10, [r13+8]
0x140003050  xorps   xmm0, xmm0
0x140003053  mov     esi, [rdi+8]
0x140003056  mov     rbx, [rdi+18h]
0x14000305a  movups  [rsp+0A8h+var_58], xmm0
0x14000305f  mov     r15d, [r10+2Ch]
0x140003063  add     r15, [r10+20h]
0x140003067  cmp     qword ptr [r14+2A0h], 0
0x14000306f  jnz     loc_140003840
0x140003075  test    r15, 0FFFh
0x14000307c  jz      loc_14000316D
0x140003082  mov     rax, [rbp+18h]
0x140003086  mov     r10, [rax+210h]
0x14000308d  movzx   ecx, byte ptr [r10+18h]
0x140003092  cmp     cl, 13h
0x140003095  jnz     loc_1400032B3
0x14000309b  mov     r11d, [r10+8]
0x14000309f  mov     r12d, [r14+28Ch]
0x1400030a6  cmp     r12d, r11d
0x1400030a9  jnb     loc_1400035FF
0x1400030af  mov     rbp, [rsp+0A8h+arg_0]
0x1400030b7  xor     edx, edx
0x1400030b9  mov     eax, esi
0x1400030bb  div     r12d
0x1400030be  test    edx, edx
0x1400030c0  lea     r8d, [rax+1]
0x1400030c4  cmovz   r8d, eax
0x1400030c8  mov     rax, [rsp+0A8h+var_68]
0x1400030cd  xor     ecx, ecx
0x1400030cf  mov     [rsp+0A8h+arg_8], r8d
0x1400030d7  xor     edi, edi
0x1400030d9  mov     [rsp+0A8h+var_78], rcx
0x1400030de  mov     qword ptr [rsp+0A8h+var_58], rcx
0x1400030e3  test    rax, rax
0x1400030e6  jnz     loc_140003875
0x1400030ec  test    r8d, r8d
0x1400030ef  jnz     loc_140003350
0x1400030f5  cmp     edi, r8d
0x1400030f8  jz      loc_1400031D4
0x1400030fe  cmp     edi, 1
0x140003101  jnb     loc_1400038C8
0x140003107  mov     rcx, cs:WPP_GLOBAL_Control
0x14000310e  lea     rax, WPP_GLOBAL_Control
0x140003115  cmp     rcx, rax
0x140003118  jnz     loc_1400038D3
0x14000311e  cmp     [rsp+0A8h+arg_18], 2
0x140003126  jz      loc_14003EF8B
0x14000312c  mov     rax, [r13+0B8h]
0x140003133  mov     rdx, r13
0x140003136  mov     rcx, rbp
0x140003139  or      byte ptr [rax+3], 1
0x14000313d  call    EnqueueDeferredClientIrp
0x140003142  mov     eax, 103h
0x140003147  mov     r15, [rsp+0A8h+var_40]
0x14000314c  mov     r12, [rsp+0A8h+var_38]
0x140003151  mov     rsi, [rsp+0A8h+var_30]
0x140003156  mov     rbx, [rsp+0A8h+var_28]
0x14000315e  add     rsp, 88h
0x140003165  pop     r14
0x140003167  pop     r13
0x140003169  pop     rdi
0x14000316a  pop     rbp
0x14000316b  retn
0x14000316d  cmp     dword ptr [r14+28Ch], 0FFFFEFFFh
0x140003178  ja      loc_140003082
0x14000317e  mov     rcx, [rbp+18h]
0x140003182  mov     r10, [rcx+210h]
0x140003189  movzx   eax, byte ptr [r10+18h]
0x14000318e  cmp     al, 13h
0x140003190  jnz     loc_140003395
0x140003196  mov     r11d, [r10+8]
0x14000319a  mov     r12d, [r14+28Ch]
0x1400031a1  add     r12d, 1000h
0x1400031a8  cmp     r12d, r11d
0x1400031ab  jb      loc_1400030AF
0x1400031b1  mov     rcx, [rbp+18h]
0x1400031b5  mov     r12, [rcx+210h]
0x1400031bc  movzx   eax, byte ptr [r12+18h]
0x1400031c2  cmp     al, 13h
0x1400031c4  jnz     loc_140003473
0x1400031ca  mov     r12d, [r12+8]
0x1400031cf  jmp     loc_1400030AF
0x1400031d4  test    rax, rax
0x1400031d7  jnz     loc_1400030FE
0x1400031dd  mov     [r13+38h], rax
0x1400031e1  mov     edx, 103h
0x1400031e6  movsxd  rax, r8d
0x1400031e9  mov     [r13+78h], rax
0x1400031ed  cmp     r8d, 1
0x1400031f1  ja      loc_1400035ED
0x1400031f7  xor     ebp, ebp
0x1400031f9  cmp     r12d, esi
0x1400031fc  mov     edi, esi
0x1400031fe  cmovb   edi, r12d
0x140003202  test    esi, esi
0x140003204  jz      short loc_140003285
0x140003206  mov     rax, rcx
0x140003209  test    rcx, rcx
0x14000320c  jz      short loc_14000321D
0x14000320e  mov     rcx, [rcx]
0x140003211  mov     [rsp+0A8h+var_78], rcx
0x140003216  mov     qword ptr [rax], 0
0x14000321d  lea     r14, [rax-10h]
0x140003221  cmp     r8d, 1
0x140003225  ja      loc_14000333D
0x14000322b  mov     r9, rbx
0x14000322e  mov     qword ptr [rsp+0A8h+BugCheckOnFailure], r13
0x140003233  mov     r8d, edi
0x140003236  mov     rdx, r15
0x140003239  mov     rcx, r14
0x14000323c  call    SetupReadWriteTransferPacket
0x140003241  cmp     [rsp+0A8h+arg_10], 0
0x140003249  mov     rcx, r14; DeferredContext
0x14000324c  jnz     loc_1400038AE
0x140003252  call    SubmitTransferPacket
0x140003257  test    eax, eax
0x140003259  mov     edx, 103h
0x14000325e  cmovnz  ebp, edx
0x140003261  mov     r8d, [rsp+0A8h+arg_8]
0x140003269  sub     esi, edi
0x14000326b  mov     ecx, edi
0x14000326d  mov     edi, esi
0x14000326f  add     r15, rcx
0x140003272  add     rbx, rcx
0x140003275  mov     rcx, [rsp+0A8h+var_78]
0x14000327a  cmp     r12d, esi
0x14000327d  cmovb   edi, r12d
0x140003281  test    esi, esi
0x140003283  jnz     short loc_140003206
0x140003285  mov     eax, ebp
0x140003287  jmp     loc_140003147
0x14000328c  test    byte ptr [rdi+2], 1
0x140003290  jz      loc_140003018
0x140003296  mov     eax, [rdi+10h]
0x140003299  and     eax, 0FFFFFE00h
0x14000329e  cmp     eax, 52434E00h
0x1400032a3  jnz     loc_140003018
0x1400032a9  mov     eax, 40000035h
0x1400032ae  jmp     loc_14000301A
0x1400032b3  mov     r12, [rax+480h]
0x1400032ba  mov     rdi, [rax+478h]
0x1400032c1  cmp     cl, 14h
0x1400032c4  jnz     loc_14000341E
0x1400032ca  mov     eax, [rdi+298h]
0x1400032d0  test    al, 40h
0x1400032d2  jnz     short loc_1400032E1
0x1400032d4  mov     eax, [r12+10h]
0x1400032d9  test    al, 1
0x1400032db  jnz     loc_140003447
0x1400032e1  mov     r11d, [r10+8]
0x1400032e5  mov     rax, [r13+0B8h]
0x1400032ec  cmp     byte ptr [rax], 4
0x1400032ef  jnz     loc_14000309F
0x1400032f5  mov     eax, [rdi+298h]
0x1400032fb  test    al, 40h
0x1400032fd  jnz     loc_14000309F
0x140003303  mov     eax, [r12+10h]
0x140003308  test    al, 1
0x14000330a  jz      loc_14000309F
0x140003310  mov     ecx, [r12+44h]
0x140003315  test    ecx, ecx
0x140003317  jz      loc_14000309F
0x14000331d  mov     rdx, [rbp+18h]
0x140003321  mov     edx, [rdx+23Ch]
0x140003327  call    ClasspCalculateTransferLengthInBytes
0x14000332c  cmp     r11d, eax
0x14000332f  jb      loc_14000309F
0x140003335  mov     r11d, eax
0x140003338  jmp     loc_14000309F
0x14000333d  mov     byte ptr [r14+128h], 1
0x140003345  jmp     loc_14000322B
0x140003350  mov     rcx, rbp
0x140003353  call    DequeueFreeTransferPacket
0x140003358  test    rax, rax
0x14000335b  jz      loc_1400030FE
0x140003361  mov     rcx, [rsp+0A8h+var_78]
0x140003366  add     rax, 10h
0x14000336a  mov     r8d, [rsp+0A8h+arg_8]
0x140003372  inc     edi
0x140003374  mov     [rsp+0A8h+var_78], rax
0x140003379  mov     qword ptr [rsp+0A8h+var_58], rax
0x14000337e  mov     [rax], rcx
0x140003381  mov     rcx, rax
0x140003384  cmp     edi, r8d
0x140003387  jb      short loc_140003350
0x140003389  jmp     loc_1400038A4
0x14000338e  xor     ecx, ecx
0x140003390  jmp     loc_140002FF1
0x140003395  mov     r12, [rcx+480h]
0x14000339c  mov     rdi, [rcx+478h]
0x1400033a3  cmp     al, 14h
0x1400033a5  jnz     loc_1400034F9
0x1400033ab  mov     eax, [rdi+298h]
0x1400033b1  test    al, 40h
0x1400033b3  jnz     short loc_1400033C2
0x1400033b5  mov     eax, [r12+10h]
0x1400033ba  test    al, 1
0x1400033bc  jnz     loc_140003521
0x1400033c2  mov     r11d, [r10+8]
0x1400033c6  mov     rax, [r13+0B8h]
0x1400033cd  cmp     byte ptr [rax], 4
0x1400033d0  jnz     loc_14000319A
0x1400033d6  mov     eax, [rdi+298h]
0x1400033dc  test    al, 40h
0x1400033de  jnz     loc_14000319A
0x1400033e4  mov     eax, [r12+10h]
0x1400033e9  test    al, 1
0x1400033eb  jz      loc_14000319A
0x1400033f1  mov     ecx, [r12+44h]
0x1400033f6  test    ecx, ecx
0x1400033f8  jz      loc_14000319A
0x1400033fe  mov     rdx, [rbp+18h]
0x140003402  mov     edx, [rdx+23Ch]
0x140003408  call    ClasspCalculateTransferLengthInBytes
0x14000340d  cmp     r11d, eax
0x140003410  jb      loc_14000319A
0x140003416  mov     r11d, eax
0x140003419  jmp     loc_14000319A
0x14000341e  cmp     cl, 11h
0x140003421  jz      loc_1400032CA
0x140003427  mov     eax, [rdi+298h]
0x14000342d  test    al, 40h
0x14000342f  jnz     short loc_14000343E
0x140003431  mov     eax, [r12+10h]
0x140003436  test    al, 1
0x140003438  jnz     loc_1400035C1
0x14000343e  mov     r11d, [r10+8]
0x140003442  jmp     loc_1400032F5
0x140003447  mov     ecx, [r12+40h]
0x14000344c  test    ecx, ecx
0x14000344e  jz      loc_1400032E1
0x140003454  mov     rdx, [rbp+18h]
0x140003458  mov     edx, [rdx+23Ch]
0x14000345e  call    ClasspCalculateTransferLengthInBytes
0x140003463  mov     r11d, [r10+8]
0x140003467  cmp     eax, r11d
0x14000346a  cmovb   r11d, eax
0x14000346e  jmp     loc_1400032E5
0x140003473  mov     r11, [rcx+480h]
0x14000347a  mov     r10, [rcx+478h]
0x140003481  cmp     al, 14h
0x140003483  jnz     loc_14000354D
0x140003489  mov     eax, [r10+298h]
0x140003490  test    al, 40h
0x140003492  jnz     short loc_1400034A0
0x140003494  mov     eax, [r11+10h]
0x140003498  test    al, 1
0x14000349a  jnz     loc_140003595
0x1400034a0  mov     r12d, [r12+8]
0x1400034a5  mov     rax, [r13+0B8h]
0x1400034ac  cmp     byte ptr [rax], 4
0x1400034af  jnz     loc_1400030AF
0x1400034b5  mov     eax, [r10+298h]
0x1400034bc  test    al, 40h
0x1400034be  jnz     loc_1400030AF
0x1400034c4  mov     eax, [r11+10h]
0x1400034c8  test    al, 1
0x1400034ca  jz      loc_1400030AF
0x1400034d0  mov     ecx, [r11+44h]
0x1400034d4  test    ecx, ecx
0x1400034d6  jz      loc_1400030AF
0x1400034dc  mov     rdx, [rbp+18h]
0x1400034e0  mov     edx, [rdx+23Ch]
0x1400034e6  call    ClasspCalculateTransferLengthInBytes
0x1400034eb  cmp     r12d, eax
0x1400034ee  jb      loc_1400030AF
  ... truncated ...
```
