# PmFilterDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400068b0`
- end: `0x1400070cd`
- name: `?PmFilterDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2077`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `38`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400068b0`
- `0x14000a014`
- `0x14001c0e0`
- `0x14001d6a4`
- `0x14001d744`
- `0x14001d7cc`
- `0x14001d830`
- `0x14001d9ec`
- `0x14001da78`
- `0x14001dc08`
- `0x14001dd8c`
- `0x14001de70`
- `0x14001dfcc`
- `0x14001e068`
- `0x14001e19c`
- `0x14001e2bc`
- `0x14001e3dc`
- `0x14001eba4`
- `0x14001ebd8`
- `0x14001ec94`
- `0x14001ed38`
- `0x14001ef24`
- `0x14001ef94`
- `0x14001f014`
- `0x14001f120`
- `0x14001f304`
- `0x14001f510`
- `0x14001f5c4`
- `0x14001f650`
- `0x14001fb44`
- `0x140024214`
- `0x14002454c`
- `0x140024bf8`
- `0x140024f44`
- `0x140024fd4`
- `0x14002589c`
- `0x140025a28`
- `0x140025ab8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400069d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006a8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006bfd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006f9a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400069d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006a8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006bfd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006f9a`
- `ntoskrnl!IofCallDriver` at `0x140006d63`
- `ntoskrnl!IofCallDriver` at `0x140006d63`
- `ntoskrnl!IofCompleteRequest` at `0x140006914`
- `ntoskrnl!IofCompleteRequest` at `0x14000708a`
- `ntoskrnl!IofCompleteRequest` at `0x140006914`
- `ntoskrnl!IofCompleteRequest` at `0x14000708a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400068fa`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400068fa`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400070a2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400070a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006af7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006b08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007028`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006af7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006b08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007028`
- `ntoskrnl!KeReleaseMutex` at `0x140006a12`
- `ntoskrnl!KeReleaseMutex` at `0x140006aab`
- `ntoskrnl!KeReleaseMutex` at `0x140006b65`
- `ntoskrnl!KeReleaseMutex` at `0x140006b95`
- `ntoskrnl!KeReleaseMutex` at `0x140006c48`
- `ntoskrnl!KeReleaseMutex` at `0x14000703a`
- `ntoskrnl!KeReleaseMutex` at `0x140006a12`
- `ntoskrnl!KeReleaseMutex` at `0x140006aab`
- `ntoskrnl!KeReleaseMutex` at `0x140006b65`
- `ntoskrnl!KeReleaseMutex` at `0x140006b95`
- `ntoskrnl!KeReleaseMutex` at `0x140006c48`
- `ntoskrnl!KeReleaseMutex` at `0x14000703a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006acd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ff1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006acd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ff1`

## pseudocode

```c
__int64 __fastcall PmFilterDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _IO_REMOVE_LOCK *v5; // r12
  int v7; // eax
  struct _IRP *v8; // rdx
  unsigned int v9; // edi
  unsigned int LowPart; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int ReliabilityInfo; // eax
  signed int Property; // esi
  struct _KMUTANT *v17; // rbx
  struct _IRP *MasterIrp; // r14
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  char *v22; // rbx
  struct _KMUTANT *v23; // rdi
  char v24; // r15
  KIRQL v25; // al
  KSPIN_LOCK *v26; // rcx
  KIRQL v27; // dl
  struct _LIST_ENTRY *v28; // rbx
  struct _LIST_ENTRY *Blink; // rcx
  int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  bool v37; // zf
  unsigned int v38; // eax
  bool v39; // zf
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  char *v54; // r14
  KIRQL v55; // bl
  unsigned __int8 v56; // [rsp+60h] [rbp+8h] BYREF

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  v5 = (struct _IO_REMOVE_LOCK *)(DeviceExtension + 120);
  v7 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, File, 1u, 0x20u);
  v9 = v7;
  if ( v7 < 0 )
  {
    a2->IoStatus.Status = v7;
    IofCompleteRequest(a2, 0);
    return v9;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart > 0x7421C )
  {
    if ( LowPart > 0x700010 )
    {
      v31 = LowPart - 7340052;
      if ( !v31 )
      {
        ReliabilityInfo = PmIoctlGetReliabilityInfo(a1, a2);
        goto LABEL_142;
      }
      v32 = v31 - 49156;
      if ( !v32 )
      {
        ReliabilityInfo = PmIoctlResetReliabilityInfo(a1, v8);
        goto LABEL_142;
      }
      if ( v32 == 24 )
      {
        Property = -1073741637;
        goto LABEL_143;
      }
      goto LABEL_62;
    }
    switch ( LowPart )
    {
      case 0x700010u:
        ReliabilityInfo = PmIoctlQueryDeviceState(a1, a2);
        goto LABEL_142;
      case 0x7C064u:
        Property = -1073741808;
        goto LABEL_143;
      case 0x7C0F4u:
        PmEtwControlStart((struct _DEVICE_EXTENSION *)DeviceExtension, a2);
        v30 = PmIoctlSetDiskAttributes(a1, a2);
LABEL_56:
        Property = v30;
        PmEtwControlComplete((struct _DEVICE_EXTENSION *)DeviceExtension, a2, v30);
        goto LABEL_143;
    }
    if ( LowPart != 2954240 )
    {
      if ( LowPart != 5636144 )
      {
LABEL_62:
        v33 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        if ( (*((_QWORD *)DeviceExtension + 66) & 0x40) != 0 )
        {
          if ( v33 > 0x7C0D0 )
          {
            if ( v33 <= 0x704008 )
            {
              if ( v33 == 7356424 )
                goto LABEL_85;
              v41 = v33 - 508160;
              if ( !v41 )
                goto LABEL_85;
              v42 = v41 - 268;
              if ( !v42 )
                goto LABEL_85;
              v43 = v42 - 4;
              if ( !v43 )
                goto LABEL_85;
              v37 = v43 == 2478580;
              goto LABEL_83;
            }
            v44 = v33 - 7389212;
            if ( !v44 )
              goto LABEL_85;
            v40 = v44 - 4;
            v39 = v40 == 0;
          }
          else
          {
            if ( v33 == 508112 )
              goto LABEL_85;
            if ( v33 <= 0x74208 )
            {
              if ( v33 != 475656 )
              {
                v34 = v33 - 458824;
                if ( v34 )
                {
                  v35 = v34 - 8;
                  if ( v35 )
                  {
                    v36 = v35 - 240;
                    if ( v36 )
                    {
                      v37 = v36 == 16076;
                      goto LABEL_83;
                    }
                  }
                }
              }
LABEL_85:
              Property = -1073741790;
              goto LABEL_143;
            }
            v38 = v33 - 507920;
            if ( !v38 )
              goto LABEL_85;
            v40 = v38 - 68;
            v39 = v40 == 0;
          }
          if ( v39 )
            goto LABEL_85;
          v37 = v40 == 4;
LABEL_83:
          if ( !v37 )
          {
LABEL_84:
            ++a2->CurrentLocation;
            ++a2->Tail.Overlay.CurrentStackLocation;
            Property = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
            goto LABEL_144;
          }
          goto LABEL_85;
        }
        if ( v33 <= 0x7C054 )
        {
          if ( v33 == 507988 )
          {
            ReliabilityInfo = PmIoctlSetDriveLayoutEx(a1, a2);
            goto LABEL_142;
          }
          if ( v33 <= 0x70048 )
          {
            if ( v33 != 458824 )
            {
              switch ( v33 )
              {
                case 0x4D004u:
                case 0x4D014u:
                case 0x4D02Cu:
                case 0x4D030u:
                case 0x4D044u:
                case 0x4D048u:
                  Property = PmIoctlRedirect(a1, a2);
                  break;
                default:
                  goto LABEL_84;
              }
              goto LABEL_144;
            }
            ReliabilityInfo = PmIoctlGetPartitionInfoEx(a1, a2);
            goto LABEL_142;
          }
          if ( v33 > 0x7400C )
          {
            if ( v33 == 475656 )
            {
              ReliabilityInfo = PmIoctlGetSnapshotInfo(a1, a2);
              goto LABEL_142;
            }
            if ( v33 == 507920 )
            {
              ReliabilityInfo = PmIoctlSetDriveLayout(a1, a2);
              goto LABEL_142;
            }
          }
          else
          {
            if ( v33 == 475148 )
            {
              ReliabilityInfo = PmIoctlGetDriveLayout(a1, a2);
              goto LABEL_142;
            }
            v45 = v33 - 458832;
            if ( !v45 )
            {
              ReliabilityInfo = PmIoctlGetDriveLayoutEx(a1, a2);
              goto LABEL_142;
            }
            v46 = v45 - 80;
            if ( !v46 )
            {
              ReliabilityInfo = PmIoctlGetDriveGeometryEx(a1, a2);
              goto LABEL_142;
            }
            if ( v46 == 160 )
            {
              ReliabilityInfo = PmIoctlUpdateProperties(a1, v8);
              goto LABEL_142;
            }
          }
          goto LABEL_84;
        }
        if ( v33 > 0x7C218 )
        {
          v50 = v33 - 2987012;
          if ( !v50 )
          {
            Property = PmIoctlDsm(a1, a2);
            goto LABEL_144;
          }
          v51 = v50 - 4369412;
          if ( !v51 )
          {
            ReliabilityInfo = PmIoctlQueryDiskSignature(a1, a2);
            goto LABEL_142;
          }
          v52 = v51 - 32788;
          if ( !v52 )
          {
            v54 = (char *)a1->DeviceExtension;
            v56 = 0;
            KeWaitForSingleObject(v54 + 56, Executive, 0, 0, 0);
            if ( v54[604] )
            {
              Property = -1073741637;
            }
            else
            {
              *((GUID *)v54 + 34) = GUID_NULL;
              Property = PmAttributesPhase1((struct _DEVICE_EXTENSION *)v54, &v56);
              if ( Property >= 0 )
              {
                if ( !v56 || (Property = PmAttributesPhase2((struct _DEVICE_EXTENSION *)v54), Property >= 0) )
                {
                  v55 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v54 + 14);
                  *((_DWORD *)v54 + 129) |= 0x200000u;
                  PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)v54, "PmIoctlReauctionDisk");
                  KeReleaseSpinLock((PKSPIN_LOCK)v54 + 14, v55);
                }
              }
            }
            KeReleaseMutex((PRKMUTEX)v54 + 1, 0);
            goto LABEL_143;
          }
          v53 = v52 - 4;
          if ( !v53 )
          {
            ReliabilityInfo = PmIoctlCreateSpacesMetadata(a1, a2);
            goto LABEL_142;
          }
          if ( v53 == 4 )
          {
            ReliabilityInfo = PmIoctlDeleteSpacesMetadata(a1, v8);
            goto LABEL_142;
          }
          goto LABEL_84;
        }
        if ( v33 != 508440 )
        {
          if ( v33 > 0x7C100 )
          {
            v49 = v33 - 508428;
            if ( !v49 )
            {
              ReliabilityInfo = PmIoctlSetSnapshotInfo(a1, a2);
              goto LABEL_142;
            }
            if ( v49 == 4 )
            {
              ReliabilityInfo = PmIoctlResetSnapshotInfo(a1, v8);
              goto LABEL_142;
            }
          }
          else
          {
            if ( v33 == 508160 )
            {
              ReliabilityInfo = PmIoctlDeleteDriveLayout(a1, v8);
              goto LABEL_142;
            }
            v47 = v33 - 507992;
            if ( !v47 )
            {
              ReliabilityInfo = PmIoctlCreateDisk(a1, a2);
              goto LABEL_142;
            }
            v48 = v47 - 112;
            if ( !v48 )
            {
              ReliabilityInfo = PmIoctlUpdateDriveSize(a1, a2);
              goto LABEL_142;
            }
            if ( v48 == 8 )
            {
              ReliabilityInfo = PmIoctlGrowPartition(a1, a2);
              goto LABEL_142;
            }
          }
          goto LABEL_84;
        }
        PmEtwControlStart((struct _DEVICE_EXTENSION *)DeviceExtension, a2);
        v30 = PmIoctlSetClusterInfo(a1, a2);
        goto LABEL_56;
      }
      v22 = (char *)a1->DeviceExtension;
      KeWaitForSingleObject(v22 + 56, Executive, 0, 0, 0);
      if ( *((_QWORD *)v22 + 68) == CLUSDISK_OWNER_GUID && *((_QWORD *)v22 + 69) == 0xAFD277CBD217D7BFuLL )
        Property = (*((_DWORD *)v22 + 129) & 0x10) != 0 ? 0xC0000001 : 0;
      else
        Property = -1073741823;
LABEL_28:
      KeReleaseMutex((PRKMUTEX)v22 + 1, 0);
LABEL_143:
      a2->IoStatus.Status = Property;
      IofCompleteRequest(a2, 0);
      goto LABEL_144;
    }
    Property = PmIoctlQueryProperty(a1, a2);
  }
  else
  {
    if ( LowPart != 475676 )
    {
      if ( LowPart > 0x700F8 )
      {
        v20 = LowPart - 459284;
        if ( !v20 )
        {
          ReliabilityInfo = PmIoctlGetClusterInfo(a1, a2);
          goto LABEL_142;
        }
        v21 = v20 - 16;
        if ( !v21 )
        {
          ReliabilityInfo = PmIoctlGetPerformanceInfo(a1, a2);
          goto LABEL_142;
        }
        if ( v21 == 15840 )
        {
          ReliabilityInfo = PmIoctlGetPartitionInfo(a1, a2);
          goto LABEL_142;
        }
      }
      else
      {
        if ( LowPart == 459000 )
        {
          if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length )
          {
            v17 = (struct _KMUTANT *)a1->DeviceExtension;
            MasterIrp = a2->AssociatedIrp.MasterIrp;
            Property = 0;
            KeWaitForSingleObject(&v17[1], Executive, 0, 0, 0);
            v19 = (__int64)v17[9].OwnerThread - CLUSDISK_OWNER_GUID;
            if ( !v19 )
              v19 = *(_QWORD *)&v17[9].Abandoned + 0x502D88342DE82841LL;
            LOBYTE(MasterIrp->Type) = v19 == 0;
            KeReleaseMutex(v17 + 1, 0);
            a2->IoStatus.Information = 1;
          }
          else
          {
            Property = -1073741789;
          }
          goto LABEL_143;
        }
        v12 = LowPart - 458784;
        if ( !v12 )
        {
          ReliabilityInfo = PmIoctlPerformance(a1, a2);
          goto LABEL_142;
        }
        v13 = v12 - 4;
        if ( !v13 )
        {
          ReliabilityInfo = PmIoctlIsWritable(a1, a2);
          goto LABEL_142;
        }
        v14 = v13 - 60;
        if ( !v14 )
        {
          ReliabilityInfo = PmIoctlPerformanceOff(a1, v8);
          goto LABEL_142;
        }
        if ( v14 == 144 )
        {
          ReliabilityInfo = PmIoctlGetDiskAttributes(a1, a2);
LABEL_142:
          Property = ReliabilityInfo;
          goto LABEL_143;
        }
      }
      goto LABEL_62;
    }
    v22 = (char *)a1->DeviceExtension;
    v23 = (struct _KMUTANT *)(v22 + 56);
    KeWaitForSingleObject(v22 + 56, Executive, 0, 0, 0);
    if ( (*((_QWORD *)v22 + 66) & 1) != 0 )
    {
      Property = -2147483632;
      goto LABEL_28;
    }
    v24 = 0;
    if ( !*((_DWORD *)v22 + 220) )
    {
      v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v22 + 14);
      v26 = (KSPIN_LOCK *)(v22 + 112);
      if ( v22[816] )
      {
        v27 = v25;
      }
      else
      {
        v27 = v25;
        if ( (*((_DWORD *)v22 + 129) & 0x24) != 0 )
        {
          Property = 0;
          KeReleaseSpinLock(v26, v25);
          goto LABEL_28;
        }
      }
      KeReleaseSpinLock(v26, v27);
    }
    v28 = (struct _LIST_ENTRY *)(v22 + 864);
    Blink = v28->Blink;
    if ( Blink->Flink != v28 )
      __fastfail(3u);
    a2->Tail.Overlay.ListEntry.Flink = v28;
    a2->Tail.Overlay.ListEntry.Blink = Blink;
    Blink->Flink = &a2->Tail.Overlay.ListEntry;
    v28->Blink = &a2->Tail.Overlay.ListEntry;
    _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)PmAreVolumesReadyCancelRoutine);
    if ( a2->Cancel )
    {
      if ( !_InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, 0) )
      {
        Property = 0;
        KeReleaseMutex(v23, 0);
        goto LABEL_144;
      }
      Property = -1073741536;
      v24 = 1;
    }
    else
    {
      Property = 259;
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    }
    KeReleaseMutex(v23, 0);
    if ( v24 )
      goto LABEL_143;
  }
LABEL_144:
  IoReleaseRemoveLockEx(v5, a2, 0x20u);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400068b0  mov     [rsp+arg_10], rbx
0x1400068b5  mov     [rsp+arg_18], rbp
0x1400068ba  push    rsi
0x1400068bb  push    rdi
0x1400068bc  push    r12
0x1400068be  push    r13
0x1400068c0  push    r14
0x1400068c2  sub     rsp, 30h
0x1400068c6  mov     r14, [rcx+40h]
0x1400068ca  lea     r8, File; File
0x1400068d1  mov     rsi, [rdx+0B8h]
0x1400068d8  mov     rbx, rcx
0x1400068db  xor     r13d, r13d
0x1400068de  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x1400068e6  mov     r9d, 1; Line
0x1400068ec  mov     [rdx+38h], r13
0x1400068f0  lea     r12, [r14+78h]
0x1400068f4  mov     rbp, rdx
0x1400068f7  mov     rcx, r12; RemoveLock
0x1400068fa  call    cs:__imp_IoAcquireRemoveLockEx
0x140006901  nop     dword ptr [rax+rax+00h]
0x140006906  mov     edi, eax
0x140006908  test    eax, eax
0x14000690a  jns     short loc_140006927
0x14000690c  xor     edx, edx; PriorityBoost
0x14000690e  mov     [rbp+30h], eax
0x140006911  mov     rcx, rbp; Irp
0x140006914  call    cs:__imp_IofCompleteRequest
0x14000691b  nop     dword ptr [rax+rax+00h]
0x140006920  mov     eax, edi
0x140006922  jmp     loc_1400070B5
0x140006927  mov     eax, [rsi+18h]
0x14000692a  mov     [rsp+58h+arg_8], r15
0x14000692f  cmp     eax, 7421Ch
0x140006934  ja      loc_140006BAF
0x14000693a  jz      loc_140006A72
0x140006940  cmp     eax, 700F8h
0x140006945  ja      loc_140006A2B
0x14000694b  jz      short loc_1400069A6
0x14000694d  sub     eax, 70020h
0x140006952  jz      short loc_140006996
0x140006954  sub     eax, 4
0x140006957  jz      short loc_140006986
0x140006959  sub     eax, 3Ch ; '<'
0x14000695c  jz      short loc_140006979
0x14000695e  cmp     eax, 90h
0x140006963  jnz     loc_140006CCF
0x140006969  mov     rdx, rbp; struct _IRP *
0x14000696c  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x14000696f  call    ?PmIoctlGetDiskAttributes@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlGetDiskAttributes(_DEVICE_OBJECT *,_IRP *)
0x140006974  jmp     loc_140007080
0x140006979  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x14000697c  call    ?PmIoctlPerformanceOff@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlPerformanceOff(_DEVICE_OBJECT *,_IRP *)
0x140006981  jmp     loc_140007080
0x140006986  mov     rdx, rbp; struct _IRP *
0x140006989  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x14000698c  call    ?PmIoctlIsWritable@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlIsWritable(_DEVICE_OBJECT *,_IRP *)
0x140006991  jmp     loc_140007080
0x140006996  mov     rdx, rbp; struct _IRP *
0x140006999  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x14000699c  call    ?PmIoctlPerformance@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlPerformance(_DEVICE_OBJECT *,_IRP *)
0x1400069a1  jmp     loc_140007080
0x1400069a6  mov     rax, [rbp+0B8h]
0x1400069ad  cmp     dword ptr [rax+8], 1
0x1400069b1  jnb     short loc_1400069BD
0x1400069b3  mov     esi, 0C0000023h
0x1400069b8  jmp     loc_140007082
0x1400069bd  mov     rbx, [rbx+40h]
0x1400069c1  xor     r9d, r9d; Alertable
0x1400069c4  mov     r14, [rbp+18h]
0x1400069c8  xor     r8d, r8d; WaitMode
0x1400069cb  xor     edx, edx; WaitReason
0x1400069cd  mov     qword ptr [rsp+58h+RemlockSize], r13; Timeout
0x1400069d2  mov     esi, r13d
0x1400069d5  lea     rcx, [rbx+38h]; Object
0x1400069d9  call    cs:__imp_KeWaitForSingleObject
0x1400069e0  nop     dword ptr [rax+rax+00h]
0x1400069e5  mov     rax, [rbx+220h]
0x1400069ec  sub     rax, cs:CLUSDISK_OWNER_GUID
0x1400069f3  jnz     short loc_140006A03
0x1400069f5  mov     rax, [rbx+228h]
0x1400069fc  sub     rax, cs:qword_140013998
0x140006a03  test    rax, rax
0x140006a06  lea     rcx, [rbx+38h]; Mutex
0x140006a0a  setz    al
0x140006a0d  xor     edx, edx; Wait
0x140006a0f  mov     [r14], al
0x140006a12  call    cs:__imp_KeReleaseMutex
0x140006a19  nop     dword ptr [rax+rax+00h]
0x140006a1e  mov     qword ptr [rbp+38h], 1
0x140006a26  jmp     loc_140007082
0x140006a2b  sub     eax, 70214h
0x140006a30  jz      short loc_140006A62
0x140006a32  sub     eax, 10h
0x140006a35  jz      short loc_140006A52
0x140006a37  cmp     eax, 3DE0h
0x140006a3c  jnz     loc_140006CCF
0x140006a42  mov     rdx, rbp; struct _IRP *
0x140006a45  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006a48  call    ?PmIoctlGetPartitionInfo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlGetPartitionInfo(_DEVICE_OBJECT *,_IRP *)
0x140006a4d  jmp     loc_140007080
0x140006a52  mov     rdx, rbp; struct _IRP *
0x140006a55  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006a58  call    ?PmIoctlGetPerformanceInfo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlGetPerformanceInfo(_DEVICE_OBJECT *,_IRP *)
0x140006a5d  jmp     loc_140007080
0x140006a62  mov     rdx, rbp; struct _IRP *
0x140006a65  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006a68  call    ?PmIoctlGetClusterInfo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlGetClusterInfo(_DEVICE_OBJECT *,_IRP *)
0x140006a6d  jmp     loc_140007080
0x140006a72  mov     rbx, [rbx+40h]
0x140006a76  xor     r9d, r9d; Alertable
0x140006a79  xor     r8d, r8d; WaitMode
0x140006a7c  mov     qword ptr [rsp+58h+RemlockSize], r13; Timeout
0x140006a81  xor     edx, edx; WaitReason
0x140006a83  lea     rdi, [rbx+38h]
0x140006a87  mov     rcx, rdi; Object
0x140006a8a  call    cs:__imp_KeWaitForSingleObject
0x140006a91  nop     dword ptr [rax+rax+00h]
0x140006a96  mov     rax, [rbx+210h]
0x140006a9d  test    al, 1
0x140006a9f  jz      short loc_140006ABC
0x140006aa1  mov     esi, 80000010h
0x140006aa6  xor     edx, edx; Wait
0x140006aa8  mov     rcx, rdi; Mutex
0x140006aab  call    cs:__imp_KeReleaseMutex
0x140006ab2  nop     dword ptr [rax+rax+00h]
0x140006ab7  jmp     loc_140007082
0x140006abc  mov     eax, [rbx+370h]
0x140006ac2  xor     r15b, r15b
0x140006ac5  test    eax, eax
0x140006ac7  jnz     short loc_140006B14
0x140006ac9  lea     rcx, [rbx+70h]; SpinLock
0x140006acd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006ad4  nop     dword ptr [rax+rax+00h]
0x140006ad9  lea     rcx, [rbx+70h]; SpinLock
0x140006add  cmp     [rbx+330h], r13b
0x140006ae4  jnz     short loc_140006B05
0x140006ae6  mov     edx, [rbx+204h]
0x140006aec  test    dl, 24h
0x140006aef  movzx   edx, al; NewIrql
0x140006af2  jz      short loc_140006B08
0x140006af4  mov     esi, r13d
0x140006af7  call    cs:__imp_KeReleaseSpinLock
0x140006afe  nop     dword ptr [rax+rax+00h]
0x140006b03  jmp     short loc_140006AA6
0x140006b05  movzx   edx, al; NewIrql
0x140006b08  call    cs:__imp_KeReleaseSpinLock
0x140006b0f  nop     dword ptr [rax+rax+00h]
0x140006b14  add     rbx, 360h
0x140006b1b  mov     rcx, [rbx+8]
0x140006b1f  cmp     [rcx], rbx
0x140006b22  jz      short loc_140006B2B
0x140006b24  mov     ecx, 3
0x140006b29  int     29h; Win8: RtlFailFast(ecx)
0x140006b2b  lea     rax, [rbp+0A8h]
0x140006b32  mov     [rax], rbx
0x140006b35  mov     [rax+8], rcx
0x140006b39  mov     [rcx], rax
0x140006b3c  mov     [rbx+8], rax
0x140006b40  lea     rax, ?PmAreVolumesReadyCancelRoutine@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmAreVolumesReadyCancelRoutine(_DEVICE_OBJECT *,_IRP *)
0x140006b47  xchg    rax, [rbp+68h]
0x140006b4b  cmp     [rbp+44h], r13b
0x140006b4f  jz      short loc_140006B80
0x140006b51  mov     rax, r13
0x140006b54  xchg    rax, [rbp+68h]
0x140006b58  test    rax, rax
0x140006b5b  jnz     short loc_140006B76
0x140006b5d  xor     edx, edx; Wait
0x140006b5f  mov     rcx, rdi; Mutex
0x140006b62  mov     esi, r13d
0x140006b65  call    cs:__imp_KeReleaseMutex
0x140006b6c  nop     dword ptr [rax+rax+00h]
0x140006b71  jmp     loc_140007096
0x140006b76  mov     esi, 0C0000120h
0x140006b7b  mov     r15b, 1
0x140006b7e  jmp     short loc_140006B90
0x140006b80  mov     rax, [rbp+0B8h]
0x140006b87  mov     esi, 103h
0x140006b8c  or      byte ptr [rax+3], 1
0x140006b90  xor     edx, edx; Wait
0x140006b92  mov     rcx, rdi; Mutex
0x140006b95  call    cs:__imp_KeReleaseMutex
0x140006b9c  nop     dword ptr [rax+rax+00h]
0x140006ba1  test    r15b, r15b
0x140006ba4  jz      loc_140007096
0x140006baa  jmp     loc_140007082
0x140006baf  cmp     eax, 700010h
0x140006bb4  ja      loc_140006CB0
0x140006bba  jz      loc_140006CA0
0x140006bc0  cmp     eax, 7C064h
0x140006bc5  jz      loc_140006C96
0x140006bcb  cmp     eax, 7C0F4h
0x140006bd0  jz      loc_140006C6B
0x140006bd6  cmp     eax, 2D1400h
0x140006bdb  jz      short loc_140006C59
0x140006bdd  cmp     eax, 560030h
0x140006be2  jnz     loc_140006CCF
0x140006be8  mov     rbx, [rbx+40h]
0x140006bec  xor     r9d, r9d; Alertable
0x140006bef  xor     r8d, r8d; WaitMode
0x140006bf2  mov     qword ptr [rsp+58h+RemlockSize], r13; Timeout
0x140006bf7  xor     edx, edx; WaitReason
0x140006bf9  lea     rcx, [rbx+38h]; Object
0x140006bfd  call    cs:__imp_KeWaitForSingleObject
0x140006c04  nop     dword ptr [rax+rax+00h]
0x140006c09  mov     rax, [rbx+220h]
0x140006c10  cmp     rax, cs:CLUSDISK_OWNER_GUID
0x140006c17  jnz     short loc_140006C3D
0x140006c19  mov     rax, [rbx+228h]
0x140006c20  cmp     rax, cs:qword_140013998
0x140006c27  jnz     short loc_140006C3D
0x140006c29  mov     eax, [rbx+204h]
0x140006c2f  and     al, 10h
0x140006c31  neg     al
0x140006c33  sbb     esi, esi
0x140006c35  and     esi, 0C0000001h
0x140006c3b  jmp     short loc_140006C42
0x140006c3d  mov     esi, 0C0000001h
0x140006c42  xor     edx, edx; Wait
0x140006c44  lea     rcx, [rbx+38h]; Mutex
0x140006c48  call    cs:__imp_KeReleaseMutex
0x140006c4f  nop     dword ptr [rax+rax+00h]
0x140006c54  jmp     loc_140007082
0x140006c59  mov     rdx, rbp; struct _IRP *
0x140006c5c  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006c5f  call    ?PmIoctlQueryProperty@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlQueryProperty(_DEVICE_OBJECT *,_IRP *)
0x140006c64  mov     esi, eax
0x140006c66  jmp     loc_140007096
0x140006c6b  mov     rdx, rbp; struct _IRP *
0x140006c6e  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140006c71  call    ?PmEtwControlStart@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z; PmEtwControlStart(_DEVICE_EXTENSION *,_IRP *)
0x140006c76  mov     rdx, rbp; struct _IRP *
0x140006c79  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006c7c  call    ?PmIoctlSetDiskAttributes@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlSetDiskAttributes(_DEVICE_OBJECT *,_IRP *)
0x140006c81  mov     r8d, eax; int
0x140006c84  mov     rdx, rbp; struct _IRP *
0x140006c87  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140006c8a  mov     esi, eax
0x140006c8c  call    ?PmEtwControlComplete@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@J@Z; PmEtwControlComplete(_DEVICE_EXTENSION *,_IRP *,long)
0x140006c91  jmp     loc_140007082
0x140006c96  mov     esi, 0C0000010h
0x140006c9b  jmp     loc_140007082
0x140006ca0  mov     rdx, rbp; struct _IRP *
0x140006ca3  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006ca6  call    ?PmIoctlQueryDeviceState@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlQueryDeviceState(_DEVICE_OBJECT *,_IRP *)
0x140006cab  jmp     loc_140007080
0x140006cb0  sub     eax, 700014h
0x140006cb5  jz      loc_140007075
0x140006cbb  sub     eax, 0C004h
0x140006cc0  jz      loc_14000706B
0x140006cc6  cmp     eax, 18h
0x140006cc9  jz      loc_140007064
0x140006ccf  mov     rax, [r14+210h]
0x140006cd6  test    al, 40h
0x140006cd8  mov     eax, [rsi+18h]
0x140006cdb  jz      loc_140006D80
0x140006ce1  cmp     eax, 7C0D0h
0x140006ce6  ja      short loc_140006D1D
0x140006ce8  jz      loc_140006D76
0x140006cee  cmp     eax, 74208h
0x140006cf3  ja      short loc_140006D11
0x140006cf5  jz      short loc_140006D76
0x140006cf7  sub     eax, 70048h
0x140006cfc  jz      short loc_140006D76
0x140006cfe  sub     eax, 8
0x140006d01  jz      short loc_140006D76
0x140006d03  sub     eax, 0F0h
0x140006d08  jz      short loc_140006D76
0x140006d0a  cmp     eax, 3ECCh
0x140006d0f  jmp     short loc_140006D4F
0x140006d11  sub     eax, 7C010h
0x140006d16  jz      short loc_140006D76
0x140006d18  sub     eax, 44h ; 'D'
0x140006d1b  jmp     short loc_140006D4A
0x140006d1d  cmp     eax, 704008h
0x140006d22  ja      short loc_140006D40
0x140006d24  jz      short loc_140006D76
0x140006d26  sub     eax, 7C100h
0x140006d2b  jz      short loc_140006D76
0x140006d2d  sub     eax, 10Ch
0x140006d32  jz      short loc_140006D76
0x140006d34  sub     eax, 4
0x140006d37  jz      short loc_140006D76
0x140006d39  cmp     eax, 25D1F4h
0x140006d3e  jmp     short loc_140006D4F
0x140006d40  sub     eax, 70C01Ch
0x140006d45  jz      short loc_140006D76
0x140006d47  sub     eax, 4
0x140006d4a  jz      short loc_140006D76
0x140006d4c  cmp     eax, 4
0x140006d4f  jz      short loc_140006D76
0x140006d51  inc     byte ptr [rbp+43h]; jumptable 0000000140006DBD default case, cases 315397-315411,315413-315435,315437-315439,315441-315459,315461-315463
0x140006d54  mov     rdx, rbp; Irp
0x140006d57  add     qword ptr [rbp+0B8h], 48h ; 'H'
0x140006d5f  mov     rcx, [r14+10h]; DeviceObject
0x140006d63  call    cs:__imp_IofCallDriver
0x140006d6a  nop     dword ptr [rax+rax+00h]
0x140006d6f  mov     esi, eax
0x140006d71  jmp     loc_140007096
0x140006d76  mov     esi, 0C0000022h
  ... truncated ...
```
