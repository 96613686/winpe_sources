# HbIoDispatchIoctl

- ea: `0x14000ecd0`
- end: `0x14000f941`
- name: `HbIoDispatchIoctl`
- size: `3185`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001600`
- `0x140002ae0`
- `0x140002c00`
- `0x140002f00`
- `0x14000ecd0`
- `0x14000fee8`
- `0x14001006c`
- `0x14001274c`
- `0x1400129f4`
- `0x140013510`

## import_xrefs

- `ntoskrnl!HvlQueryActiveHypervisorProcessorCount` at `0x14000ef26`
- `ntoskrnl!HvlQueryActiveHypervisorProcessorCount` at `0x14000ef26`
- `ntoskrnl!ExAllocatePool2` at `0x14000f3ac`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7e1`
- `ntoskrnl!ExAllocatePool2` at `0x14000f3ac`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f3ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f3ec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000efb0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000efb0`
- `ntoskrnl!IofCompleteRequest` at `0x14000ee1f`
- `ntoskrnl!IofCompleteRequest` at `0x14000ee1f`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14000ef47`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14000ef47`
- `winhvr!WinHvGetSystemInformation` at `0x14000f0c6`
- `winhvr!WinHvGetSystemInformation` at `0x14000f162`
- `winhvr!WinHvGetSystemInformation` at `0x14000f1e8`
- `winhvr!WinHvGetSystemInformation` at `0x14000f2a9`
- `winhvr!WinHvGetSystemInformation` at `0x14000f61e`
- `winhvr!WinHvGetSystemInformation` at `0x14000f6ed`
- `winhvr!WinHvGetSystemInformation` at `0x14000f0c6`
- `winhvr!WinHvGetSystemInformation` at `0x14000f162`
- `winhvr!WinHvGetSystemInformation` at `0x14000f1e8`
- `winhvr!WinHvGetSystemInformation` at `0x14000f2a9`
- `winhvr!WinHvGetSystemInformation` at `0x14000f61e`
- `winhvr!WinHvGetSystemInformation` at `0x14000f6ed`
- `winhvr!WinHvCommitSecFwSvn` at `0x14000f008`
- `winhvr!WinHvCommitSecFwSvn` at `0x14000f008`
- `winhvr!WinHvLogHypervisorSystemConfig` at `0x14000f588`
- `winhvr!WinHvLogHypervisorSystemConfig` at `0x14000f588`
- `winhvr!WinHvGetPartitionProperty` at `0x14000f237`
- `winhvr!WinHvGetPartitionProperty` at `0x14000f840`
- `winhvr!WinHvGetPartitionProperty` at `0x14000f8f9`
- `winhvr!WinHvGetPartitionProperty` at `0x14000f237`
- `winhvr!WinHvGetPartitionProperty` at `0x14000f840`
- `winhvr!WinHvGetPartitionProperty` at `0x14000f8f9`
- `winhvr!WinHvUpdateSecFw` at `0x14000efde`
- `winhvr!WinHvUpdateSecFw` at `0x14000efde`
- `winhvr!WinHvConfigureProfiler` at `0x14000edcf`
- `winhvr!WinHvConfigureProfiler` at `0x14000edcf`
- `winhvr!WinHvSetLogicalProcessorRegisters` at `0x14000f498`
- `winhvr!WinHvSetLogicalProcessorRegisters` at `0x14000f498`
- `winhvr!WinHvUpdateHvProcessorFeatures` at `0x14000f02d`
- `winhvr!WinHvUpdateHvProcessorFeatures` at `0x14000f19f`
- `winhvr!WinHvUpdateHvProcessorFeatures` at `0x14000f02d`
- `winhvr!WinHvUpdateHvProcessorFeatures` at `0x14000f19f`
- `winhvr!WinHvGetPartitionPropertyEx` at `0x14000f815`
- `winhvr!WinHvGetPartitionPropertyEx` at `0x14000f815`
- `winhvr!WinHvSetHwWatchdogConfig` at `0x14000f5c9`
- `winhvr!WinHvSetHwWatchdogConfig` at `0x14000f5c9`
- `winhvr!WinHvGetLogicalProcessorRegisters` at `0x14000f3d4`
- `winhvr!WinHvGetLogicalProcessorRegisters` at `0x14000f3d4`
- `winhvr!WinHvSetSystemInformation` at `0x14000f10f`
- `winhvr!WinHvSetSystemInformation` at `0x14000f10f`

## string_xrefs

- `0x14000f556`: `MSR read exception for address 0x%x`

## pseudocode

```c
__int64 __fastcall HbIoDispatchIoctl(__int64 a1, IRP *a2)
{
  unsigned int v4; // r12d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r11
  __int64 Options; // rdx
  size_t Length; // r15
  unsigned int *MasterIrp; // rbx
  struct _IRP *v9; // rsi
  unsigned int LowPart; // ecx
  __int64 v11; // r13
  int v12; // r14d
  int SystemInformation; // ebx
  IRP *v14; // rsi
  int v15; // eax
  int v17; // eax
  __int64 v18; // r8
  ULONG ActiveProcessorCount; // eax
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // r9
  int updated; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  unsigned int *v26; // rdx
  unsigned __int8 v27; // r14
  __int64 v28; // rax
  __int64 v29; // r8
  unsigned __int64 v30; // r9
  unsigned int *v31; // rax
  _QWORD *Pool2; // rax
  _BYTE *v33; // r14
  char *v34; // rcx
  unsigned int v35; // r10d
  __int64 v36; // r8
  unsigned __int64 v37; // r9
  unsigned __int64 v38; // rdx
  char *v39; // rbx
  char *v40; // rax
  unsigned int v41; // r8d
  int v52; // eax
  _OWORD *v53; // rax
  __int64 v54; // r14
  _BYTE *v55; // rax
  unsigned __int8 v56; // r15
  unsigned __int8 v57; // dl
  unsigned __int8 v58; // bl
  __int64 v60; // [rsp+38h] [rbp-2B0h] BYREF
  ULONG v61; // [rsp+40h] [rbp-2A8h] BYREF
  unsigned int v62; // [rsp+44h] [rbp-2A4h] BYREF
  int v63; // [rsp+48h] [rbp-2A0h] BYREF
  _QWORD v64[2]; // [rsp+50h] [rbp-298h] BYREF
  LARGE_INTEGER *p_ByteOffset; // [rsp+60h] [rbp-288h]
  unsigned __int64 v66; // [rsp+68h] [rbp-280h]
  __int64 v67; // [rsp+70h] [rbp-278h] BYREF
  int v68; // [rsp+78h] [rbp-270h]
  int v69; // [rsp+7Ch] [rbp-26Ch]
  __int128 v70; // [rsp+80h] [rbp-268h] BYREF
  __int128 v71; // [rsp+90h] [rbp-258h]
  LIST_ENTRY v72; // [rsp+A0h] [rbp-248h]
  _BYTE v73[520]; // [rsp+B0h] [rbp-238h] BYREF

  v64[1] = a2;
  v62 = 0;
  v4 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (_DWORD)Options )
    MasterIrp = (unsigned int *)a2->AssociatedIrp.MasterIrp;
  else
    MasterIrp = 0;
  if ( (_DWORD)Length )
    v9 = a2->AssociatedIrp.MasterIrp;
  else
    v9 = 0;
  p_ByteOffset = &CurrentStackLocation->Parameters.Read.ByteOffset;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart > 0x228044 )
  {
    if ( LowPart <= 0x228060 )
    {
      switch ( LowPart )
      {
        case 0x228060u:
          if ( v9 )
          {
            v12 = 48;
            if ( (unsigned int)Length >= 0x30 )
            {
              v70 = 0;
              v71 = 0;
              v72 = 0;
              SystemInformation = WinHvGetSystemInformation(0, 0, 0, &v70, 48, 0);
              if ( SystemInformation < 0 )
                goto LABEL_22;
              *(_OWORD *)&v9->Type = v70;
              *(_OWORD *)&v9->Flags = v71;
              v9->ThreadListEntry = v72;
              goto LABEL_47;
            }
          }
          goto LABEL_62;
        case 0x228048u:
          v4 = 520;
          memset(v73, 0, sizeof(v73));
          if ( (unsigned int)Length < 0x208 || !v9 )
          {
            SystemInformation = -1073741789;
            goto LABEL_35;
          }
          SystemInformation = WinHvGetSystemInformation(11, 0, 0, v73, 520, 0);
          if ( SystemInformation < 0 )
            goto LABEL_22;
          v53 = v73;
          v54 = 4;
          do
          {
            *(_OWORD *)&v9->Type = *v53;
            *(_OWORD *)&v9->Flags = v53[1];
            v9->ThreadListEntry = (LIST_ENTRY)v53[2];
            *(_OWORD *)&v9->IoStatus.Status = v53[3];
            *(_OWORD *)&v9->RequestorMode = v53[4];
            *(_OWORD *)&v9->UserEvent = v53[5];
            *(union _IRP::$6B96A96ED958C92F2CB4B83EAB343043 *)((char *)&v9->Overlay + 8) = (union _IRP::$6B96A96ED958C92F2CB4B83EAB343043)v53[6];
            *(_OWORD *)&v9->UserBuffer = v53[7];
            v9 = (struct _IRP *)((char *)v9 + 128);
            v53 += 8;
            --v54;
          }
          while ( v54 );
          v28 = *(_QWORD *)v53;
          goto LABEL_107;
        case 0x22804Cu:
          if ( (unsigned int)(Options - 1) > 0xFFF || !MasterIrp )
            goto LABEL_18;
          v15 = WinHvSetHwWatchdogConfig(MasterIrp);
          goto LABEL_21;
        case 0x228050u:
          SystemInformation = WinHvLogHypervisorSystemConfig();
          v52 = HbEvtpTraceMinrootConfig();
          v14 = a2;
          if ( SystemInformation < 0 )
            goto LABEL_24;
          SystemInformation = v52;
          goto LABEL_23;
      }
      if ( LowPart != 2261076 )
      {
        if ( LowPart == 2261080 )
        {
          v60 = 0;
          if ( (unsigned int)Length < 8 || !v9 || (unsigned int)Options < 0x10 || !MasterIrp )
            goto LABEL_18;
          v34 = (char *)MasterIrp + MasterIrp[1];
          v35 = *MasterIrp;
          v36 = 2LL * *MasterIrp;
          v37 = (unsigned __int64)&v34[16 * *MasterIrp];
          v38 = (unsigned __int64)MasterIrp + Options;
          if ( v37 <= v38 )
          {
            v39 = (char *)MasterIrp + MasterIrp[2];
            if ( (unsigned __int64)&v39[8 * v36] <= v38 )
            {
              v40 = v34;
              if ( (unsigned __int64)v34 >= v37 )
              {
LABEL_139:
                v17 = WinHvSetLogicalProcessorRegisters(v35, v34, v39, &v60);
LABEL_32:
                SystemInformation = v17;
                if ( v17 >= 0 )
                {
                  *(_QWORD *)&v9->Type = v60;
                  v4 = 8;
                }
                goto LABEL_22;
              }
              while ( *((_DWORD *)v40 + 1) == 65539 )
              {
                v40 += 16;
                if ( (unsigned __int64)v40 >= v37 )
                  goto LABEL_139;
              }
            }
          }
          goto LABEL_34;
        }
        if ( LowPart != 2261084 )
          goto LABEL_169;
        if ( (unsigned int)Length < 0x20 || !v9 || (unsigned int)Options < 0x14 || !MasterIrp )
          goto LABEL_18;
        v29 = 4LL * *MasterIrp;
        v30 = (unsigned __int64)&MasterIrp[v29 + 1];
        if ( MasterIrp + 1 == (unsigned int *)v30
          || v30 > (unsigned __int64)MasterIrp + Options
          || (char *)&v9->Flags + v29 * 4 > (char *)v9 + Length )
        {
          goto LABEL_34;
        }
        v31 = MasterIrp + 1;
        if ( (unsigned __int64)(MasterIrp + 1) < v30 )
        {
          while ( v31[1] == 65539 )
          {
            v31 += 4;
            if ( (unsigned __int64)v31 >= v30 )
              goto LABEL_126;
          }
          goto LABEL_34;
        }
LABEL_126:
        Pool2 = (_QWORD *)ExAllocatePool2(64, Length, 1867080264);
        v33 = Pool2;
        if ( Pool2 )
        {
          *Pool2 = 0;
          SystemInformation = WinHvGetLogicalProcessorRegisters(*MasterIrp, MasterIrp + 1, Pool2, Pool2 + 2);
          if ( SystemInformation >= 0 )
          {
            memmove(v9, v33, Length);
            v4 = Length;
          }
LABEL_129:
          ExFreePoolWithTag(v33, 0x6F496248u);
          goto LABEL_22;
        }
        goto LABEL_58;
      }
      if ( (unsigned int)Options < 4 )
        goto LABEL_62;
      if ( !MasterIrp )
        goto LABEL_62;
      v4 = 8;
      LODWORD(v60) = 8;
      if ( (unsigned int)Length < 8 || !v9 )
        goto LABEL_62;
      v41 = *MasterIrp;
      if ( *MasterIrp + 1073675982 > 1 )
        goto LABEL_34;
      LODWORD(v67) = 0;
      _RAX = 0x80000000LL;
      __asm { cpuid }
      HIDWORD(v67) = _RBX;
      v68 = _RCX;
      v69 = _RDX;
      if ( (unsigned int)_RAX < 0x8000001F )
        goto LABEL_34;
      v61 = v41;
      _RAX = 2147483679LL;
      __asm { cpuid }
      HIDWORD(v67) = _RBX;
      v68 = _RCX;
      v69 = _RDX;
      if ( (_RAX & 0x10) == 0 )
        goto LABEL_34;
      v66 = __readmsr(v41);
      *(_QWORD *)&v9->Type = v66;
LABEL_102:
      SystemInformation = 0;
      v14 = a2;
      goto LABEL_25;
    }
    switch ( LowPart )
    {
      case 0x228064u:
        if ( (_DWORD)Options != 1 || !MasterIrp )
        {
          SystemInformation = -1073741811;
LABEL_49:
          v14 = a2;
          goto LABEL_23;
        }
        v24 = 1;
        v25 = 17;
        break;
      case 0x228068u:
        if ( (unsigned int)Length < 8 || !v9 )
          goto LABEL_62;
        v60 = 0;
        SystemInformation = WinHvGetPartitionProperty(-1, 393237, &v60);
        if ( SystemInformation < 0 )
          goto LABEL_22;
        *(_QWORD *)&v9->Type = v60;
        v4 = 8;
        goto LABEL_102;
      case 0x22806Cu:
        if ( MasterIrp )
          goto LABEL_18;
        if ( (unsigned int)Length < 0x18 || !v9 )
          goto LABEL_62;
        v55 = (_BYTE *)ExAllocatePool2(256, 4072, 1867080264);
        v33 = v55;
        if ( v55 )
        {
          memset(v55, 0, 0xFE8u);
          if ( (int)WinHvGetPartitionPropertyEx(-1, 589840, 0, v33) >= 0 )
          {
            if ( *v33 )
            {
              v57 = *v33;
              if ( *v33 > 3u )
                v57 = 3;
              if ( Length >= 8 * (unsigned __int64)v57 )
              {
                v58 = 0;
                do
                {
                  *((_QWORD *)&v9->Type + v58) = *(_QWORD *)&v33[8 * v58 + 8];
                  ++v58;
                }
                while ( v58 < v57 );
                v4 = 8 * v57;
LABEL_192:
                SystemInformation = 0;
              }
              else
              {
                SystemInformation = -1073741789;
              }
            }
            else
            {
              SystemInformation = -1073741811;
            }
          }
          else
          {
            v56 = 0;
            while ( 1 )
            {
              v60 = 0;
              SystemInformation = WinHvGetPartitionProperty(-1, (unsigned int)v56 + 393226, &v60);
              if ( SystemInformation < 0 )
                break;
              *((_QWORD *)&v9->Type + v56++) = v60;
              if ( v56 >= 2u )
              {
                v4 = 16;
                goto LABEL_192;
              }
            }
          }
          goto LABEL_129;
        }
LABEL_58:
        SystemInformation = -1073741670;
        goto LABEL_35;
      case 0x22BFE4u:
        v24 = 0;
        v26 = 0;
        v25 = 16;
        goto LABEL_82;
      case 0x22BFE8u:
        if ( (_DWORD)Options != 1 || !MasterIrp )
          goto LABEL_18;
        v24 = 1;
        v25 = (unsigned int)(Options - 1 + 15);
        break;
      default:
        goto LABEL_169;
    }
LABEL_81:
    v26 = MasterIrp;
LABEL_82:
    v15 = WinHvSetSystemInformation(v25, v26, v24);
    goto LABEL_21;
  }
  if ( LowPart == 2261060 )
  {
    v64[0] = 0;
    v4 = 8;
    if ( (unsigned int)Length < 8 || !v9 )
      goto LABEL_62;
    SystemInformation = WinHvGetSystemInformation(12, 0, 0, v64, 8, 0);
    if ( SystemInformation < 0 )
      goto LABEL_22;
    v28 = v64[0];
LABEL_107:
    *(_QWORD *)&v9->Type = v28;
    goto LABEL_22;
  }
  if ( LowPart <= 0x22800C )
  {
    if ( LowPart == 2261004 )
    {
      if ( (_DWORD)Options || (_DWORD)Length )
        goto LABEL_18;
      SystemInformation = WinHvUpdateHvProcessorFeatures(0, 1);
      if ( SystemInformation >= 0 )
      {
        LOBYTE(v23) = 1;
        HbEvtpLogProcessorFeatures(v23);
      }
      goto LABEL_22;
    }
    v11 = *(_QWORD *)(a1 + 64);
    if ( LowPart == 2244588 )
    {
      updated = WinHvCommitSecFwSvn();
      goto LABEL_60;
    }
    if ( LowPart != 2244593 )
    {
      v12 = 4;
      if ( LowPart != 2244596 )
      {
        if ( LowPart != 2244600 )
        {
          if ( LowPart != 2244604 )
          {
            if ( LowPart == 2261000 )
            {
              if ( (_DWORD)Options != 8 )
              {
LABEL_18:
                SystemInformation = -1073741811;
LABEL_19:
                v14 = a2;
LABEL_24:
                HbpTraceEvent(
                  0,
                  "HbIoDispatchIoctl",
                  1252,
                  "IOCTL 0x%x failed with 0x%x",
                  p_ByteOffset->LowPart,
                  SystemInformation);
                goto LABEL_25;
              }
              v15 = WinHvConfigureProfiler(
                      a2->AssociatedIrp.MasterIrp->Type,
                      *(unsigned int *)(&a2->AssociatedIrp.MasterIrp->Size + 1));
              goto LABEL_21;
            }
            goto LABEL_169;
          }
          if ( (unsigned int)Length < 8 || !v9 || (unsigned int)Options < 8 || !MasterIrp )
            goto LABEL_18;
          v60 = 0;
          if ( *MasterIrp - 1 <= 9 )
          {
            v17 = HvStatsMapHvStatsPage(v11, CurrentStackLocation->FileObject, *MasterIrp, MasterIrp[1], (__int64)&v60);
            goto LABEL_32;
          }
          goto LABEL_34;
        }
        if ( (unsigned int)Options < 8 || !MasterIrp )
          goto LABEL_18;
        v18 = *MasterIrp;
        if ( (unsigned int)(v18 - 1) <= 9 )
        {
          v15 = HvStatsUnmapHvStatsPage(v11, CurrentStackLocation->FileObject, v18, MasterIrp[1]);
LABEL_21:
          SystemInformation = v15;
LABEL_22:
          v14 = a2;
          goto LABEL_23;
        }
LABEL_34:
        SystemInformation = -1073741811;
LABEL_35:
        v14 = a2;
        goto LABEL_24;
      }
      if ( (unsigned int)Length >= 4 && v9 )
      {
        v61 = 0;
        if ( HbpIsCpuManagementPartition )
        {
          SystemInformation = HvlQueryActiveHypervisorProcessorCount(&v61);
          if ( SystemInformation < 0 )
            goto LABEL_22;
          ActiveProcessorCount = v61;
        }
        else
        {
          ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
          SystemInformation = 0;
        }
        *(_DWORD *)&v9->Type = ActiveProcessorCount;
LABEL_47:
        v4 = v12;
        goto LABEL_22;
      }
      SystemInformation = -1073741789;
      goto LABEL_49;
    }
    v4 = 16;
    if ( (unsigned int)Options >= 0x10 && MasterIrp && (unsigned int)Length >= MasterIrp[3] && (_DWORD)Length )
    {
      MdlAddress = a2->MdlAddress;
      if ( (MdlAddress->MdlFlags & 5) != 0 )
        MappedSystemVa = MdlAddress->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0xC0000010);
      if ( !MappedSystemVa )
        goto LABEL_58;
      LOBYTE(MdlAddress) = *(_BYTE *)MasterIrp;
      updated = WinHvUpdateSecFw(MdlAddress, MasterIrp[1], MasterIrp[2]);
LABEL_60:
      SystemInformation = updated;
      if ( updated >= 0 )
        HbEvtpLogSecFwStatus();
      goto LABEL_22;
    }
LABEL_62:
    SystemInformation = -1073741789;
    goto LABEL_19;
  }
  switch ( LowPart )
  {
    case 0x228010u:
      if ( (unsigned int)Length >= 0x10 && v9 )
      {
        v27 = 0;
        while ( 1 )
        {
          v60 = 0;
          SystemInformation = WinHvGetPartitionProperty(-1, (unsigned int)v27 + 393226, &v60);
          if ( SystemInformation < 0 )
            goto LABEL_22;
          *((_QWORD *)&v9->Type + v27++) = v60;
          if ( v27 >= 2u )
          {
            v4 = 16;
            goto LABEL_102;
          }
        }
      }
      goto LABEL_62;
    case 0x228028u:
      v4 = 4;
      if ( (unsigned int)Length >= 4 && v9 )
      {
        v63 = 0;
        SystemInformation = WinHvGetSystemInformation(1, 0, 0, &v63, 4, 0);
        if ( SystemInformation >= 0 )
          *(_DWORD *)&v9->Type = v63;
        goto LABEL_22;
      }
      goto LABEL_62;
    case 0x228034u:
      if ( (unsigned int)Options < 0x10 || !MasterIrp )
        goto LABEL_18;
      v15 = WinHvUpdateHvProcessorFeatures(*MasterIrp, *((_QWORD *)MasterIrp + 1));
      goto LABEL_21;
  }
  if ( LowPart != 2261048 )
  {
    if ( LowPart != 2261052 )
    {
      if ( LowPart == 2261056 )
      {
        v67 = 0;
        v68 = 0;
        v4 = 12;
        if ( (unsigned int)Length >= 0xC && v9 )
        {
          SystemInformation = WinHvGetSystemInformation(10, 0, 0, &v67, 12, 0);
          if ( SystemInformation >= 0 )
          {
            *(_QWORD *)&v9->Type = v67;
            LODWORD(v9->MdlAddress) = v68;
          }
          goto LABEL_22;
        }
        goto LABEL_62;
      }
LABEL_169:
      HbpTraceEvent(1, "HbIoDispatchIoctl", 1233, "Unrecognized IOCTL code 0x%x", LowPart);
      SystemInformation = -1073741808;
      goto LABEL_35;
    }
    if ( (unsigned int)Options < 4 || !MasterIrp )
      goto LABEL_18;
    v24 = 4;
    v25 = 10;
    goto LABEL_81;
  }
  if ( (unsigned int)Options < 4 || !MasterIrp || (unsigned int)Length < 8 || !v9 )
    goto LABEL_18;
  SystemInformation = WinHvGetSystemInformation(3, MasterIrp, 4, v9, Length, &v62);
  v14 = a2;
  if ( SystemInformation >= 0 )
    v4 = v62;
LABEL_23:
  if ( SystemInformation < 0 )
    goto LABEL_24;
LABEL_25:
  v14->IoStatus.Information = v4;
  v14->IoStatus.Status = SystemInformation;
  IofCompleteRequest(v14, 0);
  return (unsigned int)SystemInformation;
}

```

## disassembly

```asm
0x14000ecd0  mov     [rsp+arg_10], rbx
0x14000ecd5  mov     [rsp+arg_18], rsi
0x14000ecda  push    rdi
0x14000ecdb  push    r12
0x14000ecdd  push    r13
0x14000ecdf  push    r14
0x14000ece1  push    r15
0x14000ece3  sub     rsp, 2C0h
0x14000ecea  mov     rax, cs:__security_cookie
0x14000ecf1  xor     rax, rsp
0x14000ecf4  mov     [rsp+2E8h+var_30], rax
0x14000ecfc  mov     r8, rdx
0x14000ecff  mov     [rsp+2E8h+Irp], rdx
0x14000ed04  mov     r13, rcx
0x14000ed07  mov     [rsp+2E8h+var_290], rdx
0x14000ed0c  xor     edi, edi
0x14000ed0e  mov     [rsp+2E8h+var_2A4], edi
0x14000ed12  mov     r12d, edi
0x14000ed15  mov     r11, [rdx+0B8h]
0x14000ed1c  mov     edx, [r11+10h]
0x14000ed20  mov     r15d, [r11+8]
0x14000ed24  test    edx, edx
0x14000ed26  jz      short loc_14000ED2E
0x14000ed28  mov     rbx, [r8+18h]
0x14000ed2c  jmp     short loc_14000ED31
0x14000ed2e  mov     rbx, rdi
0x14000ed31  test    r15d, r15d
0x14000ed34  jz      short loc_14000ED3C
0x14000ed36  mov     rsi, [r8+18h]
0x14000ed3a  jmp     short loc_14000ED3F
0x14000ed3c  mov     rsi, rdi
0x14000ed3f  lea     rcx, [r11+18h]
0x14000ed43  mov     [rsp+2E8h+var_288], rcx
0x14000ed48  mov     ecx, [rcx]
0x14000ed4a  mov     eax, 228044h
0x14000ed4f  cmp     ecx, eax
0x14000ed51  ja      loc_14000F2CC
0x14000ed57  jz      loc_14000F275
0x14000ed5d  mov     eax, 22800Ch
0x14000ed62  cmp     ecx, eax
0x14000ed64  ja      loc_14000F04F
0x14000ed6a  jz      loc_14000F016
0x14000ed70  mov     r13, [r13+40h]
0x14000ed74  mov     eax, ecx
0x14000ed76  sub     eax, 223FECh
0x14000ed7b  jz      loc_14000F008
0x14000ed81  sub     eax, 5
0x14000ed84  jz      loc_14000EF6C
0x14000ed8a  sub     eax, 3
0x14000ed8d  mov     r14d, 4
0x14000ed93  jz      loc_14000EF0A
0x14000ed99  sub     eax, r14d
0x14000ed9c  jz      loc_14000EED7
0x14000eda2  sub     eax, r14d
0x14000eda5  jz      loc_14000EE5B
0x14000edab  cmp     eax, 400Ch
0x14000edb0  jnz     loc_14000F758
0x14000edb6  cmp     edx, 8
0x14000edb9  jz      short loc_14000EDC5
0x14000edbb  mov     ebx, 0C000000Dh
0x14000edc0  mov     rsi, r8
0x14000edc3  jmp     short loc_14000EDE6
0x14000edc5  mov     rcx, [r8+18h]
0x14000edc9  mov     edx, [rcx+4]
0x14000edcc  movzx   ecx, word ptr [rcx]
0x14000edcf  call    cs:__imp_WinHvConfigureProfiler
0x14000edd6  nop     dword ptr [rax+rax+00h]
0x14000eddb  mov     ebx, eax
0x14000eddd  mov     rsi, [rsp+2E8h+Irp]
0x14000ede2  test    ebx, ebx
0x14000ede4  jns     short loc_14000EE10
0x14000ede6  mov     [rsp+2E8h+Priority], ebx
0x14000edea  mov     rax, [rsp+2E8h+var_288]
0x14000edef  mov     eax, [rax]
0x14000edf1  mov     [rsp+2E8h+BugCheckOnFailure], eax
0x14000edf5  lea     r9, aIoctl0xXFailed; "IOCTL 0x%x failed with 0x%x"
0x14000edfc  mov     r8d, 4E4h
0x14000ee02  lea     rdx, aHbiodispatchio; "HbIoDispatchIoctl"
0x14000ee09  xor     ecx, ecx
0x14000ee0b  call    HbpTraceEvent
0x14000ee10  mov     eax, r12d
0x14000ee13  mov     [rsi+38h], rax
0x14000ee17  mov     [rsi+30h], ebx
0x14000ee1a  xor     edx, edx; PriorityBoost
0x14000ee1c  mov     rcx, rsi; Irp
0x14000ee1f  call    cs:__imp_IofCompleteRequest
0x14000ee26  nop     dword ptr [rax+rax+00h]
0x14000ee2b  mov     eax, ebx
0x14000ee2d  mov     rcx, [rsp+2E8h+var_30]
0x14000ee35  xor     rcx, rsp; StackCookie
0x14000ee38  call    __security_check_cookie
0x14000ee3d  lea     r11, [rsp+2E8h+var_28]
0x14000ee45  mov     rbx, [r11+40h]
0x14000ee49  mov     rsi, [r11+48h]
0x14000ee4d  mov     rsp, r11
0x14000ee50  pop     r15
0x14000ee52  pop     r14
0x14000ee54  pop     r13
0x14000ee56  pop     r12
0x14000ee58  pop     rdi
0x14000ee59  retn
0x14000ee5b  cmp     r15d, 8
0x14000ee5f  jb      loc_14000EDBB
0x14000ee65  test    rsi, rsi
0x14000ee68  jz      loc_14000EDBB
0x14000ee6e  cmp     edx, 8
0x14000ee71  jb      loc_14000EDBB
0x14000ee77  test    rbx, rbx
0x14000ee7a  jz      loc_14000EDBB
0x14000ee80  mov     [rsp+2E8h+var_2B0], rdi
0x14000ee85  mov     r8d, [rbx]
0x14000ee88  lea     eax, [r8-1]
0x14000ee8c  cmp     eax, 9
0x14000ee8f  ja      short loc_14000EEC8
0x14000ee91  lea     rax, [rsp+2E8h+var_2B0]
0x14000ee96  mov     qword ptr [rsp+2E8h+BugCheckOnFailure], rax
0x14000ee9b  mov     r9d, [rbx+4]
0x14000ee9f  mov     rdx, [r11+30h]
0x14000eea3  mov     rcx, r13
0x14000eea6  call    HvStatsMapHvStatsPage
0x14000eeab  mov     ebx, eax
0x14000eead  test    eax, eax
0x14000eeaf  js      loc_14000EDDD
0x14000eeb5  mov     rax, [rsp+2E8h+var_2B0]
0x14000eeba  mov     [rsi], rax
0x14000eebd  mov     r12d, 8
0x14000eec3  jmp     loc_14000EDDD
0x14000eec8  mov     ebx, 0C000000Dh
0x14000eecd  mov     rsi, [rsp+2E8h+Irp]
0x14000eed2  jmp     loc_14000EDE6
0x14000eed7  cmp     edx, 8
0x14000eeda  jb      loc_14000EDBB
0x14000eee0  test    rbx, rbx
0x14000eee3  jz      loc_14000EDBB
0x14000eee9  mov     r8d, [rbx]
0x14000eeec  lea     eax, [r8-1]
0x14000eef0  cmp     eax, 9
0x14000eef3  ja      short loc_14000EEC8
0x14000eef5  mov     r9d, [rbx+4]
0x14000eef9  mov     rdx, [r11+30h]
0x14000eefd  mov     rcx, r13
0x14000ef00  call    HvStatsUnmapHvStatsPage
0x14000ef05  jmp     loc_14000EDDB
0x14000ef0a  cmp     r15d, r14d
0x14000ef0d  jb      short loc_14000EF5F
0x14000ef0f  test    rsi, rsi
0x14000ef12  jz      short loc_14000EF5F
0x14000ef14  mov     [rsp+2E8h+var_2A8], edi
0x14000ef18  cmp     cs:HbpIsCpuManagementPartition, dil
0x14000ef1f  jz      short loc_14000EF42
0x14000ef21  lea     rcx, [rsp+2E8h+var_2A8]
0x14000ef26  call    cs:__imp_HvlQueryActiveHypervisorProcessorCount
0x14000ef2d  nop     dword ptr [rax+rax+00h]
0x14000ef32  mov     ebx, eax
0x14000ef34  test    eax, eax
0x14000ef36  js      loc_14000EDDD
0x14000ef3c  mov     eax, [rsp+2E8h+var_2A8]
0x14000ef40  jmp     short loc_14000EF55
0x14000ef42  mov     ecx, 0FFFFh; GroupNumber
0x14000ef47  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14000ef4e  nop     dword ptr [rax+rax+00h]
0x14000ef53  mov     ebx, edi
0x14000ef55  mov     [rsi], eax
0x14000ef57  mov     r12d, r14d
0x14000ef5a  jmp     loc_14000EDDD
0x14000ef5f  mov     ebx, 0C0000023h
0x14000ef64  mov     rsi, r8
0x14000ef67  jmp     loc_14000EDE2
0x14000ef6c  mov     r12d, 10h
0x14000ef72  cmp     edx, r12d
0x14000ef75  jb      loc_14000EFFE
0x14000ef7b  test    rbx, rbx
0x14000ef7e  jz      short loc_14000EFFE
0x14000ef80  cmp     r15d, [rbx+0Ch]
0x14000ef84  jb      short loc_14000EFFE
0x14000ef86  test    r15d, r15d
0x14000ef89  jz      short loc_14000EFFE
0x14000ef8b  mov     rcx, [r8+8]; MemoryDescriptorList
0x14000ef8f  test    byte ptr [rcx+0Ah], 5
0x14000ef93  jz      short loc_14000EF9B
0x14000ef95  mov     r9, [rcx+18h]
0x14000ef99  jmp     short loc_14000EFBF
0x14000ef9b  mov     [rsp+2E8h+Priority], 0C0000010h; Priority
0x14000efa3  mov     [rsp+2E8h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14000efa7  xor     r9d, r9d; RequestedAddress
0x14000efaa  xor     edx, edx; AccessMode
0x14000efac  lea     r8d, [r9+1]; CacheType
0x14000efb0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000efb7  nop     dword ptr [rax+rax+00h]
0x14000efbc  mov     r9, rax
0x14000efbf  test    r9, r9
0x14000efc2  jnz     short loc_14000EFCE
0x14000efc4  mov     ebx, 0C000009Ah
0x14000efc9  jmp     loc_14000EECD
0x14000efce  mov     eax, [rbx+0Ch]
0x14000efd1  mov     [rsp+2E8h+BugCheckOnFailure], eax
0x14000efd5  mov     r8d, [rbx+8]
0x14000efd9  mov     edx, [rbx+4]
0x14000efdc  mov     cl, [rbx]
0x14000efde  call    cs:__imp_WinHvUpdateSecFw
0x14000efe5  nop     dword ptr [rax+rax+00h]
0x14000efea  mov     ebx, eax
0x14000efec  test    eax, eax
0x14000efee  js      loc_14000EDDD
0x14000eff4  call    HbEvtpLogSecFwStatus
0x14000eff9  jmp     loc_14000EDDD
0x14000effe  mov     ebx, 0C0000023h
0x14000f003  jmp     loc_14000EDC0
0x14000f008  call    cs:__imp_WinHvCommitSecFwSvn
0x14000f00f  nop     dword ptr [rax+rax+00h]
0x14000f014  jmp     short loc_14000EFEA
0x14000f016  test    edx, edx
0x14000f018  jnz     loc_14000EDBB
0x14000f01e  test    r15d, r15d
0x14000f021  jnz     loc_14000EDBB
0x14000f027  lea     edx, [r15+1]
0x14000f02b  xor     ecx, ecx
0x14000f02d  call    cs:__imp_WinHvUpdateHvProcessorFeatures
0x14000f034  nop     dword ptr [rax+rax+00h]
0x14000f039  mov     ebx, eax
0x14000f03b  test    eax, eax
0x14000f03d  js      loc_14000EDDD
0x14000f043  mov     cl, 1
0x14000f045  call    HbEvtpLogProcessorFeatures
0x14000f04a  jmp     loc_14000EDDD
0x14000f04f  mov     eax, ecx
0x14000f051  sub     eax, 228010h
0x14000f056  jz      loc_14000F209
0x14000f05c  sub     eax, 18h
0x14000f05f  jz      loc_14000F1B0
0x14000f065  mov     r10d, 0Ch
0x14000f06b  sub     eax, r10d
0x14000f06e  jz      loc_14000F187
0x14000f074  lea     r14d, [r10-8]
0x14000f078  sub     eax, r14d
0x14000f07b  jz      loc_14000F120
0x14000f081  sub     eax, r14d
0x14000f084  jz      short loc_14000F0F2
0x14000f086  cmp     eax, r14d
0x14000f089  jnz     loc_14000F758
0x14000f08f  xor     eax, eax
0x14000f091  mov     qword ptr [rsp+2E8h+var_278], rax
0x14000f096  mov     dword ptr [rsp+2E8h+var_278+8], eax
0x14000f09a  mov     r12d, r10d
0x14000f09d  cmp     r15d, r10d
0x14000f0a0  jb      loc_14000EFFE
0x14000f0a6  test    rsi, rsi
0x14000f0a9  jz      loc_14000EFFE
0x14000f0af  mov     qword ptr [rsp+2E8h+Priority], rdi
0x14000f0b4  mov     [rsp+2E8h+BugCheckOnFailure], r10d
0x14000f0b9  lea     r9, [rsp+2E8h+var_278]
0x14000f0be  xor     r8d, r8d
0x14000f0c1  xor     edx, edx
0x14000f0c3  lea     ecx, [rax+0Ah]
0x14000f0c6  call    cs:__imp_WinHvGetSystemInformation
0x14000f0cd  nop     dword ptr [rax+rax+00h]
0x14000f0d2  mov     ebx, eax
0x14000f0d4  test    eax, eax
0x14000f0d6  js      loc_14000EDDD
0x14000f0dc  movsd   xmm0, qword ptr [rsp+2E8h+var_278]
0x14000f0e2  movsd   qword ptr [rsi], xmm0
0x14000f0e6  mov     eax, dword ptr [rsp+2E8h+var_278+8]
0x14000f0ea  mov     [rsi+8], eax
0x14000f0ed  jmp     loc_14000EDDD
0x14000f0f2  cmp     edx, r14d
0x14000f0f5  jb      loc_14000EDBB
0x14000f0fb  test    rbx, rbx
0x14000f0fe  jz      loc_14000EDBB
0x14000f104  mov     r8d, r14d
0x14000f107  mov     ecx, 0Ah
0x14000f10c  mov     rdx, rbx
0x14000f10f  call    cs:__imp_WinHvSetSystemInformation
0x14000f116  nop     dword ptr [rax+rax+00h]
0x14000f11b  jmp     loc_14000EDDB
0x14000f120  cmp     edx, r14d
0x14000f123  jb      loc_14000EDBB
0x14000f129  test    rbx, rbx
0x14000f12c  jz      loc_14000EDBB
0x14000f132  cmp     r15d, 8
0x14000f136  jb      loc_14000EDBB
0x14000f13c  test    rsi, rsi
0x14000f13f  jz      loc_14000EDBB
0x14000f145  lea     rax, [rsp+2E8h+var_2A4]
0x14000f14a  mov     qword ptr [rsp+2E8h+Priority], rax
0x14000f14f  mov     [rsp+2E8h+BugCheckOnFailure], r15d
0x14000f154  mov     r9, rsi
0x14000f157  mov     r8d, r14d
0x14000f15a  mov     rdx, rbx
0x14000f15d  mov     ecx, 3
0x14000f162  call    cs:__imp_WinHvGetSystemInformation
0x14000f169  nop     dword ptr [rax+rax+00h]
0x14000f16e  mov     ebx, eax
0x14000f170  mov     rsi, [rsp+2E8h+Irp]
0x14000f175  test    eax, eax
0x14000f177  js      loc_14000EDE2
0x14000f17d  mov     r12d, [rsp+2E8h+var_2A4]
0x14000f182  jmp     loc_14000EDE2
0x14000f187  cmp     edx, 10h
0x14000f18a  jb      loc_14000EDBB
0x14000f190  test    rbx, rbx
  ... truncated ...
```
