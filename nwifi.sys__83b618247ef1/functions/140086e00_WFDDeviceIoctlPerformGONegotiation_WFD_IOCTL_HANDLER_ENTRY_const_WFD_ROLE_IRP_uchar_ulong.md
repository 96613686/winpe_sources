# WFDDeviceIoctlPerformGONegotiation(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong)

- ea: `0x140086e00`
- end: `0x140087999`
- name: `?WFDDeviceIoctlPerformGONegotiation@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK@Z`
- size: `2969`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, struct _IRP *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140015b1c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14004f984`
- `0x14007a08c`
- `0x14007f384`
- `0x14007f5a0`
- `0x14007f5cc`
- `0x140086e00`
- `0x14008a7d0`
- `0x14008ae64`
- `0x14008af58`
- `0x14008b620`
- `0x14008bb2c`
- `0x140098ffc`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008719e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400871f4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008746e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008719e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400871f4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008746e`
- `ntoskrnl!ExAllocatePool2` at `0x1400871b9`
- `ntoskrnl!ExAllocatePool2` at `0x14008748b`
- `ntoskrnl!ExAllocatePool2` at `0x1400871b9`
- `ntoskrnl!ExAllocatePool2` at `0x14008748b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087254`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008736d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400876e5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087933`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087254`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008736d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400876e5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087933`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400875ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400876be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400877a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087944`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400875ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400876be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400877a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087944`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087735`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087900`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087735`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087900`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086ed1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400877ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140086ed1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400877ef`
- `NDIS!NdisReleaseRWLock` at `0x140087342`
- `NDIS!NdisReleaseRWLock` at `0x140087603`
- `NDIS!NdisReleaseRWLock` at `0x140087342`
- `NDIS!NdisReleaseRWLock` at `0x140087603`
- `NDIS!NdisAcquireRWLockRead` at `0x1400872e9`
- `NDIS!NdisAcquireRWLockRead` at `0x1400872e9`

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
  int *v31; // rsi
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  struct _WFD_ROLE *v34; // r13
  char *v35; // rsi
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  char v38; // bl
  __int64 v39; // r9
  unsigned int v40; // eax
  _DWORD *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r13
  unsigned __int8 *v44; // r14
  KSPIN_LOCK *v45; // rsi
  unsigned int v46; // eax
  KIRQL v47; // al
  unsigned int v48; // edx
  __int64 v49; // rbx
  char v51[4]; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v52; // [rsp+74h] [rbp-2Dh] BYREF
  char v53; // [rsp+78h] [rbp-29h]
  unsigned int Size; // [rsp+7Ch] [rbp-25h] BYREF
  struct _LOCK_STATE_EX Size_4; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v56; // [rsp+84h] [rbp-1Dh] BYREF
  unsigned int v57; // [rsp+88h] [rbp-19h]
  unsigned int v58[3]; // [rsp+8Ch] [rbp-15h] BYREF
  void *v59; // [rsp+98h] [rbp-9h]
  unsigned int v60; // [rsp+A0h] [rbp-1h]
  int *v61; // [rsp+A8h] [rbp+7h]
  __int64 v62; // [rsp+B0h] [rbp+Fh]
  void *Src; // [rsp+B8h] [rbp+17h]

  pRoleExt = (KSPIN_LOCK *)a2->pRoleExt;
  v5 = 0;
  *(_QWORD *)&v58[1] = 0;
  v51[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  AdapterSync = PtQueryAdapterSyncEx(a2->pGenVElan->pAdapt, 0xE050111u, v51, 1u, 0, 0);
  if ( !AdapterSync )
  {
    v9 = 0;
    v59 = 0;
    v10 = 0;
    *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc(pRoleExt + 149);
    if ( !(unsigned int)WFDDeviceFindPeerByMAC(
                          (struct _WFD_DEVICE_ROLE *)pRoleExt,
                          (unsigned __int8 (*)[6])(a4 + 16),
                          (struct _WFD_PEER_DEVICE **)&v58[1]) )
    {
      AdapterSync = 1073807377;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_DL(
          WPP_GLOBAL_Control->AttachedDevice,
          v11,
          WPP_GLOBAL_Control,
          v11,
          *(_DWORD *)(*(_QWORD *)&v58[1] + 56LL),
          *(_DWORD *)(*(_QWORD *)&v58[1] + 36LL));
LABEL_133:
      v45 = pRoleExt + 149;
      goto LABEL_134;
    }
    AdapterSync = WFDPeerDeviceCreate(pRoleExt, v11, *(_QWORD *)a4, 2, &v58[1]);
    if ( AdapterSync )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, AdapterSync);
      goto LABEL_133;
    }
    v60 = 0;
    v12 = *(_QWORD *)&v58[1];
    v13 = *(_QWORD *)&v58[1] + 245LL;
    v57 = *(_DWORD *)(*(_QWORD *)&v58[1] + 56LL);
    v14 = (_BYTE *)(*(_QWORD *)&v58[1] + 244LL);
    v15 = (_WORD *)(*(_QWORD *)&v58[1] + 251LL);
    *(_DWORD *)(*(_QWORD *)&v58[1] + 196LL) = *((_DWORD *)a4 + 15);
    *(_BYTE *)(v12 + 40) = v51[0];
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
    v58[0] = v19;
    if ( *(_BYTE *)(v12 + 440) )
      v21 = v12 + 441;
    else
      v21 = 0;
    v62 = v21;
    v53 = *(_BYTE *)(v12 + 40);
    v22 = 256;
    v52 = 0;
    Size = 256;
    v56 = 0;
    Size_4.OldIrql = 0;
    *(_WORD *)&Size_4.LockState = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      v22 = Size;
      v13 = v12 + 245;
      v19 = v58[0];
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
                Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, v25, 808679286, v13);
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
                        if ( *((_QWORD *)v31 - 2) )
                          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v31 - 2), v31 - 4);
                        else
                          ExFreePoolWithTag(v31 - 4, *(v31 - 2));
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
                        v45 = pRoleExt + 149;
                        KeReleaseSpinLock(pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
                        v9 = (PNPAGED_LOOKASIDE_LIST *)v59;
                        v46 = PtRequestAdapterSync(v34->pGenVElan->pAdapt, 1u, 0xE05010Au, v59, v60);
                        if ( v46 != 1076035585 )
                          AdapterSync = v46;
                        if ( AdapterSync )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              96,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                              AdapterSync);
                          v10 = v57;
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
                        v47 = KeAcquireSpinLockRaiseToDpc(pRoleExt + 149);
                        v10 = v57;
                        v48 = v57;
                        *((_BYTE *)pRoleExt + 1200) = v47;
                        v5 = 0;
                        if ( (unsigned int)WFDDeviceFindPeerByID(
                                             (struct _WFD_DEVICE_ROLE *)pRoleExt,
                                             v48,
                                             (struct _WFD_PEER_DEVICE **)&v58[1]) )
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
                          v49 = *(_QWORD *)&v58[1];
                          if ( (unsigned __int8)WFDPeerDeviceSetState(*(_QWORD *)&v58[1], 18) )
                          {
                            WFDPeerDeviceQueueTimer((struct _WFD_PEER_DEVICE *)v49, 0x2710u, 0x3E8u);
                          }
                          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              98,
                              WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
                              *(unsigned int *)(v49 + 36));
                          }
                          v9 = (PNPAGED_LOOKASIDE_LIST *)v59;
                          AdapterSync = 0;
                        }
LABEL_134:
                        KeReleaseSpinLock(v45, *((_BYTE *)v45 + 8));
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
                  v31 = v30 + 4;
                  v30[2] = 808679286;
                  v61 = v30 + 4;
                  memset(v30 + 4, 0, 0x208u);
                  v31[2] = v20;
                  v31[1] = 524416;
                  v31[3] |= 1u;
                  v31[4] = 32;
                  if ( !WcnGenerateWpsIe(v31, &Size, (_BYTE *)v29 + 16) )
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
                  AdapterSync = WFDRoleGetCachedFrameIEs(a2, 5u, &v56, 0);
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
                  v52 = 44;
                  AdapterSync = RtlULongAdd(0x2Cu, Size, &v52);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 48;
                    goto LABEL_57;
                  }
                  AdapterSync = RtlULongAdd(v52, v58[0], &v52);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 49;
                    goto LABEL_57;
                  }
                  AdapterSync = RtlULongAdd(v52, v56, &v52);
                  if ( AdapterSync )
                  {
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 50;
                    goto LABEL_57;
                  }
                  v40 = v52 + 16;
                  if ( v52 >= 0xFFFFFFF0 )
                  {
LABEL_84:
                    AdapterSync = -1073741670;
                    v36 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      goto LABEL_58;
                    v37 = 52;
                    goto LABEL_57;
                  }
                  if ( v40 > 0x40 )
                  {
                    if ( v40 > 0x100 )
                    {
                      if ( v40 > 0x400 )
                      {
                        if ( v40 > 0x800 )
                        {
                          p_DeviceQueue = 0;
                          v41 = (_DWORD *)ExAllocatePool2(64, v40, 808679286, v39);
LABEL_83:
                          if ( v41 )
                          {
                            v35 = (char *)(v41 + 4);
                            *(_QWORD *)v41 = p_DeviceQueue;
                            v41[2] = 808679286;
                            AdapterSync = 0;
                            memset(v41 + 4, 0, v52);
                            v42 = v62;
                            *(_DWORD *)v35 = 2884224;
                            *((_DWORD *)v35 + 1) = *(_DWORD *)(v12 + 24);
                            *((_WORD *)v35 + 4) = *(_WORD *)(v12 + 28);
                            v35[10] = v53;
                            *((_DWORD *)v35 + 3) = 10000;
                            v35[16] = *(_BYTE *)(v12 + 253);
                            *(_WORD *)(v35 + 17) = *(_WORD *)(v12 + 251);
                            *(_DWORD *)(v35 + 19) = *(_DWORD *)(v12 + 245);
                            *(_WORD *)(v35 + 23) = *(_WORD *)(v12 + 249);
                            v35[25] = *(_BYTE *)(v12 + 244);
                            if ( v42 )
                            {
                              *((_DWORD *)v35 + 9) = *(_DWORD *)v42;
                              v35[40] = *(_BYTE *)(v42 + 4);
                              v35[41] = 1;
                            }
                            *((_DWORD *)v35 + 7) = 44;
                            v43 = v58[0];
                            *((_DWORD *)v35 + 8) = Size + v58[0] + v56;
                            memmove(v35 + 44, v29 + 2, Size);
                            v44 = (unsigned __int8 *)&v35[Size + 44];
                            if ( Src )
                            {
                              memmove(&v35[Size + 44], Src, (unsigned int)v43);
                              v44 += v43;
                            }
                            v34 = a2;
                            if ( !v56 || (AdapterSync = WFDRoleGetCachedFrameIEs(a2, 5u, &v56, v44)) == 0 )
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
                              v60 = v52;
                              v59 = v35;
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
                            v31 = v61;
                            goto LABEL_48;
                          }
                          goto LABEL_84;
                        }
                        p_DeviceQueue = &stru_1400B0180;
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
                  v41 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
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
                v10 = v57;
                v9 = (PNPAGED_LOOKASIDE_LIST *)v59;
                goto LABEL_133;
              }
              p_WaitListHead = &stru_1400B0180;
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
0x140086e00  mov     [rsp-8+arg_0], rbx
0x140086e05  mov     [rsp-8+arg_8], rdx
0x140086e0a  push    rbp
0x140086e0b  push    rsi
0x140086e0c  push    rdi
0x140086e0d  push    r12
0x140086e0f  push    r13
0x140086e11  push    r14
0x140086e13  push    r15
0x140086e15  lea     rbp, [rsp-1Fh]
0x140086e1a  sub     rsp, 0C0h
0x140086e21  mov     r15, [rdx+0B8h]
0x140086e28  xor     r14d, r14d
0x140086e2b  mov     qword ptr [rbp+4Fh+var_64+4], r14
0x140086e2f  mov     rsi, r9
0x140086e32  mov     [rbp+4Fh+var_80], r14b
0x140086e36  mov     r12, rdx
0x140086e39  mov     rcx, cs:WPP_GLOBAL_Control
0x140086e40  lea     rax, WPP_GLOBAL_Control
0x140086e47  cmp     rcx, rax
0x140086e4a  jz      short loc_140086E60
0x140086e4c  mov     rcx, [rcx+18h]
0x140086e50  lea     edx, [r14+5Bh]
0x140086e54  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140086e5b  call    WPP_SF_
0x140086e60  mov     rcx, [r12]
0x140086e64  lea     r8, [rbp+4Fh+var_80]; void *
0x140086e68  mov     [rsp+0F0h+var_C8], r14; unsigned int *
0x140086e6d  mov     r9d, 1; unsigned int
0x140086e73  mov     edx, 0E050111h; unsigned int
0x140086e78  mov     [rsp+0F0h+var_D0], r14; unsigned int *
0x140086e7d  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140086e81  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140086e86  mov     edi, eax
0x140086e88  test    eax, eax
0x140086e8a  jz      short loc_140086EC0
0x140086e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086e93  lea     rax, WPP_GLOBAL_Control
0x140086e9a  cmp     rcx, rax
0x140086e9d  jz      loc_14008797B
0x140086ea3  mov     rcx, [rcx+18h]
0x140086ea7  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140086eae  mov     edx, 5Ch ; '\'
0x140086eb3  mov     r9d, edi
0x140086eb6  call    WPP_SF_d
0x140086ebb  jmp     loc_140087950
0x140086ec0  mov     rbx, r14
0x140086ec3  lea     rcx, [r15+4A8h]; SpinLock
0x140086eca  mov     [rbp+4Fh+var_58], rbx
0x140086ece  mov     r13d, r14d
0x140086ed1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140086ed8  nop     dword ptr [rax+rax+00h]
0x140086edd  lea     rdx, [rsi+10h]; unsigned __int8 (*)[6]
0x140086ee1  mov     rcx, r15; struct _WFD_DEVICE_ROLE *
0x140086ee4  lea     r8, [rbp+4Fh+var_64+4]; struct _WFD_PEER_DEVICE **
0x140086ee8  mov     [r15+4B0h], al
0x140086eef  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140086ef4  test    eax, eax
0x140086ef6  jnz     short loc_140086F37
0x140086ef8  mov     edi, 40010011h
0x140086efd  mov     r8, cs:WPP_GLOBAL_Control
0x140086f04  lea     rax, WPP_GLOBAL_Control
0x140086f0b  cmp     r8, rax
0x140086f0e  jz      loc_1400878F3
0x140086f14  mov     rcx, qword ptr [rbp+4Fh+var_64+4]
0x140086f18  mov     r9, rdx
0x140086f1b  mov     eax, [rcx+24h]
0x140086f1e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140086f22  mov     eax, [rcx+38h]
0x140086f25  mov     rcx, [r8+18h]
0x140086f29  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140086f2d  call    WPP_SF__MAC_DL
0x140086f32  jmp     loc_1400878F3
0x140086f37  mov     r8, [rsi]
0x140086f3a  lea     rax, [rbp+4Fh+var_64+4]
0x140086f3e  mov     r9d, 2
0x140086f44  mov     [rsp+0F0h+var_D0], rax
0x140086f49  mov     rcx, r15
0x140086f4c  call    ?WFDPeerDeviceCreate@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAXW4WFD_PEER_TYPE@@PEAPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCreate(_WFD_DEVICE_ROLE *,uchar (*)[6],void *,WFD_PEER_TYPE,_WFD_PEER_DEVICE * *)
0x140086f51  mov     edi, eax
0x140086f53  test    eax, eax
0x140086f55  jz      short loc_140086F8B
0x140086f57  mov     rcx, cs:WPP_GLOBAL_Control
0x140086f5e  lea     rax, WPP_GLOBAL_Control
0x140086f65  cmp     rcx, rax
0x140086f68  jz      loc_1400878F3
0x140086f6e  mov     rcx, [rcx+18h]
0x140086f72  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140086f79  mov     edx, 5Eh ; '^'
0x140086f7e  mov     r9d, edi
0x140086f81  call    WPP_SF_d
0x140086f86  jmp     loc_1400878F3
0x140086f8b  mov     [rbp+4Fh+var_50], ebx
0x140086f8e  mov     rbx, qword ptr [rbp+4Fh+var_64+4]
0x140086f92  mov     eax, [rbx+38h]
0x140086f95  lea     r9, [rbx+0F5h]
0x140086f9c  mov     [rbp+4Fh+var_68], eax
0x140086f9f  lea     r10, [rbx+0F4h]
0x140086fa6  mov     eax, [rsi+3Ch]
0x140086fa9  lea     r11, [rbx+0FBh]
0x140086fb0  mov     [rbx+0C4h], eax
0x140086fb6  mov     al, [rbp+4Fh+var_80]
0x140086fb9  mov     [rbx+28h], al
0x140086fbc  or      byte ptr [rbx+104h], 1
0x140086fc3  movups  xmm0, xmmword ptr [rsi+18h]
0x140086fc7  movups  xmmword ptr [rbx+0D0h], xmm0
0x140086fce  movups  xmm1, xmmword ptr [rsi+28h]
0x140086fd2  movups  xmmword ptr [rbx+0E0h], xmm1
0x140086fd9  mov     eax, [rsi+38h]
0x140086fdc  mov     [rbx+0F0h], eax
0x140086fe2  mov     rax, [r12]
0x140086fe6  mov     rcx, [rax+10h]
0x140086fea  mov     rax, [rcx+18h]
0x140086fee  mov     rcx, [rax+38h]
0x140086ff2  mov     eax, [rcx+18h]
0x140086ff5  mov     [rbx+0C8h], eax
0x140086ffb  movzx   eax, word ptr [rcx+1Ch]
0x140086fff  mov     [rbx+0CCh], ax
0x140087006  mov     al, [rsi+49h]
0x140087009  mov     [r10], al
0x14008700c  mov     eax, [rsi+41h]
0x14008700f  mov     [r9], eax
0x140087012  movzx   eax, word ptr [rsi+45h]
0x140087016  mov     [r9+4], ax
0x14008701b  movzx   eax, word ptr [rsi+47h]
0x14008701f  mov     [r11], ax
0x140087023  cmp     [rsi+64h], r14d
0x140087027  jz      short loc_140087042
0x140087029  mov     byte ptr [rbx+1B8h], 1
0x140087030  mov     eax, [rsi+68h]
0x140087033  mov     [rbx+1B9h], eax
0x140087039  mov     al, [rsi+6Ch]
0x14008703c  mov     [rbx+1BDh], al
0x140087042  mov     cl, [rsi+40h]
0x140087045  mov     [rbx+0FDh], cl
0x14008704b  cmp     cl, 2
0x14008704e  jnb     short loc_14008705B
0x140087050  and     cl, 0FEh
0x140087053  mov     [rbx+0FDh], cl
0x140087059  jmp     short loc_140087070
0x14008705b  mov     al, cl
0x14008705d  xor     al, [r15+2Ch]
0x140087061  and     al, 1
0x140087063  xor     al, cl
0x140087065  mov     [rbx+0FDh], al
0x14008706b  xor     byte ptr [r15+2Ch], 1
0x140087070  mov     r8, [rbx+108h]
0x140087077  mov     edx, [rbx+110h]
0x14008707d  mov     r13d, [rbx+0C4h]
0x140087084  mov     [rbp+4Fh+Src], r8
0x140087088  mov     dword ptr [rbp+4Fh+var_64], edx
0x14008708b  cmp     [rbx+1B8h], r14b
0x140087092  jz      short loc_14008709D
0x140087094  lea     rax, [rbx+1B9h]
0x14008709b  jmp     short loc_14008709F
0x14008709d  xor     eax, eax
0x14008709f  mov     [rbp+4Fh+var_40], rax
0x1400870a3  lea     rdi, [rbx+18h]
0x1400870a7  mov     al, [rbx+28h]
0x1400870aa  mov     r12d, 100h
0x1400870b0  mov     byte ptr [rbp+4Fh+var_7C+4], al
0x1400870b3  xor     ecx, ecx
0x1400870b5  mov     eax, r12d
0x1400870b8  mov     dword ptr [rbp+4Fh+var_7C], r14d
0x1400870bc  mov     dword ptr [rbp+4Fh+Size], eax
0x1400870bf  mov     [rbp+4Fh+var_6C], r14d
0x1400870c3  mov     byte ptr [rbp+4Fh+Size+4], r14b
0x1400870c7  mov     word ptr [rbp+4Fh+Size+5], cx
0x1400870cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400870d2  lea     rsi, WPP_GLOBAL_Control
0x1400870d9  cmp     rcx, rsi
0x1400870dc  jz      short loc_140087112
0x1400870de  mov     rcx, [rcx+18h]
0x1400870e2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400870e9  mov     edx, 2Ah ; '*'
0x1400870ee  call    WPP_SF_
0x1400870f3  mov     eax, dword ptr [rbp+4Fh+Size]
0x1400870f6  lea     r9, [rbx+0F5h]
0x1400870fd  mov     edx, dword ptr [rbp+4Fh+var_64]
0x140087100  lea     r10, [rbx+0F4h]
0x140087107  mov     r8, [rbp+4Fh+Src]
0x14008710b  lea     r11, [rbx+0FBh]
0x140087112  test    rdi, rdi
0x140087115  jz      short loc_14008712F
0x140087117  test    r11, r11
0x14008711a  jz      short loc_14008712F
0x14008711c  test    r9, r9
0x14008711f  jz      short loc_14008712F
0x140087121  test    r10, r10
0x140087124  jz      short loc_14008712F
0x140087126  test    r8, r8
0x140087129  jnz     short loc_14008714E
0x14008712b  test    edx, edx
0x14008712d  jz      short loc_140087152
0x14008712f  mov     edi, 0C000000Dh
0x140087134  mov     rcx, cs:WPP_GLOBAL_Control
0x14008713b  cmp     rcx, rsi
0x14008713e  jz      loc_1400878C7
0x140087144  mov     edx, 2Bh ; '+'
0x140087149  jmp     loc_1400877D3
0x14008714e  test    edx, edx
0x140087150  jz      short loc_14008712F
0x140087152  add     eax, 10h
0x140087155  cmp     eax, 10h
0x140087158  jb      loc_1400877B9
0x14008715e  lea     r14, WPP_MAIN_CB.DeviceQueue
0x140087165  cmp     eax, 40h ; '@'
0x140087168  ja      short loc_14008716F
0x14008716a  mov     rdi, r14
0x14008716d  jmp     short loc_14008719B
0x14008716f  cmp     eax, r12d
0x140087172  ja      short loc_14008717D
0x140087174  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008717b  jmp     short loc_14008719B
0x14008717d  cmp     eax, 400h
0x140087182  ja      short loc_14008718D
0x140087184  lea     rdi, Lookaside
0x14008718b  jmp     short loc_14008719B
0x14008718d  cmp     eax, 800h
0x140087192  ja      short loc_1400871AC
0x140087194  lea     rdi, stru_1400B0180
0x14008719b  mov     rcx, rdi; Lookaside
0x14008719e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400871a5  nop     dword ptr [rax+rax+00h]
0x1400871aa  jmp     short loc_1400871C5
0x1400871ac  xor     edi, edi
0x1400871ae  mov     edx, eax
0x1400871b0  mov     r8d, 30337776h
0x1400871b6  lea     ecx, [rdi+40h]
0x1400871b9  call    cs:__imp_ExAllocatePool2
0x1400871c0  nop     dword ptr [rax+rax+00h]
0x1400871c5  mov     r12, rax
0x1400871c8  test    rax, rax
0x1400871cb  jz      loc_1400877B9
0x1400871d1  mov     [rax], rdi
0x1400871d4  lea     rcx, [rax+10h]; void *
0x1400871d8  mov     dword ptr [rax+8], 30337776h
0x1400871df  xor     edx, edx; Val
0x1400871e1  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x1400871e5  call    memset
0x1400871ea  lea     rsi, Lookaside
0x1400871f1  mov     rcx, rsi; Lookaside
0x1400871f4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400871fb  nop     dword ptr [rax+rax+00h]
0x140087200  test    rax, rax
0x140087203  jnz     short loc_140087265
0x140087205  xor     esi, esi
0x140087207  mov     edi, 0C000009Ah
0x14008720c  mov     rcx, cs:WPP_GLOBAL_Control
0x140087213  lea     rax, WPP_GLOBAL_Control
0x14008721a  cmp     rcx, rax
0x14008721d  jz      short loc_140087232
0x14008721f  lea     edx, [rsi+2Dh]
0x140087222  mov     rcx, [rcx+18h]
0x140087226  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008722d  call    WPP_SF_
0x140087232  mov     r13, [rbp+4Fh+arg_8]
0x140087236  lea     rax, [r12+10h]
0x14008723b  test    rax, rax
0x14008723e  jz      loc_1400876CA
0x140087244  mov     rcx, [r12]; Lookaside
0x140087248  test    rcx, rcx
0x14008724b  jz      loc_1400876B6
0x140087251  mov     rdx, r12; Entry
0x140087254  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008725b  nop     dword ptr [rax+rax+00h]
0x140087260  jmp     loc_1400876CA
0x140087265  mov     [rax], rsi
0x140087268  xor     edx, edx; Val
0x14008726a  lea     rsi, [rax+10h]
0x14008726e  mov     dword ptr [rax+8], 30337776h
0x140087275  mov     rcx, rsi; void *
0x140087278  mov     [rbp+4Fh+var_48], rsi
0x14008727c  mov     r8d, 208h; Size
0x140087282  call    memset
0x140087287  mov     [rsi+8], r13d
0x14008728b  lea     r8, [r12+10h]
0x140087290  mov     dword ptr [rsi+4], 80080h
0x140087297  lea     rdx, [rbp+4Fh+Size]
0x14008729b  or      dword ptr [rsi+0Ch], 1
0x14008729f  mov     rcx, rsi
0x1400872a2  mov     dword ptr [rsi+10h], 20h ; ' '
0x1400872a9  call    WcnGenerateWpsIe
0x1400872ae  test    al, al
0x1400872b0  jnz     short loc_1400872D8
0x1400872b2  mov     edi, 0C0000001h
0x1400872b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400872be  lea     rax, WPP_GLOBAL_Control
0x1400872c5  cmp     rcx, rax
0x1400872c8  jz      loc_140087232
0x1400872ce  mov     edx, 2Eh ; '.'
0x1400872d3  jmp     loc_140087222
0x1400872d8  mov     rdi, [rbp+4Fh+arg_8]
0x1400872dc  lea     rdx, [rbp+4Fh+Size+4]; LockState
0x1400872e0  xor     r8d, r8d; Flags
0x1400872e3  xor     esi, esi
0x1400872e5  mov     rcx, [rdi+20h]; Lock
0x1400872e9  call    cs:__imp_NdisAcquireRWLockRead
0x1400872f0  nop     dword ptr [rax+rax+00h]
0x1400872f5  xor     r9d, r9d; unsigned __int8 *
  ... truncated ...
```
