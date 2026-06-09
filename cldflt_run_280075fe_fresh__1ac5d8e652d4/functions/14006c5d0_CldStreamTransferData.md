# CldStreamTransferData

- ea: `0x14006c5d0`
- end: `0x14006d070`
- name: `CldStreamTransferData`
- size: `2720`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG Length, PVOID VirtualAddress)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14006c058`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140010808`
- `0x140010890`
- `0x140010a28`
- `0x140010a98`
- `0x140010b20`
- `0x14001e280`
- `0x1400344a8`
- `0x14005fcc4`
- `0x14006c5d0`
- `0x14006d078`
- `0x14006d410`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c910`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c910`
- `ntoskrnl!IoFreeMdl` at `0x14006c86f`
- `ntoskrnl!IoFreeMdl` at `0x14006ca1a`
- `ntoskrnl!IoFreeMdl` at `0x14006c86f`
- `ntoskrnl!IoFreeMdl` at `0x14006ca1a`
- `ntoskrnl!IoAllocateMdl` at `0x14006c75b`
- `ntoskrnl!IoAllocateMdl` at `0x14006c75b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c7d7`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c7d7`
- `ntoskrnl!MmUnlockPages` at `0x14006ca01`
- `ntoskrnl!MmUnlockPages` at `0x14006ca01`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006cf9c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006cf9c`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006cde4`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006cde4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce52`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce52`
- `ntoskrnl!ExAllocatePool2` at `0x14006cf21`
- `ntoskrnl!ExAllocatePool2` at `0x14006cf21`
- `FLTMGR!FltReleasePushLockEx` at `0x14006c9eb`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cbc3`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cdd4`
- `FLTMGR!FltReleasePushLockEx` at `0x14006ce39`
- `FLTMGR!FltReleasePushLockEx` at `0x14006ce92`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cfff`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d058`
- `FLTMGR!FltReleasePushLockEx` at `0x14006c9eb`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cbc3`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cdd4`
- `FLTMGR!FltReleasePushLockEx` at `0x14006ce39`
- `FLTMGR!FltReleasePushLockEx` at `0x14006ce92`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cfff`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d058`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006c997`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cb85`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cd26`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cdfb`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006ce6a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cfd2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d015`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006c997`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cb85`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cd26`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cdfb`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006ce6a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cfd2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d015`

## pseudocode

```c
__int64 __fastcall CldStreamTransferData(
        volatile signed __int32 *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 Length,
        PVOID VirtualAddress)
{
  _QWORD *v9; // r8
  __int64 v10; // r13
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdi
  void *v15; // r12
  struct _MDL *v16; // rcx
  __int64 v17; // rdx
  PVOID v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v22; // r8
  __int16 SyncPolicy; // ax
  _QWORD *v24; // rdi
  __int64 v25; // rdx
  char v26; // cl
  __int128 v27; // rax
  int v28; // r8d
  __int64 v29; // rdx
  __int64 v30; // r8
  struct _EX_RUNDOWN_REF *v31; // rdi
  char v32; // cl
  __int64 *v33; // rax
  char v34; // di
  _QWORD *Count; // rax
  PVOID *v36; // rcx
  ULONG_PTR v37; // r14
  struct _EX_RUNDOWN_REF *v38; // rax
  ULONG_PTR v39; // r8
  struct _EX_RUNDOWN_REF **v40; // rdx
  __int64 v41; // r8
  PDEVICE_OBJECT v42; // rcx
  __int64 v43; // rdx
  struct _EX_RUNDOWN_REF *Pool2; // rax
  __int64 v45; // rdi
  struct _EX_RUNDOWN_REF *v46; // r14
  struct _EX_RUNDOWN_REF **v47; // rdx
  __int64 *v48; // rax
  void *Src; // [rsp+50h] [rbp-E8h]
  int v50; // [rsp+58h] [rbp-E0h]
  PMDL MemoryDescriptorList; // [rsp+60h] [rbp-D8h]
  __int64 v52; // [rsp+68h] [rbp-D0h]
  __int128 v53; // [rsp+70h] [rbp-C8h] BYREF
  __int128 v54; // [rsp+80h] [rbp-B8h]
  __int64 v55; // [rsp+90h] [rbp-A8h]
  __int64 v56; // [rsp+A0h] [rbp-98h]
  _QWORD *v57; // [rsp+A8h] [rbp-90h]
  __int64 v58; // [rsp+B0h] [rbp-88h]
  __int64 v59; // [rsp+B8h] [rbp-80h]
  __int64 v60; // [rsp+C0h] [rbp-78h]
  PMDL Mdl; // [rsp+C8h] [rbp-70h]
  _QWORD *v62; // [rsp+D8h] [rbp-60h]
  __int64 v63; // [rsp+E0h] [rbp-58h]
  __int64 v64; // [rsp+E8h] [rbp-50h]
  __int64 v65; // [rsp+F0h] [rbp-48h]
  char v66; // [rsp+148h] [rbp+10h]
  char IsValidationRequired; // [rsp+158h] [rbp+20h]
  char VirtualAddressa; // [rsp+168h] [rbp+30h]

  v53 = 0;
  v54 = 0;
  v55 = 0;
  v9 = *(_QWORD **)a1;
  v57 = v9;
  v62 = v9;
  v10 = *(_QWORD *)(*(_QWORD *)(*v9 + 16LL) + 32LL);
  v63 = v10;
  v11 = Length;
  if ( Length == -1 )
    v11 = 0x7FFFFFFFFFFFFFFFLL - a4;
  v56 = v11;
  MemoryDescriptorList = 0;
  Src = 0;
  v66 = 0;
  if ( VirtualAddress && v11 > 0xFFFFFFFFLL || (v52 = v11 + a4, v11 + a4 <= a4) )
  {
    v50 = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_iiiqd(WPP_GLOBAL_Control->AttachedDevice, v12, v13, v10, a4, v11, VirtualAddress, a3);
      LODWORD(v14) = -1073688821;
      v15 = 0;
      goto LABEL_29;
    }
    goto LABEL_27;
  }
  v58 = v10;
  v50 = 0;
  v60 = v9[1];
  v64 = v60;
  v59 = v9[2];
  v65 = v59;
  if ( a3 >= 0 )
  {
    v16 = IoAllocateMdl(VirtualAddress, v11, 0, 0, 0);
    MemoryDescriptorList = v16;
    Mdl = v16;
    if ( !v16 )
    {
      a3 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_iDqd(WPP_GLOBAL_Control->AttachedDevice, v17, v9, v10, v11, VirtualAddress);
      }
      v16 = 0;
    }
    if ( v16 )
    {
      MmProbeAndLockPages(v16, 1, IoReadAccess);
      if ( MemoryDescriptorList )
      {
        v18 = (MemoryDescriptorList->MdlFlags & 5) != 0
            ? MemoryDescriptorList->MappedSystemVa
            : MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
        Src = v18;
        if ( !v18 )
        {
          HsmDbgBreakOnStatus(3221225626LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
              v10,
              v11,
              VirtualAddress,
              -1073741670);
          }
LABEL_27:
          LODWORD(v14) = v50;
LABEL_28:
          v15 = Src;
          goto LABEL_29;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_iqiiqd(
      WPP_GLOBAL_Control->AttachedDevice,
      &WPP_GLOBAL_Control,
      v9,
      v10,
      *(_QWORD *)a1,
      a4,
      v11,
      VirtualAddress,
      a3);
  }
  IsValidationRequired = CldSyncIsValidationRequired(*(_QWORD *)(v59 + 32));
  SyncPolicy = CldHsmGetSyncPolicy(v22, 1);
  v24 = v57;
  if ( (SyncPolicy & 0x200) != 0 )
  {
    v25 = *v57;
    if ( *(_QWORD *)(*v57 + 160LL) )
    {
      if ( *(_DWORD *)(v25 + 72) && *(_DWORD *)(v25 + 72) <= *(_DWORD *)(*(_QWORD *)(v25 + 160) + 48LL) )
        goto LABEL_49;
      v26 = 1;
    }
    else
    {
      v26 = 0;
    }
    if ( !v26 )
    {
LABEL_49:
      VirtualAddressa = 1;
      goto LABEL_51;
    }
  }
  VirtualAddressa = 0;
LABEL_51:
  if ( a3 < 0 )
  {
    v15 = Src;
    CldiStreamProcessPendingHydrationRequests((_DWORD)a1, v10, 4, a3, a4, v11, (__int64)Src);
LABEL_53:
    LODWORD(v14) = 0;
    goto LABEL_29;
  }
  if ( !IsValidationRequired && (SyncPolicy & 0xFu) < 3 )
  {
    *((_QWORD *)&v53 + 1) = &v53;
    *(_QWORD *)&v53 = &v53;
    *(_QWORD *)&v54 = Src;
    *((_QWORD *)&v54 + 1) = a4;
    LODWORD(v55) = v11;
    FltAcquirePushLockExclusiveEx(a1 + 8, 0);
    *(_QWORD *)&v27 = a1 + 18;
    *((_QWORD *)&v27 + 1) = *((_QWORD *)a1 + 10);
    if ( **((volatile signed __int32 ***)&v27 + 1) != a1 + 18 )
      goto LABEL_103;
    v53 = v27;
    **((_QWORD **)&v27 + 1) = &v53;
    *(_QWORD *)(v27 + 8) = &v53;
    FltReleasePushLockEx(a1 + 8, 0);
    v66 = 1;
  }
  CldiStreamProcessPendingHydrationRequests((_DWORD)a1, v10, 1, a3, a4, v11, (__int64)Src);
  if ( *(_BYTE *)(*(_QWORD *)v60 + 24LL) || VirtualAddressa )
  {
    FltAcquirePushLockExclusiveEx(&qword_140028828, 0);
    qword_140028858 += v11;
    while ( qword_140028858 + qword_140028850 > qword_140028860 )
    {
      v31 = (struct _EX_RUNDOWN_REF *)qword_140028840;
      if ( (__int64 *)qword_140028840 == &qword_140028840 )
      {
        v32 = 1;
        v31 = (struct _EX_RUNDOWN_REF *)qword_140028830;
      }
      else
      {
        v32 = 0;
      }
      v33 = (__int64 *)&qword_140028830;
      if ( !v32 )
        v33 = &qword_140028840;
      if ( v31 == (struct _EX_RUNDOWN_REF *)v33 )
      {
        if ( v33 != &qword_140028840 )
        {
          v34 = 0;
          goto LABEL_87;
        }
      }
      else
      {
        Count = (_QWORD *)v31->Count;
        if ( *(struct _EX_RUNDOWN_REF **)(v31->Count + 8) != v31 )
          goto LABEL_103;
        v36 = (PVOID *)v31[1].Count;
        if ( *v36 != v31 )
          goto LABEL_103;
        v37 = v31[6].Count;
        *v36 = Count;
        Count[1] = v36;
        v31[1].Count = (ULONG_PTR)v31;
        v31->Count = (ULONG_PTR)v31;
        qword_140028850 -= LODWORD(v31[8].Count);
        FltReleasePushLockEx(&qword_140028828, 0);
        ExWaitForRundownProtectionRelease(v31 + 5);
        _InterlockedIncrement((volatile signed __int32 *)(v37 + 112));
        FltAcquirePushLockExclusiveEx(v37 + 88, 0);
        v38 = v31 + 2;
        v39 = v31[2].Count;
        if ( *(struct _EX_RUNDOWN_REF **)(v39 + 8) != &v31[2] )
          goto LABEL_103;
        v40 = (struct _EX_RUNDOWN_REF **)v31[3].Count;
        if ( *v40 != v38 )
          goto LABEL_103;
        *v40 = (struct _EX_RUNDOWN_REF *)v39;
        *(_QWORD *)(v39 + 8) = v40;
        v31[3].Count = (ULONG_PTR)&v31[2];
        v38->Count = (ULONG_PTR)v38;
        FltReleasePushLockEx(v37 + 88, 0);
        _InterlockedDecrement((volatile signed __int32 *)(v37 + 112));
        ExFreePoolWithTag(v31, 0x62636C43u);
        FltAcquirePushLockExclusiveEx(&qword_140028828, 0);
      }
    }
    v34 = 1;
LABEL_87:
    if ( !v34 )
      qword_140028858 -= v11;
    FltReleasePushLockEx(&qword_140028828, 0);
    if ( v34 )
    {
      Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(256, (unsigned int)(v11 + 68), 1650682947);
      v45 = (__int64)Pool2;
      if ( Pool2 )
      {
        Pool2[1].Count = (ULONG_PTR)Pool2;
        Pool2->Count = (ULONG_PTR)Pool2;
        v46 = Pool2 + 2;
        Pool2[3].Count = (ULONG_PTR)&Pool2[2];
        Pool2[2].Count = (ULONG_PTR)&Pool2[2];
        Pool2[4].Count = MEMORY[0xFFFFF78000000014];
        ExInitializeRundownProtection(Pool2 + 5);
        *(_QWORD *)(v45 + 48) = a1;
        *(_QWORD *)(v45 + 56) = a4;
        *(_DWORD *)(v45 + 64) = v11;
        v15 = Src;
        memmove((void *)(v45 + 68), Src, (unsigned int)v11);
        _InterlockedIncrement(a1 + 28);
        FltAcquirePushLockExclusiveEx(a1 + 22, 0);
        v47 = (struct _EX_RUNDOWN_REF **)*((_QWORD *)a1 + 13);
        if ( *v47 != (struct _EX_RUNDOWN_REF *)(a1 + 24) )
          goto LABEL_103;
        v46->Count = (ULONG_PTR)(a1 + 24);
        v46[1].Count = (ULONG_PTR)v47;
        *v47 = v46;
        *((_QWORD *)a1 + 13) = v46;
        FltReleasePushLockEx(a1 + 22, 0);
        _InterlockedDecrement(a1 + 28);
        FltAcquirePushLockExclusiveEx(&qword_140028828, 0);
        qword_140028850 += v11;
        qword_140028858 -= v11;
        v48 = (__int64 *)qword_140028838;
        if ( *(PVOID **)qword_140028838 != &qword_140028830 )
          goto LABEL_103;
        *(_QWORD *)v45 = &qword_140028830;
        *(_QWORD *)(v45 + 8) = v48;
        *v48 = v45;
        qword_140028838 = v45;
        FltReleasePushLockEx(&qword_140028828, 0);
        goto LABEL_53;
      }
      LODWORD(v14) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_28;
      }
      v43 = 46;
    }
    else
    {
      LODWORD(v14) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_28;
      }
      v43 = 45;
    }
    WPP_SF_iqiid(v42->AttachedDevice, v43, v41, v58, *(_QWORD *)a1, a4, v52, -1073741670);
    goto LABEL_28;
  }
  v15 = Src;
  LOBYTE(v28) = IsValidationRequired;
  v14 = (unsigned int)HsmRecallTransferData(*(_QWORD *)v60, *v24, v28, a4, v11, (__int64)Src);
  HsmDbgBreakOnStatus(v14);
  if ( (int)v14 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_iqii(WPP_GLOBAL_Control->AttachedDevice, v29, v30, v10, *(_QWORD *)a1, a4, v52);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_iqiid(WPP_GLOBAL_Control->AttachedDevice, 43, v30, v10, *(_QWORD *)a1, a4, v52, v14);
    }
    a3 = v14;
  }
  CldiStreamProcessPendingHydrationRequests((_DWORD)a1, v10, 2, a3, a4, v11, 0);
LABEL_29:
  if ( !v66 )
    goto LABEL_33;
  FltAcquirePushLockExclusiveEx(a1 + 8, 0);
  v19 = v53;
  if ( *(__int128 **)(v53 + 8) != &v53 || (v20 = *((_QWORD *)&v53 + 1), **((__int128 ***)&v53 + 1) != &v53) )
LABEL_103:
    __fastfail(3u);
  **((_QWORD **)&v53 + 1) = v53;
  *(_QWORD *)(v19 + 8) = v20;
  *((_QWORD *)&v53 + 1) = &v53;
  *(_QWORD *)&v53 = &v53;
  FltReleasePushLockEx(a1 + 8, 0);
LABEL_33:
  if ( v15 )
    MmUnlockPages(MemoryDescriptorList);
  if ( MemoryDescriptorList )
    IoFreeMdl(MemoryDescriptorList);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14006c5d0  mov     r11, rsp
0x14006c5d3  mov     [r11+20h], r9
0x14006c5d7  mov     [r11+10h], rdx
0x14006c5db  mov     [r11+8], rcx
0x14006c5df  push    rbx
0x14006c5e0  push    rsi
0x14006c5e1  push    rdi
0x14006c5e2  push    r12
0x14006c5e4  push    r13
0x14006c5e6  push    r14
0x14006c5e8  push    r15
0x14006c5ea  sub     rsp, 100h
0x14006c5f1  mov     rsi, r9
0x14006c5f4  mov     r14d, r8d
0x14006c5f7  mov     r15, rcx
0x14006c5fa  xorps   xmm0, xmm0
0x14006c5fd  xor     eax, eax
0x14006c5ff  movups  [rsp+138h+var_C8], xmm0
0x14006c604  movups  [rsp+138h+var_B8], xmm0
0x14006c60c  mov     [r11-0A8h], rax
0x14006c613  mov     r8, [rcx]
0x14006c616  mov     [rsp+138h+var_90], r8
0x14006c61e  mov     [rsp+138h+var_60], r8
0x14006c626  mov     rax, [r8]
0x14006c629  mov     rdx, [rax+10h]
0x14006c62d  mov     r13, [rdx+20h]
0x14006c631  mov     [rsp+138h+var_58], r13
0x14006c639  mov     rbx, [rsp+138h+Length]
0x14006c641  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006c645  jnz     short loc_14006C654
0x14006c647  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14006c651  sub     rbx, r9
0x14006c654  mov     [rsp+138h+var_98], rbx
0x14006c65c  mov     [rsp+138h+MemoryDescriptorList], 0
0x14006c665  xor     r9d, r9d
0x14006c668  mov     [rsp+138h+Src], r9
0x14006c66d  xor     r10b, r10b
0x14006c670  mov     [rsp+138h+arg_8], r10b
0x14006c678  mov     rdi, [rsp+138h+VirtualAddress]
0x14006c680  test    rdi, rdi
0x14006c683  jz      short loc_14006C68F
0x14006c685  mov     eax, 0FFFFFFFFh
0x14006c68a  cmp     rbx, rax
0x14006c68d  jg      short loc_14006C69D
0x14006c68f  lea     rax, [rbx+rsi]
0x14006c693  mov     [rsp+138h+var_D0], rax
0x14006c698  cmp     rax, rsi
0x14006c69b  jg      short loc_14006C708
0x14006c69d  mov     eax, 0C000CF0Bh
0x14006c6a2  mov     [rsp+138h+var_E0], eax
0x14006c6a6  mov     ecx, eax
0x14006c6a8  call    HsmDbgBreakOnStatus
0x14006c6ad  lea     rax, WPP_GLOBAL_Control
0x14006c6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c6bb  cmp     rcx, rax
0x14006c6be  jz      loc_14006C97E
0x14006c6c4  test    dword ptr [rcx+2Ch], 100h
0x14006c6cb  jz      loc_14006C97E
0x14006c6d1  cmp     byte ptr [rcx+29h], 2
0x14006c6d5  jb      loc_14006C97E
0x14006c6db  mov     dword ptr [rsp+138h+var_100], r14d
0x14006c6e0  mov     [rsp+138h+var_108], rdi
0x14006c6e5  mov     qword ptr [rsp+138h+Priority], rbx
0x14006c6ea  mov     [rsp+138h+Irp], rsi
0x14006c6ef  mov     r9, r13
0x14006c6f2  mov     rcx, [rcx+18h]
0x14006c6f6  call    WPP_SF_iiiqd
0x14006c6fb  mov     edi, 0C000CF0Bh
0x14006c700  xor     r12d, r12d
0x14006c703  jmp     loc_14006C987
0x14006c708  mov     [rsp+138h+var_88], r13
0x14006c710  xor     eax, eax
0x14006c712  mov     [rsp+138h+var_E0], eax
0x14006c716  mov     r9, [r8+8]
0x14006c71a  mov     [rsp+138h+var_78], r9
0x14006c722  mov     [rsp+138h+var_50], r9
0x14006c72a  mov     rax, [r8+10h]
0x14006c72e  mov     [rsp+138h+var_80], rax
0x14006c736  mov     [rsp+138h+var_48], rax
0x14006c73e  test    r14d, r14d
0x14006c741  js      loc_14006CA3C
0x14006c747  mov     [rsp+138h+Irp], 0; Irp
0x14006c750  xor     r9d, r9d; ChargeQuota
0x14006c753  xor     r8d, r8d; SecondaryBuffer
0x14006c756  mov     edx, ebx; Length
0x14006c758  mov     rcx, rdi; VirtualAddress
0x14006c75b  call    cs:__imp_IoAllocateMdl
0x14006c762  nop     dword ptr [rax+rax+00h]
0x14006c767  mov     rcx, rax
0x14006c76a  mov     [rsp+138h+MemoryDescriptorList], rax
0x14006c76f  mov     [rsp+138h+Mdl], rax
0x14006c777  mov     r12d, 0C000009Ah
0x14006c77d  test    rax, rax
0x14006c780  jnz     short loc_14006C7C9
0x14006c782  mov     r14d, r12d
0x14006c785  mov     ecx, r12d
0x14006c788  call    HsmDbgBreakOnStatus
0x14006c78d  lea     rax, WPP_GLOBAL_Control
0x14006c794  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c79b  cmp     rcx, rax
0x14006c79e  jz      short loc_14006C7C4
0x14006c7a0  test    dword ptr [rcx+2Ch], 100h
0x14006c7a7  jz      short loc_14006C7C4
0x14006c7a9  cmp     byte ptr [rcx+29h], 2
0x14006c7ad  jb      short loc_14006C7C4
0x14006c7af  mov     qword ptr [rsp+138h+Priority], rdi
0x14006c7b4  mov     dword ptr [rsp+138h+Irp], ebx
0x14006c7b8  mov     r9, r13
0x14006c7bb  mov     rcx, [rcx+18h]
0x14006c7bf  call    WPP_SF_iDqd
0x14006c7c4  mov     rcx, [rsp+138h+MemoryDescriptorList]; MemoryDescriptorList
0x14006c7c9  test    rcx, rcx
0x14006c7cc  jz      loc_14006CA42
0x14006c7d2  xor     r8d, r8d; Operation
0x14006c7d5  mov     dl, 1; AccessMode
0x14006c7d7  call    cs:__imp_MmProbeAndLockPages
0x14006c7de  nop     dword ptr [rax+rax+00h]
0x14006c7e3  mov     rcx, [rsp+138h+MemoryDescriptorList]
0x14006c7e8  jmp     loc_14006C8E2
0x14006c7ed  mov     r14d, eax
0x14006c7f0  mov     ecx, eax
0x14006c7f2  call    HsmDbgBreakOnStatus
0x14006c7f7  lea     rax, WPP_GLOBAL_Control
0x14006c7fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c805  cmp     rcx, rax
0x14006c808  jz      short loc_14006C857
0x14006c80a  test    dword ptr [rcx+2Ch], 100h
0x14006c811  jz      short loc_14006C857
0x14006c813  cmp     byte ptr [rcx+29h], 2
0x14006c817  jb      short loc_14006C857
0x14006c819  mov     edx, 28h ; '('
0x14006c81e  mov     dword ptr [rsp+138h+var_108], r14d
0x14006c823  mov     rdi, [rsp+138h+VirtualAddress]
0x14006c82b  mov     qword ptr [rsp+138h+Priority], rdi
0x14006c830  mov     rbx, [rsp+138h+var_98]
0x14006c838  mov     [rsp+138h+Irp], rbx
0x14006c83d  mov     r9, [rsp+138h+var_88]
0x14006c845  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006c84c  mov     rcx, [rcx+18h]
0x14006c850  call    WPP_SF_qqqd
0x14006c855  jmp     short loc_14006C867
0x14006c857  mov     rdi, [rsp+138h+VirtualAddress]
0x14006c85f  mov     rbx, [rsp+138h+var_98]
0x14006c867  mov     rcx, [rsp+138h+Mdl]; Mdl
0x14006c86f  call    cs:__imp_IoFreeMdl
0x14006c876  nop     dword ptr [rax+rax+00h]
0x14006c87b  xor     ecx, ecx; MemoryDescriptorList
0x14006c87d  mov     [rsp+138h+MemoryDescriptorList], rcx
0x14006c882  mov     r12d, 0C000009Ah
0x14006c888  mov     rsi, [rsp+138h+arg_18]
0x14006c890  mov     r15, [rsp+138h+arg_0]
0x14006c898  mov     eax, ecx
0x14006c89a  mov     [rsp+138h+var_E0], ecx
0x14006c89e  mov     [rsp+138h+Src], rax
0x14006c8a3  mov     [rsp+138h+arg_8], al
0x14006c8aa  mov     rax, [rsp+138h+var_60]
0x14006c8b2  mov     [rsp+138h+var_90], rax
0x14006c8ba  mov     r13, [rsp+138h+var_58]
0x14006c8c2  mov     rax, [rsp+138h+var_50]
0x14006c8ca  mov     [rsp+138h+var_78], rax
0x14006c8d2  mov     rax, [rsp+138h+var_48]
0x14006c8da  mov     [rsp+138h+var_80], rax
0x14006c8e2  test    rcx, rcx
0x14006c8e5  jz      loc_14006CA42
0x14006c8eb  test    byte ptr [rcx+0Ah], 5
0x14006c8ef  jz      short loc_14006C8F7
0x14006c8f1  mov     r9, [rcx+18h]
0x14006c8f5  jmp     short loc_14006C91F
0x14006c8f7  mov     [rsp+138h+Priority], 40000010h; Priority
0x14006c8ff  mov     dword ptr [rsp+138h+Irp], 0; BugCheckOnFailure
0x14006c907  xor     r9d, r9d; RequestedAddress
0x14006c90a  xor     edx, edx; AccessMode
0x14006c90c  lea     r8d, [r9+1]; CacheType
0x14006c910  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006c917  nop     dword ptr [rax+rax+00h]
0x14006c91c  mov     r9, rax
0x14006c91f  mov     [rsp+138h+Src], r9
0x14006c924  test    r9, r9
0x14006c927  jnz     loc_14006CA42
0x14006c92d  mov     ecx, r12d
0x14006c930  call    HsmDbgBreakOnStatus
0x14006c935  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c93c  lea     rdx, WPP_GLOBAL_Control
0x14006c943  cmp     rcx, rdx
0x14006c946  jz      short loc_14006C97E
0x14006c948  test    dword ptr [rcx+2Ch], 100h
0x14006c94f  jz      short loc_14006C97E
0x14006c951  cmp     byte ptr [rcx+29h], 2
0x14006c955  jb      short loc_14006C97E
0x14006c957  mov     edx, 29h ; ')'
0x14006c95c  mov     dword ptr [rsp+138h+var_108], r12d
0x14006c961  mov     qword ptr [rsp+138h+Priority], rdi
0x14006c966  mov     [rsp+138h+Irp], rbx
0x14006c96b  mov     r9, r13
0x14006c96e  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006c975  mov     rcx, [rcx+18h]
0x14006c979  call    WPP_SF_qqqd
0x14006c97e  mov     edi, [rsp+138h+var_E0]
0x14006c982  mov     r12, [rsp+138h+Src]
0x14006c987  cmp     [rsp+138h+arg_8], 0
0x14006c98f  jz      short loc_14006C9F7
0x14006c991  xor     edx, edx
0x14006c993  lea     rcx, [r15+20h]
0x14006c997  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006c99e  nop     dword ptr [rax+rax+00h]
0x14006c9a3  mov     rdx, qword ptr [rsp+138h+var_C8]
0x14006c9a8  lea     rax, [rsp+138h+var_C8]
0x14006c9ad  cmp     [rdx+8], rax
0x14006c9b1  jnz     loc_14006D069
0x14006c9b7  mov     rax, qword ptr [rsp+138h+var_C8+8]
0x14006c9bc  lea     rcx, [rsp+138h+var_C8]
0x14006c9c1  cmp     [rax], rcx
0x14006c9c4  jnz     loc_14006D069
0x14006c9ca  mov     [rax], rdx
0x14006c9cd  mov     [rdx+8], rax
0x14006c9d1  lea     rax, [rsp+138h+var_C8]
0x14006c9d6  mov     qword ptr [rsp+138h+var_C8+8], rax
0x14006c9db  lea     rax, [rsp+138h+var_C8]
0x14006c9e0  mov     qword ptr [rsp+138h+var_C8], rax
0x14006c9e5  xor     edx, edx
0x14006c9e7  lea     rcx, [r15+20h]
0x14006c9eb  call    cs:__imp_FltReleasePushLockEx
0x14006c9f2  nop     dword ptr [rax+rax+00h]
0x14006c9f7  test    r12, r12
0x14006c9fa  jz      short loc_14006CA0D
0x14006c9fc  mov     rcx, [rsp+138h+MemoryDescriptorList]; MemoryDescriptorList
0x14006ca01  call    cs:__imp_MmUnlockPages
0x14006ca08  nop     dword ptr [rax+rax+00h]
0x14006ca0d  mov     rax, [rsp+138h+MemoryDescriptorList]
0x14006ca12  test    rax, rax
0x14006ca15  jz      short loc_14006CA26
0x14006ca17  mov     rcx, rax; Mdl
0x14006ca1a  call    cs:__imp_IoFreeMdl
0x14006ca21  nop     dword ptr [rax+rax+00h]
0x14006ca26  mov     eax, edi
0x14006ca28  add     rsp, 100h
0x14006ca2f  pop     r15
0x14006ca31  pop     r14
0x14006ca33  pop     r13
0x14006ca35  pop     r12
0x14006ca37  pop     rdi
0x14006ca38  pop     rsi
0x14006ca39  pop     rbx
0x14006ca3a  retn
0x14006ca3c  mov     r12d, 0C000009Ah
0x14006ca42  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ca49  lea     rdx, WPP_GLOBAL_Control
0x14006ca50  cmp     rcx, rdx
0x14006ca53  jz      short loc_14006CA8C
0x14006ca55  test    dword ptr [rcx+2Ch], 100h
0x14006ca5c  jz      short loc_14006CA8C
0x14006ca5e  cmp     byte ptr [rcx+29h], 4
0x14006ca62  jb      short loc_14006CA8C
0x14006ca64  mov     [rsp+138h+var_F8], r14d
0x14006ca69  mov     [rsp+138h+var_100], rdi
0x14006ca6e  mov     [rsp+138h+var_108], rbx
0x14006ca73  mov     qword ptr [rsp+138h+Priority], rsi
0x14006ca78  mov     rax, [r15]
0x14006ca7b  mov     [rsp+138h+Irp], rax
0x14006ca80  mov     r9, r13
0x14006ca83  mov     rcx, [rcx+18h]
0x14006ca87  call    WPP_SF_iqiiqd
0x14006ca8c  mov     r8, [rsp+138h+var_80]
0x14006ca94  mov     rcx, [r8+20h]
0x14006ca98  call    CldSyncIsValidationRequired
0x14006ca9d  mov     byte ptr [rsp+138h+arg_18], al
0x14006caa4  mov     edx, 1
0x14006caa9  mov     rcx, r8
0x14006caac  call    CldHsmGetSyncPolicy
0x14006cab1  mov     rdi, [rsp+138h+var_90]
0x14006cab9  bt      eax, 9
0x14006cabd  jnb     short loc_14006CAF8
0x14006cabf  mov     rdx, [rdi]
0x14006cac2  cmp     qword ptr [rdx+0A0h], 0
0x14006caca  jz      short loc_14006CAE8
0x14006cacc  mov     ecx, [rdx+48h]
0x14006cacf  test    ecx, ecx
0x14006cad1  jz      short loc_14006CAE4
0x14006cad3  mov     rcx, [rdx+0A0h]
0x14006cada  mov     edx, [rdx+48h]
0x14006cadd  mov     ecx, [rcx+30h]
0x14006cae0  cmp     edx, ecx
0x14006cae2  jle     short loc_14006CAEE
0x14006cae4  mov     cl, 1
0x14006cae6  jmp     short loc_14006CAEA
0x14006cae8  xor     cl, cl
0x14006caea  test    cl, cl
0x14006caec  jnz     short loc_14006CAF8
0x14006caee  mov     byte ptr [rsp+138h+VirtualAddress], 1
0x14006caf6  jmp     short loc_14006CB00
0x14006caf8  mov     byte ptr [rsp+138h+VirtualAddress], 0
0x14006cb00  test    r14d, r14d
0x14006cb03  jns     short loc_14006CB36
0x14006cb05  mov     r12, [rsp+138h+Src]
0x14006cb0a  mov     [rsp+138h+var_108], r12
0x14006cb0f  mov     qword ptr [rsp+138h+Priority], rbx
0x14006cb14  mov     [rsp+138h+Irp], rsi
0x14006cb19  mov     r9d, r14d
0x14006cb1c  mov     r8d, 4
0x14006cb22  mov     rdx, r13
  ... truncated ...
```
