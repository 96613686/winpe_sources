# WFDDeviceIoctlPerformGONegotiation(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong)

- ea: `0x140088630`
- end: `0x1400891c9`
- name: `?WFDDeviceIoctlPerformGONegotiation@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK@Z`
- size: `2969`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, struct _IRP *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140015b0c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14005114c`
- `0x14007b8bc`
- `0x140080bb4`
- `0x140080dd0`
- `0x140080dfc`
- `0x140088630`
- `0x14008c000`
- `0x14008c694`
- `0x14008c788`
- `0x14008ce50`
- `0x14008d35c`
- `0x14009a7dc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400889ce`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088a24`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088c9e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400889ce`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088a24`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088c9e`
- `ntoskrnl!ExAllocatePool2` at `0x1400889e9`
- `ntoskrnl!ExAllocatePool2` at `0x140088cbb`
- `ntoskrnl!ExAllocatePool2` at `0x1400889e9`
- `ntoskrnl!ExAllocatePool2` at `0x140088cbb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088a84`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088b9d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088f15`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089163`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088a84`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088b9d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088f15`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089163`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088eee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089174`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088eee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088fd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089174`
- `ntoskrnl!KeReleaseSpinLock` at `0x140088f65`
- `ntoskrnl!KeReleaseSpinLock` at `0x140089130`
- `ntoskrnl!KeReleaseSpinLock` at `0x140088f65`
- `ntoskrnl!KeReleaseSpinLock` at `0x140089130`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140088701`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008901f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140088701`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008901f`
- `NDIS!NdisReleaseRWLock` at `0x140088b72`
- `NDIS!NdisReleaseRWLock` at `0x140088e33`
- `NDIS!NdisReleaseRWLock` at `0x140088b72`
- `NDIS!NdisReleaseRWLock` at `0x140088e33`
- `NDIS!NdisAcquireRWLockRead` at `0x140088b19`
- `NDIS!NdisAcquireRWLockRead` at `0x140088b19`

## pseudocode

```c
__int64 __fastcall WFDDeviceIoctlPerformGONegotiation(
        const struct _WFD_IOCTL_HANDLER_ENTRY *a1,
        struct _WFD_ROLE *a2,
        struct _IRP *a3,
        unsigned __int8 *a4)
{
  KSPIN_LOCK *pRoleExt; // r15
  char v5; // r14
  unsigned int AdapterSync; // edi
  PNPAGED_LOOKASIDE_LIST *v9; // rbx
  unsigned int v10; // r13d
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // r9
  _BYTE *v14; // r10
  _WORD *v15; // r11
  _DOT11_WFD_ATTRIBUTES *WFDAttributes; // rcx
  unsigned __int8 v17; // cl
  void *v18; // r8
  unsigned int v19; // edx
  int v20; // r13d
  __int64 v21; // rax
  unsigned int v22; // eax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r14
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  PNPAGED_LOOKASIDE_LIST *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v29; // r12
  _DWORD *v30; // rax
  PNPAGED_LOOKASIDE_LIST *v31; // rsi
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  struct _WFD_ROLE *v34; // r13
  char *v35; // rsi
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  char v38; // bl
  unsigned int v39; // eax
  _DWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // r13
  unsigned __int8 *v43; // r14
  KSPIN_LOCK *v44; // rsi
  unsigned int v45; // eax
  KIRQL v46; // al
  unsigned int v47; // edx
  __int64 v48; // rbx
  char v50[4]; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v51; // [rsp+74h] [rbp-2Dh] BYREF
  char v52; // [rsp+78h] [rbp-29h]
  unsigned int Size; // [rsp+7Ch] [rbp-25h] BYREF
  struct _LOCK_STATE_EX Size_4; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v55; // [rsp+84h] [rbp-1Dh] BYREF
  unsigned int v56; // [rsp+88h] [rbp-19h]
  unsigned int v57[3]; // [rsp+8Ch] [rbp-15h] BYREF
  void *v58; // [rsp+98h] [rbp-9h]
  unsigned int v59; // [rsp+A0h] [rbp-1h]
  PNPAGED_LOOKASIDE_LIST *v60; // [rsp+A8h] [rbp+7h]
  __int64 v61; // [rsp+B0h] [rbp+Fh]
  void *Src; // [rsp+B8h] [rbp+17h]

  pRoleExt = (KSPIN_LOCK *)a2->pRoleExt;
  v5 = 0;
  *(_QWORD *)&v57[1] = 0;
  v50[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  AdapterSync = PtQueryAdapterSyncEx(a2->pGenVElan->pAdapt, 0xE050111u, v50, 1u, 0, 0);
  if ( !AdapterSync )
  {
    v9 = 0;
    v58 = 0;
    v10 = 0;
    *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc(pRoleExt + 149);
    if ( !(unsigned int)WFDDeviceFindPeerByMAC(
                          (struct _WFD_DEVICE_ROLE *)pRoleExt,
                          (unsigned __int8 (*)[6])(a4 + 16),
                          (struct _WFD_PEER_DEVICE **)&v57[1]) )
    {
      AdapterSync = 1073807377;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_DL(
          WPP_GLOBAL_Control->AttachedDevice,
          v11,
          WPP_GLOBAL_Control,
          v11,
          *(_DWORD *)(*(_QWORD *)&v57[1] + 56LL),
          *(_DWORD *)(*(_QWORD *)&v57[1] + 36LL));
LABEL_133:
      v44 = pRoleExt + 149;
      goto LABEL_134;
    }
    AdapterSync = WFDPeerDeviceCreate(pRoleExt, v11, *(_QWORD *)a4, 2, &v57[1]);
    if ( AdapterSync )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, AdapterSync);
      goto LABEL_133;
    }
    v59 = 0;
    v12 = *(_QWORD *)&v57[1];
    v13 = *(_QWORD *)&v57[1] + 245LL;
    v56 = *(_DWORD *)(*(_QWORD *)&v57[1] + 56LL);
    v14 = (_BYTE *)(*(_QWORD *)&v57[1] + 244LL);
    v15 = (_WORD *)(*(_QWORD *)&v57[1] + 251LL);
    *(_DWORD *)(*(_QWORD *)&v57[1] + 196LL) = *((_DWORD *)a4 + 15);
    *(_BYTE *)(v12 + 40) = v50[0];
    *(_BYTE *)(v12 + 260) |= 1u;
    *(_OWORD *)(v12 + 208) = *(_OWORD *)(a4 + 24);
    *(_OWORD *)(v12 + 224) = *(_OWORD *)(a4 + 40);
    *(_DWORD *)(v12 + 240) = *((_DWORD *)a4 + 14);
    WFDAttributes = a2->pGenVElan->pAdapt->pNwfAttrs->WFDAttributes;
    *(_DWORD *)(v12 + 200) = *(_DWORD *)WFDAttributes->DeviceAddress;
    *(_WORD *)(v12 + 204) = *(_WORD *)&WFDAttributes->DeviceAddress[4];
    *v14 = a4[73];
    *(_DWORD *)v13 = *(_DWORD *)(a4 + 65);
    *(_WORD *)(v13 + 4) = *(_WORD *)(a4 + 69);
    *v15 = *(_WORD *)(a4 + 71);
    if ( *((_DWORD *)a4 + 25) )
    {
      *(_BYTE *)(v12 + 440) = 1;
      *(_DWORD *)(v12 + 441) = *((_DWORD *)a4 + 26);
      *(_BYTE *)(v12 + 445) = a4[108];
    }
    v17 = a4[64];
    *(_BYTE *)(v12 + 253) = v17;
    if ( v17 >= 2u )
    {
      *(_BYTE *)(v12 + 253) = v17 ^ (*((_BYTE *)pRoleExt + 44) ^ v17) & 1;
      *((_BYTE *)pRoleExt + 44) ^= 1u;
    }
    else
    {
      *(_BYTE *)(v12 + 253) = v17 & 0xFE;
    }
    v18 = *(void **)(v12 + 264);
    v19 = *(_DWORD *)(v12 + 272);
    v20 = *(_DWORD *)(v12 + 196);
    Src = v18;
    v57[0] = v19;
    if ( *(_BYTE *)(v12 + 440) )
      v21 = v12 + 441;
    else
      v21 = 0;
    v61 = v21;
    v52 = *(_BYTE *)(v12 + 40);
    v22 = 256;
    v51 = 0;
    Size = 256;
    v55 = 0;
    Size_4.OldIrql = 0;
    *(_WORD *)&Size_4.LockState = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v22 = Size;
      v13 = v12 + 245;
      v19 = v57[0];
      v14 = (_BYTE *)(v12 + 244);
      v18 = Src;
      v15 = (_WORD *)(v12 + 251);
    }
    if ( v12 != -24 && v15 && v13 && v14 )
    {
      if ( !v18 )
      {
        if ( v19 )
          goto LABEL_28;
LABEL_31:
        v25 = v22 + 16;
        if ( v25 < 0x10 )
          goto LABEL_114;
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        if ( v25 > 0x40 )
        {
          if ( v25 > 0x100 )
          {
            if ( v25 > 0x400 )
            {
              if ( v25 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, v25, 808679286);
LABEL_42:
                v29 = Pool2;
                if ( Pool2 )
                {
                  *Pool2 = p_WaitListHead;
                  *((_DWORD *)Pool2 + 2) = 808679286;
                  memset(Pool2 + 2, 0, Size);
                  v30 = ExAllocateFromNPagedLookasideList(&Lookaside);
                  if ( !v30 )
                  {
                    v31 = 0;
                    AdapterSync = -1073741670;
                    v32 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
LABEL_47:
                      v34 = a2;
LABEL_48:
                      if ( v29 != (PNPAGED_LOOKASIDE_LIST *)-16LL )
                      {
                        if ( *v29 )
                          ExFreeToNPagedLookasideList(*v29, v29);
                        else
                          ExFreePoolWithTag(v29, *((_DWORD *)v29 + 2));
                      }
                      if ( v31 )
                      {
                        if ( *(v31 - 2) )
                          ExFreeToNPagedLookasideList(*(v31 - 2), v31 - 2);
                        else
                          ExFreePoolWithTag(v31 - 2, *((_DWORD *)v31 - 2));
                      }
LABEL_104:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          55,
                          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                          AdapterSync);
                      if ( !AdapterSync )
                      {
                        v44 = pRoleExt + 149;
                        KeReleaseSpinLock(pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
                        v9 = (PNPAGED_LOOKASIDE_LIST *)v58;
                        v45 = PtRequestAdapterSync(v34->pGenVElan->pAdapt, 1u, 0xE05010Au, v58, v59);
                        if ( v45 != 1076035585 )
                          AdapterSync = v45;
                        if ( AdapterSync )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              96,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                              AdapterSync);
                          v10 = v56;
LABEL_135:
                          WFDDeviceCleanupPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, v10);
LABEL_136:
                          if ( v9 )
                          {
                            if ( *(v9 - 2) )
                              ExFreeToNPagedLookasideList(*(v9 - 2), v9 - 2);
                            else
                              ExFreePoolWithTag(v9 - 2, *((_DWORD *)v9 - 2));
                          }
                          goto LABEL_140;
                        }
                        v46 = KeAcquireSpinLockRaiseToDpc(pRoleExt + 149);
                        v10 = v56;
                        v47 = v56;
                        *((_BYTE *)pRoleExt + 1200) = v46;
                        v5 = 0;
                        if ( (unsigned int)WFDDeviceFindPeerByID(
                                             (struct _WFD_DEVICE_ROLE *)pRoleExt,
                                             v47,
                                             (struct _WFD_PEER_DEVICE **)&v57[1]) )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_(
                              WPP_GLOBAL_Control->AttachedDevice,
                              97,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                          }
                          AdapterSync = 0;
                        }
                        else
                        {
                          v48 = *(_QWORD *)&v57[1];
                          if ( (unsigned __int8)WFDPeerDeviceSetState(*(_QWORD *)&v57[1], 18) )
                          {
                            WFDPeerDeviceQueueTimer((struct _WFD_PEER_DEVICE *)v48, 0x2710u, 0x3E8u);
                          }
                          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              98,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                              *(unsigned int *)(v48 + 36));
                          }
                          v9 = (PNPAGED_LOOKASIDE_LIST *)v58;
                          AdapterSync = 0;
                        }
LABEL_134:
                        KeReleaseSpinLock(v44, *((_BYTE *)v44 + 8));
                        if ( !v5 )
                          goto LABEL_136;
                        goto LABEL_135;
                      }
                      goto LABEL_130;
                    }
                    v33 = 45;
LABEL_46:
                    WPP_SF_(v32->AttachedDevice, v33, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                    goto LABEL_47;
                  }
                  *(_QWORD *)v30 = &Lookaside;
                  v31 = (PNPAGED_LOOKASIDE_LIST *)(v30 + 4);
                  v30[2] = 808679286;
                  v60 = (PNPAGED_LOOKASIDE_LIST *)(v30 + 4);
                  memset(v30 + 4, 0, 0x208u);
                  *((_DWORD *)v31 + 2) = v20;
                  *((_DWORD *)v31 + 1) = 524416;
                  *((_DWORD *)v31 + 3) |= 1u;
                  *((_DWORD *)v31 + 4) = 32;
                  if ( !(unsigned __int8)WcnGenerateWpsIe(v31, &Size, v29 + 2) )
                  {
                    AdapterSync = -1073741823;
                    v32 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_47;
                    v33 = 46;
                    goto LABEL_46;
                  }
                  v35 = 0;
                  NdisAcquireRWLockRead(a2->pRWLock, &Size_4, 0);
                  AdapterSync = WFDRoleGetCachedFrameIEs(a2, 5u, &v55, 0);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
LABEL_58:
                      v34 = a2;
                      v38 = 0;
                      goto LABEL_59;
                    }
                    v37 = 47;
LABEL_57:
                    WPP_SF_(v36->AttachedDevice, v37, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                    goto LABEL_58;
                  }
                  v51 = 44;
                  AdapterSync = RtlULongAdd(0x2Cu, Size, &v51);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 48;
                    goto LABEL_57;
                  }
                  AdapterSync = RtlULongAdd(v51, v57[0], &v51);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 49;
                    goto LABEL_57;
                  }
                  AdapterSync = RtlULongAdd(v51, v55, &v51);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 50;
                    goto LABEL_57;
                  }
                  v39 = v51 + 16;
                  if ( v51 >= 0xFFFFFFF0 )
                  {
LABEL_84:
                    AdapterSync = -1073741670;
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 52;
                    goto LABEL_57;
                  }
                  if ( v39 > 0x40 )
                  {
                    if ( v39 > 0x100 )
                    {
                      if ( v39 > 0x400 )
                      {
                        if ( v39 > 0x800 )
                        {
                          p_DeviceQueue = 0;
                          v40 = (_DWORD *)ExAllocatePool2(64, v39, 808679286);
LABEL_83:
                          if ( v40 )
                          {
                            v35 = (char *)(v40 + 4);
                            *(_QWORD *)v40 = p_DeviceQueue;
                            v40[2] = 808679286;
                            AdapterSync = 0;
                            memset(v40 + 4, 0, v51);
                            v41 = v61;
                            *(_DWORD *)v35 = 2884224;
                            *((_DWORD *)v35 + 1) = *(_DWORD *)(v12 + 24);
                            *((_WORD *)v35 + 4) = *(_WORD *)(v12 + 28);
                            v35[10] = v52;
                            *((_DWORD *)v35 + 3) = 10000;
                            v35[16] = *(_BYTE *)(v12 + 253);
                            *(_WORD *)(v35 + 17) = *(_WORD *)(v12 + 251);
                            *(_DWORD *)(v35 + 19) = *(_DWORD *)(v12 + 245);
                            *(_WORD *)(v35 + 23) = *(_WORD *)(v12 + 249);
                            v35[25] = *(_BYTE *)(v12 + 244);
                            if ( v41 )
                            {
                              *((_DWORD *)v35 + 9) = *(_DWORD *)v41;
                              v35[40] = *(_BYTE *)(v41 + 4);
                              v35[41] = 1;
                            }
                            *((_DWORD *)v35 + 7) = 44;
                            v42 = v57[0];
                            *((_DWORD *)v35 + 8) = Size + v57[0] + v55;
                            memmove(v35 + 44, v29 + 2, Size);
                            v43 = (unsigned __int8 *)&v35[Size + 44];
                            if ( Src )
                            {
                              memmove(&v35[Size + 44], Src, (unsigned int)v42);
                              v43 += v42;
                            }
                            v34 = a2;
                            if ( !v55 || (AdapterSync = WFDRoleGetCachedFrameIEs(a2, 5u, &v55, v43)) == 0 )
                            {
                              NdisReleaseRWLock(a2->pRWLock, &Size_4);
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                              {
                                WPP_SF__MAC_DDDDDD_MAC_CDD(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  54,
                                  (unsigned int)WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                                  (_DWORD)v35 + 4,
                                  v35[10],
                                  *((_DWORD *)v35 + 3),
                                  (unsigned __int8)v35[16] >> 1,
                                  v35[16] & 1,
                                  v35[17],
                                  v35[18],
                                  (__int64)(v35 + 19),
                                  v35[25],
                                  *((_DWORD *)v35 + 7),
                                  *((_DWORD *)v35 + 8));
                              }
                              v59 = v51;
                              v58 = v35;
                              goto LABEL_63;
                            }
                            v38 = 1;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                53,
                                WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_59:
                            NdisReleaseRWLock(v34->pRWLock, &Size_4);
                            if ( v35 && v38 )
                            {
                              if ( *((_QWORD *)v35 - 2) )
                                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v35 - 2), v35 - 16);
                              else
                                ExFreePoolWithTag(v35 - 16, *((_DWORD *)v35 - 2));
                            }
LABEL_63:
                            v31 = v60;
                            goto LABEL_48;
                          }
                          goto LABEL_84;
                        }
                        p_DeviceQueue = &stru_1400B31C0;
                      }
                      else
                      {
                        p_DeviceQueue = &Lookaside;
                      }
                    }
                    else
                    {
                      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
                    }
                  }
                  v40 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
                  goto LABEL_83;
                }
LABEL_114:
                AdapterSync = -1073741670;
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  v24 = 44;
                  goto LABEL_116;
                }
LABEL_130:
                v5 = 1;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                v10 = v56;
                v9 = (PNPAGED_LOOKASIDE_LIST *)v58;
                goto LABEL_133;
              }
              p_WaitListHead = &stru_1400B31C0;
            }
            else
            {
              p_WaitListHead = &Lookaside;
            }
          }
          else
          {
            p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          }
        }
        else
        {
          p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
        }
        Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
        goto LABEL_42;
      }
      if ( v19 )
        goto LABEL_31;
    }
LABEL_28:
    AdapterSync = -1073741811;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v24 = 43;
LABEL_116:
      WPP_SF_(v23->AttachedDevice, v24, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v34 = a2;
      goto LABEL_104;
    }
    goto LABEL_130;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return AdapterSync;
  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, AdapterSync);
LABEL_140:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, AdapterSync);
  return AdapterSync;
}

```

## disassembly

```asm
0x140088630  mov     [rsp-8+arg_0], rbx
0x140088635  mov     [rsp-8+arg_8], rdx
0x14008863a  push    rbp
0x14008863b  push    rsi
0x14008863c  push    rdi
0x14008863d  push    r12
0x14008863f  push    r13
0x140088641  push    r14
0x140088643  push    r15
0x140088645  lea     rbp, [rsp-1Fh]
0x14008864a  sub     rsp, 0C0h
0x140088651  mov     r15, [rdx+0B8h]
0x140088658  xor     r14d, r14d
0x14008865b  mov     qword ptr [rbp+4Fh+var_64+4], r14
0x14008865f  mov     rsi, r9
0x140088662  mov     [rbp+4Fh+var_80], r14b
0x140088666  mov     r12, rdx
0x140088669  mov     rcx, cs:WPP_GLOBAL_Control
0x140088670  lea     rax, WPP_GLOBAL_Control
0x140088677  cmp     rcx, rax
0x14008867a  jz      short loc_140088690
0x14008867c  mov     rcx, [rcx+18h]
0x140088680  lea     edx, [r14+5Bh]
0x140088684  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008868b  call    WPP_SF_
0x140088690  mov     rcx, [r12]
0x140088694  lea     r8, [rbp+4Fh+var_80]; void *
0x140088698  mov     [rsp+0F0h+var_C8], r14; unsigned int *
0x14008869d  mov     r9d, 1; unsigned int
0x1400886a3  mov     edx, 0E050111h; unsigned int
0x1400886a8  mov     [rsp+0F0h+var_D0], r14; unsigned int *
0x1400886ad  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400886b1  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x1400886b6  mov     edi, eax
0x1400886b8  test    eax, eax
0x1400886ba  jz      short loc_1400886F0
0x1400886bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400886c3  lea     rax, WPP_GLOBAL_Control
0x1400886ca  cmp     rcx, rax
0x1400886cd  jz      loc_1400891AB
0x1400886d3  mov     rcx, [rcx+18h]
0x1400886d7  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400886de  mov     edx, 5Ch ; '\'
0x1400886e3  mov     r9d, edi
0x1400886e6  call    WPP_SF_d
0x1400886eb  jmp     loc_140089180
0x1400886f0  mov     rbx, r14
0x1400886f3  lea     rcx, [r15+4A8h]; SpinLock
0x1400886fa  mov     [rbp+4Fh+var_58], rbx
0x1400886fe  mov     r13d, r14d
0x140088701  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140088708  nop     dword ptr [rax+rax+00h]
0x14008870d  lea     rdx, [rsi+10h]; unsigned __int8 (*)[6]
0x140088711  mov     rcx, r15; struct _WFD_DEVICE_ROLE *
0x140088714  lea     r8, [rbp+4Fh+var_64+4]; struct _WFD_PEER_DEVICE **
0x140088718  mov     [r15+4B0h], al
0x14008871f  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140088724  test    eax, eax
0x140088726  jnz     short loc_140088767
0x140088728  mov     edi, 40010011h
0x14008872d  mov     r8, cs:WPP_GLOBAL_Control
0x140088734  lea     rax, WPP_GLOBAL_Control
0x14008873b  cmp     r8, rax
0x14008873e  jz      loc_140089123
0x140088744  mov     rcx, qword ptr [rbp+4Fh+var_64+4]
0x140088748  mov     r9, rdx
0x14008874b  mov     eax, [rcx+24h]
0x14008874e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140088752  mov     eax, [rcx+38h]
0x140088755  mov     rcx, [r8+18h]
0x140088759  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14008875d  call    WPP_SF__MAC_DL
0x140088762  jmp     loc_140089123
0x140088767  mov     r8, [rsi]
0x14008876a  lea     rax, [rbp+4Fh+var_64+4]
0x14008876e  mov     r9d, 2
0x140088774  mov     [rsp+0F0h+var_D0], rax
0x140088779  mov     rcx, r15
0x14008877c  call    ?WFDPeerDeviceCreate@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAXW4WFD_PEER_TYPE@@PEAPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCreate(_WFD_DEVICE_ROLE *,uchar (*)[6],void *,WFD_PEER_TYPE,_WFD_PEER_DEVICE * *)
0x140088781  mov     edi, eax
0x140088783  test    eax, eax
0x140088785  jz      short loc_1400887BB
0x140088787  mov     rcx, cs:WPP_GLOBAL_Control
0x14008878e  lea     rax, WPP_GLOBAL_Control
0x140088795  cmp     rcx, rax
0x140088798  jz      loc_140089123
0x14008879e  mov     rcx, [rcx+18h]
0x1400887a2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400887a9  mov     edx, 5Eh ; '^'
0x1400887ae  mov     r9d, edi
0x1400887b1  call    WPP_SF_d
0x1400887b6  jmp     loc_140089123
0x1400887bb  mov     [rbp+4Fh+var_50], ebx
0x1400887be  mov     rbx, qword ptr [rbp+4Fh+var_64+4]
0x1400887c2  mov     eax, [rbx+38h]
0x1400887c5  lea     r9, [rbx+0F5h]
0x1400887cc  mov     [rbp+4Fh+var_68], eax
0x1400887cf  lea     r10, [rbx+0F4h]
0x1400887d6  mov     eax, [rsi+3Ch]
0x1400887d9  lea     r11, [rbx+0FBh]
0x1400887e0  mov     [rbx+0C4h], eax
0x1400887e6  mov     al, [rbp+4Fh+var_80]
0x1400887e9  mov     [rbx+28h], al
0x1400887ec  or      byte ptr [rbx+104h], 1
0x1400887f3  movups  xmm0, xmmword ptr [rsi+18h]
0x1400887f7  movups  xmmword ptr [rbx+0D0h], xmm0
0x1400887fe  movups  xmm1, xmmword ptr [rsi+28h]
0x140088802  movups  xmmword ptr [rbx+0E0h], xmm1
0x140088809  mov     eax, [rsi+38h]
0x14008880c  mov     [rbx+0F0h], eax
0x140088812  mov     rax, [r12]
0x140088816  mov     rcx, [rax+10h]
0x14008881a  mov     rax, [rcx+18h]
0x14008881e  mov     rcx, [rax+38h]
0x140088822  mov     eax, [rcx+18h]
0x140088825  mov     [rbx+0C8h], eax
0x14008882b  movzx   eax, word ptr [rcx+1Ch]
0x14008882f  mov     [rbx+0CCh], ax
0x140088836  mov     al, [rsi+49h]
0x140088839  mov     [r10], al
0x14008883c  mov     eax, [rsi+41h]
0x14008883f  mov     [r9], eax
0x140088842  movzx   eax, word ptr [rsi+45h]
0x140088846  mov     [r9+4], ax
0x14008884b  movzx   eax, word ptr [rsi+47h]
0x14008884f  mov     [r11], ax
0x140088853  cmp     [rsi+64h], r14d
0x140088857  jz      short loc_140088872
0x140088859  mov     byte ptr [rbx+1B8h], 1
0x140088860  mov     eax, [rsi+68h]
0x140088863  mov     [rbx+1B9h], eax
0x140088869  mov     al, [rsi+6Ch]
0x14008886c  mov     [rbx+1BDh], al
0x140088872  mov     cl, [rsi+40h]
0x140088875  mov     [rbx+0FDh], cl
0x14008887b  cmp     cl, 2
0x14008887e  jnb     short loc_14008888B
0x140088880  and     cl, 0FEh
0x140088883  mov     [rbx+0FDh], cl
0x140088889  jmp     short loc_1400888A0
0x14008888b  mov     al, cl
0x14008888d  xor     al, [r15+2Ch]
0x140088891  and     al, 1
0x140088893  xor     al, cl
0x140088895  mov     [rbx+0FDh], al
0x14008889b  xor     byte ptr [r15+2Ch], 1
0x1400888a0  mov     r8, [rbx+108h]
0x1400888a7  mov     edx, [rbx+110h]
0x1400888ad  mov     r13d, [rbx+0C4h]
0x1400888b4  mov     [rbp+4Fh+Src], r8
0x1400888b8  mov     dword ptr [rbp+4Fh+var_64], edx
0x1400888bb  cmp     [rbx+1B8h], r14b
0x1400888c2  jz      short loc_1400888CD
0x1400888c4  lea     rax, [rbx+1B9h]
0x1400888cb  jmp     short loc_1400888CF
0x1400888cd  xor     eax, eax
0x1400888cf  mov     [rbp+4Fh+var_40], rax
0x1400888d3  lea     rdi, [rbx+18h]
0x1400888d7  mov     al, [rbx+28h]
0x1400888da  mov     r12d, 100h
0x1400888e0  mov     byte ptr [rbp+4Fh+var_7C+4], al
0x1400888e3  xor     ecx, ecx
0x1400888e5  mov     eax, r12d
0x1400888e8  mov     dword ptr [rbp+4Fh+var_7C], r14d
0x1400888ec  mov     dword ptr [rbp+4Fh+Size], eax
0x1400888ef  mov     [rbp+4Fh+var_6C], r14d
0x1400888f3  mov     byte ptr [rbp+4Fh+Size+4], r14b
0x1400888f7  mov     word ptr [rbp+4Fh+Size+5], cx
0x1400888fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140088902  lea     rsi, WPP_GLOBAL_Control
0x140088909  cmp     rcx, rsi
0x14008890c  jz      short loc_140088942
0x14008890e  mov     rcx, [rcx+18h]
0x140088912  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140088919  mov     edx, 2Ah ; '*'
0x14008891e  call    WPP_SF_
0x140088923  mov     eax, dword ptr [rbp+4Fh+Size]
0x140088926  lea     r9, [rbx+0F5h]
0x14008892d  mov     edx, dword ptr [rbp+4Fh+var_64]
0x140088930  lea     r10, [rbx+0F4h]
0x140088937  mov     r8, [rbp+4Fh+Src]
0x14008893b  lea     r11, [rbx+0FBh]
0x140088942  test    rdi, rdi
0x140088945  jz      short loc_14008895F
0x140088947  test    r11, r11
0x14008894a  jz      short loc_14008895F
0x14008894c  test    r9, r9
0x14008894f  jz      short loc_14008895F
0x140088951  test    r10, r10
0x140088954  jz      short loc_14008895F
0x140088956  test    r8, r8
0x140088959  jnz     short loc_14008897E
0x14008895b  test    edx, edx
0x14008895d  jz      short loc_140088982
0x14008895f  mov     edi, 0C000000Dh
0x140088964  mov     rcx, cs:WPP_GLOBAL_Control
0x14008896b  cmp     rcx, rsi
0x14008896e  jz      loc_1400890F7
0x140088974  mov     edx, 2Bh ; '+'
0x140088979  jmp     loc_140089003
0x14008897e  test    edx, edx
0x140088980  jz      short loc_14008895F
0x140088982  add     eax, 10h
0x140088985  cmp     eax, 10h
0x140088988  jb      loc_140088FE9
0x14008898e  lea     r14, WPP_MAIN_CB.DeviceQueue
0x140088995  cmp     eax, 40h ; '@'
0x140088998  ja      short loc_14008899F
0x14008899a  mov     rdi, r14
0x14008899d  jmp     short loc_1400889CB
0x14008899f  cmp     eax, r12d
0x1400889a2  ja      short loc_1400889AD
0x1400889a4  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400889ab  jmp     short loc_1400889CB
0x1400889ad  cmp     eax, 400h
0x1400889b2  ja      short loc_1400889BD
0x1400889b4  lea     rdi, Lookaside
0x1400889bb  jmp     short loc_1400889CB
0x1400889bd  cmp     eax, 800h
0x1400889c2  ja      short loc_1400889DC
0x1400889c4  lea     rdi, stru_1400B31C0
0x1400889cb  mov     rcx, rdi; Lookaside
0x1400889ce  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400889d5  nop     dword ptr [rax+rax+00h]
0x1400889da  jmp     short loc_1400889F5
0x1400889dc  xor     edi, edi
0x1400889de  mov     edx, eax
0x1400889e0  mov     r8d, 30337776h
0x1400889e6  lea     ecx, [rdi+40h]
0x1400889e9  call    cs:__imp_ExAllocatePool2
0x1400889f0  nop     dword ptr [rax+rax+00h]
0x1400889f5  mov     r12, rax
0x1400889f8  test    rax, rax
0x1400889fb  jz      loc_140088FE9
0x140088a01  mov     [rax], rdi
0x140088a04  lea     rcx, [rax+10h]; void *
0x140088a08  mov     dword ptr [rax+8], 30337776h
0x140088a0f  xor     edx, edx; Val
0x140088a11  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x140088a15  call    memset
0x140088a1a  lea     rsi, Lookaside
0x140088a21  mov     rcx, rsi; Lookaside
0x140088a24  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088a2b  nop     dword ptr [rax+rax+00h]
0x140088a30  test    rax, rax
0x140088a33  jnz     short loc_140088A95
0x140088a35  xor     esi, esi
0x140088a37  mov     edi, 0C000009Ah
0x140088a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140088a43  lea     rax, WPP_GLOBAL_Control
0x140088a4a  cmp     rcx, rax
0x140088a4d  jz      short loc_140088A62
0x140088a4f  lea     edx, [rsi+2Dh]
0x140088a52  mov     rcx, [rcx+18h]
0x140088a56  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140088a5d  call    WPP_SF_
0x140088a62  mov     r13, [rbp+4Fh+arg_8]
0x140088a66  lea     rax, [r12+10h]
0x140088a6b  test    rax, rax
0x140088a6e  jz      loc_140088EFA
0x140088a74  mov     rcx, [r12]; Lookaside
0x140088a78  test    rcx, rcx
0x140088a7b  jz      loc_140088EE6
0x140088a81  mov     rdx, r12; Entry
0x140088a84  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088a8b  nop     dword ptr [rax+rax+00h]
0x140088a90  jmp     loc_140088EFA
0x140088a95  mov     [rax], rsi
0x140088a98  xor     edx, edx; Val
0x140088a9a  lea     rsi, [rax+10h]
0x140088a9e  mov     dword ptr [rax+8], 30337776h
0x140088aa5  mov     rcx, rsi; void *
0x140088aa8  mov     [rbp+4Fh+var_48], rsi
0x140088aac  mov     r8d, 208h; Size
0x140088ab2  call    memset
0x140088ab7  mov     [rsi+8], r13d
0x140088abb  lea     r8, [r12+10h]
0x140088ac0  mov     dword ptr [rsi+4], 80080h
0x140088ac7  lea     rdx, [rbp+4Fh+Size]
0x140088acb  or      dword ptr [rsi+0Ch], 1
0x140088acf  mov     rcx, rsi
0x140088ad2  mov     dword ptr [rsi+10h], 20h ; ' '
0x140088ad9  call    WcnGenerateWpsIe
0x140088ade  test    al, al
0x140088ae0  jnz     short loc_140088B08
0x140088ae2  mov     edi, 0C0000001h
0x140088ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x140088aee  lea     rax, WPP_GLOBAL_Control
0x140088af5  cmp     rcx, rax
0x140088af8  jz      loc_140088A62
0x140088afe  mov     edx, 2Eh ; '.'
0x140088b03  jmp     loc_140088A52
0x140088b08  mov     rdi, [rbp+4Fh+arg_8]
0x140088b0c  lea     rdx, [rbp+4Fh+Size+4]; LockState
0x140088b10  xor     r8d, r8d; Flags
0x140088b13  xor     esi, esi
0x140088b15  mov     rcx, [rdi+20h]; Lock
0x140088b19  call    cs:__imp_NdisAcquireRWLockRead
0x140088b20  nop     dword ptr [rax+rax+00h]
0x140088b25  xor     r9d, r9d; unsigned __int8 *
  ... truncated ...
```
