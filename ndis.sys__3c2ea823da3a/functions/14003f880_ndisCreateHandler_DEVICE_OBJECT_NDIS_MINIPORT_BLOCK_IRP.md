# ndisCreateHandler(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *)

- ea: `0x14003f880`
- end: `0x14003fddf`
- name: `?ndisCreateHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@@Z`
- size: `1375`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _NDIS_MINIPORT_BLOCK *, struct _IRP *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003f830`
- `0x14003f860`

## callees

- `0x140015280`
- `0x140019c70`
- `0x14001a3a0`
- `0x14001c050`
- `0x14001cc80`
- `0x14001e4b0`
- `0x14003d920`
- `0x14003e760`
- `0x14003f880`
- `0x1400400f0`
- `0x14004f200`
- `0x140082894`
- `0x1400837ac`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x14003fac7`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14003fac7`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14003f990`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14003fb13`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400eae82`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14003f990`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14003fb13`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400eae82`
- `ntoskrnl!IofCompleteRequest` at `0x14003fbe0`
- `ntoskrnl!IofCompleteRequest` at `0x14003fcc4`
- `ntoskrnl!IofCompleteRequest` at `0x14003fbe0`
- `ntoskrnl!IofCompleteRequest` at `0x14003fcc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eaeb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eaeb2`
- `ntoskrnl!KeInitializeEvent` at `0x14003fadc`
- `ntoskrnl!KeInitializeEvent` at `0x14003fadc`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003fab7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003fab7`
- `ntoskrnl!ExAllocatePool2` at `0x14003fa66`
- `ntoskrnl!ExAllocatePool2` at `0x14003fa66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f97a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f9bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fa4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fbc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fd31`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fdcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eae23`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eae6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f97a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003f9bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fa4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fbc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fd31`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003fdcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eae23`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eae6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003f946`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003f9ff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003fdae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400eae04`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003f946`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003f9ff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003fdae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400eae04`

## pseudocode

```c
__int64 __fastcall ndisCreateHandler(struct _DEVICE_OBJECT *a1, struct _NDIS_MINIPORT_BLOCK *a2, struct _IRP *a3)
{
  struct _DEVICE_OBJECT *v5; // rax
  const struct _GUID *v6; // rdx
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  char v8; // r12
  unsigned __int8 v9; // r13
  __int64 Pool2; // r14
  char v11; // r15
  KIRQL v12; // dl
  unsigned int NumUserOpens; // eax
  int v14; // ebx
  _ULONG_REFERENCE *p_Ref; // r12
  KIRQL v16; // al
  unsigned __int64 *p_Lock; // rcx
  _FILE_OBJECT *FileObject; // rax
  _OID_LIST *OidList; // rax
  _ULONG_REFERENCE *v20; // r15
  struct _NDIS_MINIPORT_BLOCK *v21; // rcx
  KIRQL v22; // dl
  int v23; // edx
  _LIST_ENTRY *Blink; // rdx
  void (__fastcall **BusInterface)(_QWORD); // rcx
  KIRQL v27; // al
  KIRQL v28; // al
  KIRQL v29; // dl
  char v30; // [rsp+40h] [rbp-48h]
  char v31; // [rsp+41h] [rbp-47h]
  char v33; // [rsp+A0h] [rbp+18h]
  unsigned __int8 v34; // [rsp+A8h] [rbp+20h] BYREF

  v34 = 0;
  v5 = a1;
  v6 = &WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)v6,
      11,
      15,
      (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
      (char)a1,
      (char)a3);
    v5 = a1;
  }
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  if ( !CurrentStackLocation->FileObject )
  {
    a3->IoStatus.Status = -1073741823;
    IofCompleteRequest(a3, 2);
    return 3221225473LL;
  }
  if ( a2->Header.Type != 17 )
    return ndisDummyHandler(v5, &a2->Header, a3);
  v8 = 0;
  v9 = 0;
  Pool2 = 0;
  v31 = 0;
  v33 = 0;
  v30 = 0;
  v11 = ndisCheckAccess(a3, CurrentStackLocation, a2->SecurityDescriptor);
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( !ndisMIsCompartmentAccessibleByClient(a2) )
  {
    v14 = -1073741772;
    goto LABEL_9;
  }
  v34 = KeAcquireSpinLockRaiseToDpc(&a2->Ref.SpinLock);
  v12 = v34;
  if ( v11 )
  {
    if ( a2->NumAdminOpens >= 0x1000000 )
      goto LABEL_8;
    ++a2->NumAdminOpens;
    v33 = 1;
  }
  else
  {
    NumUserOpens = a2->NumUserOpens;
    if ( NumUserOpens >= 0x1000000 )
    {
LABEL_8:
      v14 = -1073741670;
      KeReleaseSpinLock(&a2->Ref.SpinLock, v34);
LABEL_9:
      p_Ref = &a2->Ref;
      MmUnlockPagableImageSection(ImageSectionHandle);
      _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
LABEL_21:
      v20 = &a2->Ref;
      goto LABEL_22;
    }
    v8 = 1;
    a2->NumUserOpens = NumUserOpens + 1;
    v30 = 1;
  }
  KeReleaseSpinLock(&a2->Ref.SpinLock, v12);
  if ( (a2->PnPFlags & 0x20100) != 0 )
  {
    v14 = -1073741823;
    goto LABEL_9;
  }
  NdisWaitEvent(&a2->OpenReadyEvent, 0x32u);
  v9 = ndisReferenceMiniport(a2, MPREF_UM_HANDLE);
  if ( !v9 )
  {
    v14 = -1073676282;
    goto LABEL_9;
  }
  v16 = KeAcquireSpinLockRaiseToDpc(&a2->Lock);
  v34 = v16;
  a2->MiniportThread = 0;
  p_Lock = &a2->Lock;
  if ( a2->PnPDeviceState == NdisPnPDeviceQueryStopped )
  {
    v14 = -1073676282;
    KeReleaseSpinLock(p_Lock, v16);
    goto LABEL_9;
  }
  ++a2->UserModeOpenReferences;
  v30 = v8;
  KeReleaseSpinLock(p_Lock, v16);
  Pool2 = ExAllocatePool2(64, 96, 1668236366);
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = a1;
    *(_QWORD *)(Pool2 + 8) = a2;
    *(_QWORD *)(Pool2 + 16) = 0;
    *(_BYTE *)(Pool2 + 24) = v11;
    if ( (unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
    {
      *(_BYTE *)(Pool2 + 25) = MINIPORT_TEST_FLAG(a2, 0x80u);
      KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 32));
      ExInitializeRundownProtection((PEX_RUNDOWN_REF)(Pool2 + 88));
      KeInitializeEvent((PRKEVENT)(Pool2 + 48), NotificationEvent, 0);
    }
    FileObject = CurrentStackLocation->FileObject;
    v14 = 0;
    FileObject->FsContext = (void *)Pool2;
    OidList = a2->OidList;
    if ( OidList )
    {
      *(_QWORD *)(Pool2 + 16) = OidList;
    }
    else if ( a3->RequestorMode == 1 )
    {
      v14 = -1073741823;
    }
  }
  else
  {
    v14 = -1073741670;
  }
  MmUnlockPagableImageSection(ImageSectionHandle);
  _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
  if ( v14 < 0 || (a2->PnPFlags & 0x2000) == 0 )
  {
LABEL_20:
    v30 = v8;
    p_Ref = &a2->Ref;
    v31 = 1;
    goto LABEL_21;
  }
  BusInterface = (void (__fastcall **)(_QWORD))a2->BusInterface;
  if ( !BusInterface )
  {
    v14 = -1073741823;
    goto LABEL_20;
  }
  BusInterface[4](BusInterface[1]);
  v20 = &a2->Ref;
  v31 = 1;
  p_Ref = &a2->Ref;
LABEL_22:
  if ( (unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v14 < 0 )
    {
LABEL_50:
      if ( v33 )
      {
        v27 = KeAcquireSpinLockRaiseToDpc(&v20->SpinLock);
        --a2->NumAdminOpens;
        v34 = v27;
        KeReleaseSpinLock(&v20->SpinLock, v27);
      }
      if ( v30 )
      {
        v28 = KeAcquireSpinLockRaiseToDpc(&v20->SpinLock);
        --a2->NumUserOpens;
        v34 = v28;
        KeReleaseSpinLock(&v20->SpinLock, v28);
      }
      if ( v31 )
      {
        ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
        NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(a2, &v34);
        v29 = v34;
        --a2->UserModeOpenReferences;
        a2->MiniportThread = 0;
        KeReleaseSpinLock(&a2->Lock, v29);
        MmUnlockPagableImageSection(ImageSectionHandle);
        _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
      }
      if ( v9 )
        ndisDereferenceMiniport(a2, MPREF_UM_HANDLE);
      if ( Pool2 )
        ExFreePoolWithTag((PVOID)Pool2, 0);
      goto LABEL_30;
    }
    if ( MINIPORT_TEST_FLAG(a2, 0x80u) )
    {
      NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(v21, &v34);
      if ( a2->PnPDeviceState == NdisPnPDeviceStarted )
      {
        Blink = a2->OpenFileHandles.Blink;
        if ( Blink->Flink != &a2->OpenFileHandles )
          __fastfail(3u);
        *(_QWORD *)(Pool2 + 72) = &a2->OpenFileHandles;
        *(_QWORD *)(Pool2 + 80) = Blink;
        Blink->Flink = (_LIST_ENTRY *)(Pool2 + 72);
        a2->OpenFileHandles.Blink = (_LIST_ENTRY *)(Pool2 + 72);
      }
      else
      {
        v14 = -1073676282;
      }
      v22 = v34;
      a2->MiniportThread = 0;
      KeReleaseSpinLock(&a2->Lock, v22);
    }
  }
  v20 = p_Ref;
  if ( v14 < 0 )
    goto LABEL_50;
LABEL_30:
  a3->IoStatus.Status = v14;
  IofCompleteRequest(a3, 2);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v23) = 4;
    WPP_RECORDER_SF_qqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v23,
      11,
      16,
      (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
      (char)a1,
      (char)a3,
      v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003f880  mov     qword ptr [rsp+arg_0], rcx
0x14003f885  push    rbx
0x14003f886  push    rsi
0x14003f887  push    rdi
0x14003f888  sub     rsp, 70h
0x14003f88c  mov     rsi, r8
0x14003f88f  mov     [rsp+88h+arg_18], 0
0x14003f897  mov     rdi, rdx
0x14003f89a  mov     rax, rcx
0x14003f89d  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003f8a4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003f8ab  lea     rdx, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x14003f8b2  jnz     loc_14003FC1B
0x14003f8b8  mov     rbx, [rsi+0B8h]
0x14003f8bf  mov     [rsp+88h+var_38], r15
0x14003f8c4  cmp     qword ptr [rbx+30h], 0
0x14003f8c9  jz      loc_14003FCB5
0x14003f8cf  cmp     byte ptr [rdi], 11h
0x14003f8d2  jnz     loc_14003FCD8
0x14003f8d8  mov     r8, [rdi+0EC8h]; void *
0x14003f8df  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x14003f8e2  mov     [rsp+88h+arg_8], rbp
0x14003f8ea  mov     rcx, rsi; struct _IRP *
0x14003f8ed  mov     [rsp+88h+var_20], r12
0x14003f8f2  xor     r12b, r12b
0x14003f8f5  mov     [rsp+88h+var_28], r13
0x14003f8fa  xor     r13b, r13b
0x14003f8fd  mov     [rsp+88h+var_30], r14
0x14003f902  xor     r14d, r14d
0x14003f905  mov     [rsp+88h+var_47], r13b
0x14003f90a  mov     [rsp+88h+arg_10], r13b
0x14003f912  mov     [rsp+88h+var_48], r12b
0x14003f917  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x14003f91c  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14003f923  movzx   r15d, al
0x14003f927  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14003f92c  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14003f92f  lea     rbp, [rdi+1150h]
0x14003f936  call    ?ndisMIsCompartmentAccessibleByClient@@YA_NPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMIsCompartmentAccessibleByClient(_NDIS_MINIPORT_BLOCK *)
0x14003f93b  test    al, al
0x14003f93d  jz      loc_14003FCEB
0x14003f943  mov     rcx, rbp; SpinLock
0x14003f946  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003f94d  nop     dword ptr [rax+rax+00h]
0x14003f952  mov     [rsp+88h+arg_18], al
0x14003f959  movzx   edx, al; NewIrql
0x14003f95c  test    r15b, r15b
0x14003f95f  jnz     loc_14003FCF5
0x14003f965  mov     eax, [rdi+0E5Ch]
0x14003f96b  cmp     eax, 1000000h
0x14003f970  jb      short loc_14003F9A8
0x14003f972  mov     rcx, rbp; SpinLock
0x14003f975  mov     ebx, 0C000009Ah
0x14003f97a  call    cs:__imp_KeReleaseSpinLock
0x14003f981  nop     dword ptr [rax+rax+00h]
0x14003f986  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x14003f98d  mov     r12, rbp
0x14003f990  call    cs:__imp_MmUnlockPagableImageSection
0x14003f997  nop     dword ptr [rax+rax+00h]
0x14003f99c  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x14003f9a3  jmp     loc_14003FB4A
0x14003f9a8  inc     eax
0x14003f9aa  mov     r12b, 1
0x14003f9ad  mov     [rdi+0E5Ch], eax
0x14003f9b3  mov     [rsp+88h+var_48], r12b
0x14003f9b8  mov     rcx, rbp; SpinLock
0x14003f9bb  call    cs:__imp_KeReleaseSpinLock
0x14003f9c2  nop     dword ptr [rax+rax+00h]
0x14003f9c7  test    dword ptr [rdi+7Ch], 20100h
0x14003f9ce  jnz     loc_14003FD18
0x14003f9d4  lea     rcx, [rdi+0E90h]; Event
0x14003f9db  mov     edx, 32h ; '2'; MsToWait
0x14003f9e0  call    NdisWaitEvent
0x14003f9e5  mov     dl, 56h ; 'V'; enum _NDIS_MP_REFTAG
0x14003f9e7  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14003f9ea  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14003f9ef  movzx   r13d, al
0x14003f9f3  test    al, al
0x14003f9f5  jz      loc_14003FD22
0x14003f9fb  lea     rcx, [rdi+60h]; SpinLock
0x14003f9ff  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003fa06  nop     dword ptr [rax+rax+00h]
0x14003fa0b  mov     [rsp+88h+arg_18], al
0x14003fa12  movzx   ecx, al
0x14003fa15  mov     [rdi+208h], r14
0x14003fa1c  lea     rcx, [rdi+60h]; SpinLock
0x14003fa20  cmp     dword ptr [rdi+5F0h], 2
0x14003fa27  movzx   edx, al; NewIrql
0x14003fa2a  jz      loc_14003FD2C
0x14003fa30  movzx   eax, [rsp+88h+arg_10]
0x14003fa38  inc     dword ptr [rdi+708h]
0x14003fa3e  mov     [rsp+88h+arg_10], al
0x14003fa45  mov     [rsp+88h+var_48], r12b
0x14003fa4a  call    cs:__imp_KeReleaseSpinLock
0x14003fa51  nop     dword ptr [rax+rax+00h]
0x14003fa56  mov     edx, 60h ; '`'
0x14003fa5b  mov     ecx, 40h ; '@'
0x14003fa60  mov     r8d, 636F444Eh
0x14003fa66  call    cs:__imp_ExAllocatePool2
0x14003fa6d  nop     dword ptr [rax+rax+00h]
0x14003fa72  mov     r14, rax
0x14003fa75  test    rax, rax
0x14003fa78  jz      loc_14003FD42
0x14003fa7e  mov     rax, qword ptr [rsp+88h+arg_0]
0x14003fa86  mov     [r14], rax
0x14003fa89  mov     [r14+8], rdi
0x14003fa8d  mov     qword ptr [r14+10h], 0
0x14003fa95  mov     [r14+18h], r15b
0x14003fa99  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x14003fa9e  test    eax, eax
0x14003faa0  jz      short loc_14003FAE8
0x14003faa2  mov     edx, 80h; unsigned int
0x14003faa7  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14003faaa  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14003faaf  lea     rcx, [r14+20h]; SpinLock
0x14003fab3  mov     [r14+19h], al
0x14003fab7  call    cs:__imp_KeInitializeSpinLock
0x14003fabe  nop     dword ptr [rax+rax+00h]
0x14003fac3  lea     rcx, [r14+58h]; RunRef
0x14003fac7  call    cs:__imp_ExInitializeRundownProtection
0x14003face  nop     dword ptr [rax+rax+00h]
0x14003fad3  lea     rcx, [r14+30h]; Event
0x14003fad7  xor     r8d, r8d; State
0x14003fada  xor     edx, edx; Type
0x14003fadc  call    cs:__imp_KeInitializeEvent
0x14003fae3  nop     dword ptr [rax+rax+00h]
0x14003fae8  mov     rax, [rbx+30h]
0x14003faec  mov     r15d, 0C0000001h
0x14003faf2  xor     ebx, ebx
0x14003faf4  mov     [rax+18h], r14
0x14003faf8  mov     rax, [rdi+6F0h]
0x14003faff  test    rax, rax
0x14003fb02  jz      loc_14003FD52
0x14003fb08  mov     [r14+10h], rax
0x14003fb0c  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x14003fb13  call    cs:__imp_MmUnlockPagableImageSection
0x14003fb1a  nop     dword ptr [rax+rax+00h]
0x14003fb1f  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x14003fb26  test    ebx, ebx
0x14003fb28  jns     loc_14003FD5F
0x14003fb2e  movzx   eax, [rsp+88h+arg_10]
0x14003fb36  mov     [rsp+88h+var_48], r12b
0x14003fb3b  mov     r12, rbp
0x14003fb3e  mov     [rsp+88h+arg_10], al
0x14003fb45  mov     [rsp+88h+var_47], 1
0x14003fb4a  mov     r15, rbp
0x14003fb4d  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x14003fb52  mov     rbp, [rsp+88h+arg_8]
0x14003fb5a  test    eax, eax
0x14003fb5c  jz      short loc_14003FBCD
0x14003fb5e  test    ebx, ebx
0x14003fb60  js      loc_14003FD9D
0x14003fb66  mov     edx, 80h; unsigned int
0x14003fb6b  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14003fb6e  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14003fb73  test    al, al
0x14003fb75  jz      short loc_14003FBCD
0x14003fb77  lea     rdx, [rsp+88h+arg_18]; unsigned __int8 *
0x14003fb7f  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x14003fb84  cmp     dword ptr [rdi+5F0h], 1
0x14003fb8b  jz      loc_14003FC9A
0x14003fb91  mov     ebx, 0C0010006h
0x14003fb96  jmp     short loc_14003FBAA
0x14003fb98  lea     rax, [r14+48h]
0x14003fb9c  mov     [rax], rcx
0x14003fb9f  mov     [rax+8], rdx
0x14003fba3  mov     [rdx], rax
0x14003fba6  mov     [rcx+8], rax
0x14003fbaa  movzx   edx, [rsp+88h+arg_18]; NewIrql
0x14003fbb2  lea     rcx, [rdi+60h]; SpinLock
0x14003fbb6  mov     qword ptr [rdi+208h], 0
0x14003fbc1  call    cs:__imp_KeReleaseSpinLock
0x14003fbc8  nop     dword ptr [rax+rax+00h]
0x14003fbcd  mov     r15, r12
0x14003fbd0  test    ebx, ebx
0x14003fbd2  js      loc_14003FD9D
0x14003fbd8  mov     dl, 2; PriorityBoost
0x14003fbda  mov     [rsi+30h], ebx
0x14003fbdd  mov     rcx, rsi; Irp
0x14003fbe0  call    cs:__imp_IofCompleteRequest
0x14003fbe7  nop     dword ptr [rax+rax+00h]
0x14003fbec  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fbf3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fbfa  jnz     short loc_14003FC55
0x14003fbfc  mov     r13, [rsp+88h+var_28]
0x14003fc01  mov     eax, ebx
0x14003fc03  mov     r12, [rsp+88h+var_20]
0x14003fc08  mov     r14, [rsp+88h+var_30]
0x14003fc0d  mov     r15, [rsp+88h+var_38]
0x14003fc12  add     rsp, 70h
0x14003fc16  pop     rdi
0x14003fc17  pop     rsi
0x14003fc18  pop     rbx
0x14003fc19  retn
0x14003fc1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fc22  mov     r9d, 0Fh; int
0x14003fc28  mov     qword ptr [rsp+88h+var_58], rsi; char
0x14003fc2d  mov     r8d, 0Bh; int
0x14003fc33  mov     qword ptr [rsp+88h+var_60], rax; char
0x14003fc38  mov     [rsp+88h+var_68], rdx; struct _GUID *
0x14003fc3d  mov     dl, 4; int
0x14003fc3f  mov     rcx, [rcx+40h]; int
0x14003fc43  call    WPP_RECORDER_SF_qq
0x14003fc48  mov     rax, qword ptr [rsp+88h+arg_0]
0x14003fc50  jmp     loc_14003F8B8
0x14003fc55  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fc5c  mov     r9d, 10h; int
0x14003fc62  mov     rax, qword ptr [rsp+88h+arg_0]
0x14003fc6a  mov     r8d, 0Bh; int
0x14003fc70  mov     dword ptr [rsp+88h+var_50], ebx; char
0x14003fc74  mov     dl, 4; int
0x14003fc76  mov     qword ptr [rsp+88h+var_58], rsi; char
0x14003fc7b  mov     rcx, [rcx+40h]; int
0x14003fc7f  mov     qword ptr [rsp+88h+var_60], rax; char
0x14003fc84  lea     rax, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x14003fc8b  mov     [rsp+88h+var_68], rax; struct _GUID *
0x14003fc90  call    WPP_RECORDER_SF_qqL
0x14003fc95  jmp     loc_14003FBFC
0x14003fc9a  lea     rcx, [rdi+17D8h]
0x14003fca1  mov     rdx, [rcx+8]
0x14003fca5  cmp     [rdx], rcx
0x14003fca8  jz      loc_14003FB98
0x14003fcae  mov     ecx, 3
0x14003fcb3  int     29h; Win8: RtlFailFast(ecx)
0x14003fcb5  mov     r15d, 0C0000001h
0x14003fcbb  mov     dl, 2; PriorityBoost
0x14003fcbd  mov     rcx, rsi; Irp
0x14003fcc0  mov     [rsi+30h], r15d
0x14003fcc4  call    cs:__imp_IofCompleteRequest
0x14003fccb  nop     dword ptr [rax+rax+00h]
0x14003fcd0  mov     eax, r15d
0x14003fcd3  jmp     loc_14003FC0D
0x14003fcd8  mov     r8, rsi; struct _IRP *
0x14003fcdb  mov     rdx, rdi; struct _NDIS_OBJECT_HEADER *
0x14003fcde  mov     rcx, rax; struct _DEVICE_OBJECT *
0x14003fce1  call    ?ndisDummyHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_OBJECT_HEADER@@PEAU_IRP@@@Z; ndisDummyHandler(_DEVICE_OBJECT *,_NDIS_OBJECT_HEADER *,_IRP *)
0x14003fce6  jmp     loc_14003FC0D
0x14003fceb  mov     ebx, 0C0000034h
0x14003fcf0  jmp     loc_14003F986
0x14003fcf5  cmp     dword ptr [rdi+0EA8h], 1000000h
0x14003fcff  jnb     loc_14003F972
0x14003fd05  inc     dword ptr [rdi+0EA8h]
0x14003fd0b  mov     [rsp+88h+arg_10], 1
0x14003fd13  jmp     loc_14003F9B8
0x14003fd18  mov     ebx, 0C0000001h
0x14003fd1d  jmp     loc_14003F986
0x14003fd22  mov     ebx, 0C0010006h
0x14003fd27  jmp     loc_14003F986
0x14003fd2c  mov     ebx, 0C0010006h
0x14003fd31  call    cs:__imp_KeReleaseSpinLock
0x14003fd38  nop     dword ptr [rax+rax+00h]
0x14003fd3d  jmp     loc_14003F986
0x14003fd42  mov     ebx, 0C000009Ah
0x14003fd47  mov     r15d, 0C0000001h
0x14003fd4d  jmp     loc_14003FB0C
0x14003fd52  cmp     byte ptr [rsi+40h], 1
0x14003fd56  cmovz   ebx, r15d
0x14003fd5a  jmp     loc_14003FB0C
0x14003fd5f  test    dword ptr [rdi+7Ch], 2000h
0x14003fd66  jz      loc_14003FB2E
0x14003fd6c  mov     rcx, [rdi+0F90h]
0x14003fd73  test    rcx, rcx
0x14003fd76  jz      loc_1400EADF2
0x14003fd7c  mov     rax, [rcx+20h]
0x14003fd80  mov     rcx, [rcx+8]
0x14003fd84  call    _guard_dispatch_icall
0x14003fd89  lea     r15, [rdi+1150h]
0x14003fd90  mov     [rsp+88h+var_47], 1
0x14003fd95  mov     r12, rbp
0x14003fd98  jmp     loc_14003FB4D
0x14003fd9d  cmp     [rsp+88h+arg_10], 0
0x14003fda5  jz      loc_1400EADFA
0x14003fdab  mov     rcx, r15; SpinLock
0x14003fdae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003fdb5  nop     dword ptr [rax+rax+00h]
0x14003fdba  dec     dword ptr [rdi+0EA8h]
0x14003fdc0  mov     rcx, r15; SpinLock
0x14003fdc3  movzx   edx, al; NewIrql
0x14003fdc6  mov     [rsp+88h+arg_18], al
0x14003fdcd  call    cs:__imp_KeReleaseSpinLock
0x14003fdd4  nop     dword ptr [rax+rax+00h]
0x14003fdd9  nop
0x14003fdda  jmp     loc_1400EADFA
0x1400eadf2  mov     ebx, r15d
0x1400eadf5  jmp     loc_14003FB2E
0x1400eadfa  cmp     [rsp+88h+var_48], 0
0x1400eadff  jz      short loc_1400EAE2F
0x1400eae01  mov     rcx, r15; SpinLock
0x1400eae04  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400eae0b  nop     dword ptr [rax+rax+00h]
0x1400eae10  dec     dword ptr [rdi+0E5Ch]
0x1400eae16  mov     rcx, r15; SpinLock
0x1400eae19  movzx   edx, al; NewIrql
0x1400eae1c  mov     [rsp+88h+arg_18], al
0x1400eae23  call    cs:__imp_KeReleaseSpinLock
0x1400eae2a  nop     dword ptr [rax+rax+00h]
0x1400eae2f  cmp     [rsp+88h+var_47], 0
0x1400eae34  jz      short loc_1400EAE95
0x1400eae36  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400eae3d  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
  ... truncated ...
```
