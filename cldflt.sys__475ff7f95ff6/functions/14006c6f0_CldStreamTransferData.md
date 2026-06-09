# CldStreamTransferData

- ea: `0x14006c6f0`
- end: `0x14006d190`
- name: `CldStreamTransferData`
- size: `2720`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, int, __int64, __int64 Length, PVOID VirtualAddress)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14006c178`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140010888`
- `0x140010910`
- `0x140010aa8`
- `0x140010b18`
- `0x140010ba0`
- `0x14001e300`
- `0x1400344a8`
- `0x14005fde4`
- `0x14006c6f0`
- `0x14006d198`
- `0x14006d530`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006ca30`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006ca30`
- `ntoskrnl!IoFreeMdl` at `0x14006c98f`
- `ntoskrnl!IoFreeMdl` at `0x14006cb3a`
- `ntoskrnl!IoFreeMdl` at `0x14006c98f`
- `ntoskrnl!IoFreeMdl` at `0x14006cb3a`
- `ntoskrnl!IoAllocateMdl` at `0x14006c87b`
- `ntoskrnl!IoAllocateMdl` at `0x14006c87b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c8f7`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c8f7`
- `ntoskrnl!MmUnlockPages` at `0x14006cb21`
- `ntoskrnl!MmUnlockPages` at `0x14006cb21`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006d0bc`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006d0bc`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006cf04`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006cf04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf72`
- `ntoskrnl!ExAllocatePool2` at `0x14006d041`
- `ntoskrnl!ExAllocatePool2` at `0x14006d041`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cb0b`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cce3`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cef4`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cf59`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cfb2`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d11f`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d178`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cb0b`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cce3`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cef4`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cf59`
- `FLTMGR!FltReleasePushLockEx` at `0x14006cfb2`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d11f`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d178`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cab7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cca5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006ce46`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cf1b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cf8a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d0f2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d135`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cab7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cca5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006ce46`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cf1b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006cf8a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d0f2`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d135`

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
0x14006c6f0  mov     r11, rsp
0x14006c6f3  mov     [r11+20h], r9
0x14006c6f7  mov     [r11+10h], rdx
0x14006c6fb  mov     [r11+8], rcx
0x14006c6ff  push    rbx
0x14006c700  push    rsi
0x14006c701  push    rdi
0x14006c702  push    r12
0x14006c704  push    r13
0x14006c706  push    r14
0x14006c708  push    r15
0x14006c70a  sub     rsp, 100h
0x14006c711  mov     rsi, r9
0x14006c714  mov     r14d, r8d
0x14006c717  mov     r15, rcx
0x14006c71a  xorps   xmm0, xmm0
0x14006c71d  xor     eax, eax
0x14006c71f  movups  [rsp+138h+var_C8], xmm0
0x14006c724  movups  [rsp+138h+var_B8], xmm0
0x14006c72c  mov     [r11-0A8h], rax
0x14006c733  mov     r8, [rcx]
0x14006c736  mov     [rsp+138h+var_90], r8
0x14006c73e  mov     [rsp+138h+var_60], r8
0x14006c746  mov     rax, [r8]
0x14006c749  mov     rdx, [rax+10h]
0x14006c74d  mov     r13, [rdx+20h]
0x14006c751  mov     [rsp+138h+var_58], r13
0x14006c759  mov     rbx, [rsp+138h+Length]
0x14006c761  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006c765  jnz     short loc_14006C774
0x14006c767  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14006c771  sub     rbx, r9
0x14006c774  mov     [rsp+138h+var_98], rbx
0x14006c77c  mov     [rsp+138h+MemoryDescriptorList], 0
0x14006c785  xor     r9d, r9d
0x14006c788  mov     [rsp+138h+Src], r9
0x14006c78d  xor     r10b, r10b
0x14006c790  mov     [rsp+138h+arg_8], r10b
0x14006c798  mov     rdi, [rsp+138h+VirtualAddress]
0x14006c7a0  test    rdi, rdi
0x14006c7a3  jz      short loc_14006C7AF
0x14006c7a5  mov     eax, 0FFFFFFFFh
0x14006c7aa  cmp     rbx, rax
0x14006c7ad  jg      short loc_14006C7BD
0x14006c7af  lea     rax, [rbx+rsi]
0x14006c7b3  mov     [rsp+138h+var_D0], rax
0x14006c7b8  cmp     rax, rsi
0x14006c7bb  jg      short loc_14006C828
0x14006c7bd  mov     eax, 0C000CF0Bh
0x14006c7c2  mov     [rsp+138h+var_E0], eax
0x14006c7c6  mov     ecx, eax
0x14006c7c8  call    HsmDbgBreakOnStatus
0x14006c7cd  lea     rax, WPP_GLOBAL_Control
0x14006c7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c7db  cmp     rcx, rax
0x14006c7de  jz      loc_14006CA9E
0x14006c7e4  test    dword ptr [rcx+2Ch], 100h
0x14006c7eb  jz      loc_14006CA9E
0x14006c7f1  cmp     byte ptr [rcx+29h], 2
0x14006c7f5  jb      loc_14006CA9E
0x14006c7fb  mov     dword ptr [rsp+138h+var_100], r14d
0x14006c800  mov     [rsp+138h+var_108], rdi
0x14006c805  mov     qword ptr [rsp+138h+Priority], rbx
0x14006c80a  mov     [rsp+138h+Irp], rsi
0x14006c80f  mov     r9, r13
0x14006c812  mov     rcx, [rcx+18h]
0x14006c816  call    WPP_SF_iiiqd
0x14006c81b  mov     edi, 0C000CF0Bh
0x14006c820  xor     r12d, r12d
0x14006c823  jmp     loc_14006CAA7
0x14006c828  mov     [rsp+138h+var_88], r13
0x14006c830  xor     eax, eax
0x14006c832  mov     [rsp+138h+var_E0], eax
0x14006c836  mov     r9, [r8+8]
0x14006c83a  mov     [rsp+138h+var_78], r9
0x14006c842  mov     [rsp+138h+var_50], r9
0x14006c84a  mov     rax, [r8+10h]
0x14006c84e  mov     [rsp+138h+var_80], rax
0x14006c856  mov     [rsp+138h+var_48], rax
0x14006c85e  test    r14d, r14d
0x14006c861  js      loc_14006CB5C
0x14006c867  mov     [rsp+138h+Irp], 0; Irp
0x14006c870  xor     r9d, r9d; ChargeQuota
0x14006c873  xor     r8d, r8d; SecondaryBuffer
0x14006c876  mov     edx, ebx; Length
0x14006c878  mov     rcx, rdi; VirtualAddress
0x14006c87b  call    cs:__imp_IoAllocateMdl
0x14006c882  nop     dword ptr [rax+rax+00h]
0x14006c887  mov     rcx, rax
0x14006c88a  mov     [rsp+138h+MemoryDescriptorList], rax
0x14006c88f  mov     [rsp+138h+Mdl], rax
0x14006c897  mov     r12d, 0C000009Ah
0x14006c89d  test    rax, rax
0x14006c8a0  jnz     short loc_14006C8E9
0x14006c8a2  mov     r14d, r12d
0x14006c8a5  mov     ecx, r12d
0x14006c8a8  call    HsmDbgBreakOnStatus
0x14006c8ad  lea     rax, WPP_GLOBAL_Control
0x14006c8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c8bb  cmp     rcx, rax
0x14006c8be  jz      short loc_14006C8E4
0x14006c8c0  test    dword ptr [rcx+2Ch], 100h
0x14006c8c7  jz      short loc_14006C8E4
0x14006c8c9  cmp     byte ptr [rcx+29h], 2
0x14006c8cd  jb      short loc_14006C8E4
0x14006c8cf  mov     qword ptr [rsp+138h+Priority], rdi
0x14006c8d4  mov     dword ptr [rsp+138h+Irp], ebx
0x14006c8d8  mov     r9, r13
0x14006c8db  mov     rcx, [rcx+18h]
0x14006c8df  call    WPP_SF_iDqd
0x14006c8e4  mov     rcx, [rsp+138h+MemoryDescriptorList]; MemoryDescriptorList
0x14006c8e9  test    rcx, rcx
0x14006c8ec  jz      loc_14006CB62
0x14006c8f2  xor     r8d, r8d; Operation
0x14006c8f5  mov     dl, 1; AccessMode
0x14006c8f7  call    cs:__imp_MmProbeAndLockPages
0x14006c8fe  nop     dword ptr [rax+rax+00h]
0x14006c903  mov     rcx, [rsp+138h+MemoryDescriptorList]
0x14006c908  jmp     loc_14006CA02
0x14006c90d  mov     r14d, eax
0x14006c910  mov     ecx, eax
0x14006c912  call    HsmDbgBreakOnStatus
0x14006c917  lea     rax, WPP_GLOBAL_Control
0x14006c91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c925  cmp     rcx, rax
0x14006c928  jz      short loc_14006C977
0x14006c92a  test    dword ptr [rcx+2Ch], 100h
0x14006c931  jz      short loc_14006C977
0x14006c933  cmp     byte ptr [rcx+29h], 2
0x14006c937  jb      short loc_14006C977
0x14006c939  mov     edx, 28h ; '('
0x14006c93e  mov     dword ptr [rsp+138h+var_108], r14d
0x14006c943  mov     rdi, [rsp+138h+VirtualAddress]
0x14006c94b  mov     qword ptr [rsp+138h+Priority], rdi
0x14006c950  mov     rbx, [rsp+138h+var_98]
0x14006c958  mov     [rsp+138h+Irp], rbx
0x14006c95d  mov     r9, [rsp+138h+var_88]
0x14006c965  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006c96c  mov     rcx, [rcx+18h]
0x14006c970  call    WPP_SF_qqqd
0x14006c975  jmp     short loc_14006C987
0x14006c977  mov     rdi, [rsp+138h+VirtualAddress]
0x14006c97f  mov     rbx, [rsp+138h+var_98]
0x14006c987  mov     rcx, [rsp+138h+Mdl]; Mdl
0x14006c98f  call    cs:__imp_IoFreeMdl
0x14006c996  nop     dword ptr [rax+rax+00h]
0x14006c99b  xor     ecx, ecx; MemoryDescriptorList
0x14006c99d  mov     [rsp+138h+MemoryDescriptorList], rcx
0x14006c9a2  mov     r12d, 0C000009Ah
0x14006c9a8  mov     rsi, [rsp+138h+arg_18]
0x14006c9b0  mov     r15, [rsp+138h+arg_0]
0x14006c9b8  mov     eax, ecx
0x14006c9ba  mov     [rsp+138h+var_E0], ecx
0x14006c9be  mov     [rsp+138h+Src], rax
0x14006c9c3  mov     [rsp+138h+arg_8], al
0x14006c9ca  mov     rax, [rsp+138h+var_60]
0x14006c9d2  mov     [rsp+138h+var_90], rax
0x14006c9da  mov     r13, [rsp+138h+var_58]
0x14006c9e2  mov     rax, [rsp+138h+var_50]
0x14006c9ea  mov     [rsp+138h+var_78], rax
0x14006c9f2  mov     rax, [rsp+138h+var_48]
0x14006c9fa  mov     [rsp+138h+var_80], rax
0x14006ca02  test    rcx, rcx
0x14006ca05  jz      loc_14006CB62
0x14006ca0b  test    byte ptr [rcx+0Ah], 5
0x14006ca0f  jz      short loc_14006CA17
0x14006ca11  mov     r9, [rcx+18h]
0x14006ca15  jmp     short loc_14006CA3F
0x14006ca17  mov     [rsp+138h+Priority], 40000010h; Priority
0x14006ca1f  mov     dword ptr [rsp+138h+Irp], 0; BugCheckOnFailure
0x14006ca27  xor     r9d, r9d; RequestedAddress
0x14006ca2a  xor     edx, edx; AccessMode
0x14006ca2c  lea     r8d, [r9+1]; CacheType
0x14006ca30  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006ca37  nop     dword ptr [rax+rax+00h]
0x14006ca3c  mov     r9, rax
0x14006ca3f  mov     [rsp+138h+Src], r9
0x14006ca44  test    r9, r9
0x14006ca47  jnz     loc_14006CB62
0x14006ca4d  mov     ecx, r12d
0x14006ca50  call    HsmDbgBreakOnStatus
0x14006ca55  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ca5c  lea     rdx, WPP_GLOBAL_Control
0x14006ca63  cmp     rcx, rdx
0x14006ca66  jz      short loc_14006CA9E
0x14006ca68  test    dword ptr [rcx+2Ch], 100h
0x14006ca6f  jz      short loc_14006CA9E
0x14006ca71  cmp     byte ptr [rcx+29h], 2
0x14006ca75  jb      short loc_14006CA9E
0x14006ca77  mov     edx, 29h ; ')'
0x14006ca7c  mov     dword ptr [rsp+138h+var_108], r12d
0x14006ca81  mov     qword ptr [rsp+138h+Priority], rdi
0x14006ca86  mov     [rsp+138h+Irp], rbx
0x14006ca8b  mov     r9, r13
0x14006ca8e  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006ca95  mov     rcx, [rcx+18h]
0x14006ca99  call    WPP_SF_qqqd
0x14006ca9e  mov     edi, [rsp+138h+var_E0]
0x14006caa2  mov     r12, [rsp+138h+Src]
0x14006caa7  cmp     [rsp+138h+arg_8], 0
0x14006caaf  jz      short loc_14006CB17
0x14006cab1  xor     edx, edx
0x14006cab3  lea     rcx, [r15+20h]
0x14006cab7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006cabe  nop     dword ptr [rax+rax+00h]
0x14006cac3  mov     rdx, qword ptr [rsp+138h+var_C8]
0x14006cac8  lea     rax, [rsp+138h+var_C8]
0x14006cacd  cmp     [rdx+8], rax
0x14006cad1  jnz     loc_14006D189
0x14006cad7  mov     rax, qword ptr [rsp+138h+var_C8+8]
0x14006cadc  lea     rcx, [rsp+138h+var_C8]
0x14006cae1  cmp     [rax], rcx
0x14006cae4  jnz     loc_14006D189
0x14006caea  mov     [rax], rdx
0x14006caed  mov     [rdx+8], rax
0x14006caf1  lea     rax, [rsp+138h+var_C8]
0x14006caf6  mov     qword ptr [rsp+138h+var_C8+8], rax
0x14006cafb  lea     rax, [rsp+138h+var_C8]
0x14006cb00  mov     qword ptr [rsp+138h+var_C8], rax
0x14006cb05  xor     edx, edx
0x14006cb07  lea     rcx, [r15+20h]
0x14006cb0b  call    cs:__imp_FltReleasePushLockEx
0x14006cb12  nop     dword ptr [rax+rax+00h]
0x14006cb17  test    r12, r12
0x14006cb1a  jz      short loc_14006CB2D
0x14006cb1c  mov     rcx, [rsp+138h+MemoryDescriptorList]; MemoryDescriptorList
0x14006cb21  call    cs:__imp_MmUnlockPages
0x14006cb28  nop     dword ptr [rax+rax+00h]
0x14006cb2d  mov     rax, [rsp+138h+MemoryDescriptorList]
0x14006cb32  test    rax, rax
0x14006cb35  jz      short loc_14006CB46
0x14006cb37  mov     rcx, rax; Mdl
0x14006cb3a  call    cs:__imp_IoFreeMdl
0x14006cb41  nop     dword ptr [rax+rax+00h]
0x14006cb46  mov     eax, edi
0x14006cb48  add     rsp, 100h
0x14006cb4f  pop     r15
0x14006cb51  pop     r14
0x14006cb53  pop     r13
0x14006cb55  pop     r12
0x14006cb57  pop     rdi
0x14006cb58  pop     rsi
0x14006cb59  pop     rbx
0x14006cb5a  retn
0x14006cb5c  mov     r12d, 0C000009Ah
0x14006cb62  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb69  lea     rdx, WPP_GLOBAL_Control
0x14006cb70  cmp     rcx, rdx
0x14006cb73  jz      short loc_14006CBAC
0x14006cb75  test    dword ptr [rcx+2Ch], 100h
0x14006cb7c  jz      short loc_14006CBAC
0x14006cb7e  cmp     byte ptr [rcx+29h], 4
0x14006cb82  jb      short loc_14006CBAC
0x14006cb84  mov     [rsp+138h+var_F8], r14d
0x14006cb89  mov     [rsp+138h+var_100], rdi
0x14006cb8e  mov     [rsp+138h+var_108], rbx
0x14006cb93  mov     qword ptr [rsp+138h+Priority], rsi
0x14006cb98  mov     rax, [r15]
0x14006cb9b  mov     [rsp+138h+Irp], rax
0x14006cba0  mov     r9, r13
0x14006cba3  mov     rcx, [rcx+18h]
0x14006cba7  call    WPP_SF_iqiiqd
0x14006cbac  mov     r8, [rsp+138h+var_80]
0x14006cbb4  mov     rcx, [r8+20h]
0x14006cbb8  call    CldSyncIsValidationRequired
0x14006cbbd  mov     byte ptr [rsp+138h+arg_18], al
0x14006cbc4  mov     edx, 1
0x14006cbc9  mov     rcx, r8
0x14006cbcc  call    CldHsmGetSyncPolicy
0x14006cbd1  mov     rdi, [rsp+138h+var_90]
0x14006cbd9  bt      eax, 9
0x14006cbdd  jnb     short loc_14006CC18
0x14006cbdf  mov     rdx, [rdi]
0x14006cbe2  cmp     qword ptr [rdx+0A0h], 0
0x14006cbea  jz      short loc_14006CC08
0x14006cbec  mov     ecx, [rdx+48h]
0x14006cbef  test    ecx, ecx
0x14006cbf1  jz      short loc_14006CC04
0x14006cbf3  mov     rcx, [rdx+0A0h]
0x14006cbfa  mov     edx, [rdx+48h]
0x14006cbfd  mov     ecx, [rcx+30h]
0x14006cc00  cmp     edx, ecx
0x14006cc02  jle     short loc_14006CC0E
0x14006cc04  mov     cl, 1
0x14006cc06  jmp     short loc_14006CC0A
0x14006cc08  xor     cl, cl
0x14006cc0a  test    cl, cl
0x14006cc0c  jnz     short loc_14006CC18
0x14006cc0e  mov     byte ptr [rsp+138h+VirtualAddress], 1
0x14006cc16  jmp     short loc_14006CC20
0x14006cc18  mov     byte ptr [rsp+138h+VirtualAddress], 0
0x14006cc20  test    r14d, r14d
0x14006cc23  jns     short loc_14006CC56
0x14006cc25  mov     r12, [rsp+138h+Src]
0x14006cc2a  mov     [rsp+138h+var_108], r12
0x14006cc2f  mov     qword ptr [rsp+138h+Priority], rbx
0x14006cc34  mov     [rsp+138h+Irp], rsi
0x14006cc39  mov     r9d, r14d
0x14006cc3c  mov     r8d, 4
0x14006cc42  mov     rdx, r13
  ... truncated ...
```
