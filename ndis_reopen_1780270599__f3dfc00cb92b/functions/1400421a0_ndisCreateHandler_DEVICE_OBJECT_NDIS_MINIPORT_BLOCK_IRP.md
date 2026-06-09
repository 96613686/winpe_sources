# ndisCreateHandler(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *)

- ea: `0x1400421a0`
- end: `0x1400426ff`
- name: `?ndisCreateHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@@Z`
- size: `1375`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _NDIS_MINIPORT_BLOCK *, struct _IRP *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140042150`
- `0x140042180`

## callees

- `0x140009320`
- `0x14000dd10`
- `0x14000e440`
- `0x1400100f0`
- `0x140010d20`
- `0x140012610`
- `0x1400400d0`
- `0x140040f10`
- `0x1400421a0`
- `0x140042a10`
- `0x1400548f0`
- `0x140087b14`
- `0x140088a2c`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400423e7`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400423e7`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400422b0`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140042433`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400efa7a`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400422b0`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140042433`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400efa7a`
- `ntoskrnl!IofCompleteRequest` at `0x140042500`
- `ntoskrnl!IofCompleteRequest` at `0x1400425e4`
- `ntoskrnl!IofCompleteRequest` at `0x140042500`
- `ntoskrnl!IofCompleteRequest` at `0x1400425e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400efaaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400efaaa`
- `ntoskrnl!KeInitializeEvent` at `0x1400423fc`
- `ntoskrnl!KeInitializeEvent` at `0x1400423fc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400423d7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400423d7`
- `ntoskrnl!ExAllocatePool2` at `0x140042386`
- `ntoskrnl!ExAllocatePool2` at `0x140042386`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004229a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400422db`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004236a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400424e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042651`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400426ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400efa1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400efa67`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004229a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400422db`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004236a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400424e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042651`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400426ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400efa1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400efa67`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042266`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004231f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400426ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ef9fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042266`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004231f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400426ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ef9fc`

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
  unsigned __int8 v11; // r15
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
0x1400421a0  mov     qword ptr [rsp+arg_0], rcx
0x1400421a5  push    rbx
0x1400421a6  push    rsi
0x1400421a7  push    rdi
0x1400421a8  sub     rsp, 70h
0x1400421ac  mov     rsi, r8
0x1400421af  mov     [rsp+88h+arg_18], 0
0x1400421b7  mov     rdi, rdx
0x1400421ba  mov     rax, rcx
0x1400421bd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400421c4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400421cb  lea     rdx, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x1400421d2  jnz     loc_14004253B
0x1400421d8  mov     rbx, [rsi+0B8h]
0x1400421df  mov     [rsp+88h+var_38], r15
0x1400421e4  cmp     qword ptr [rbx+30h], 0
0x1400421e9  jz      loc_1400425D5
0x1400421ef  cmp     byte ptr [rdi], 11h
0x1400421f2  jnz     loc_1400425F8
0x1400421f8  mov     r8, [rdi+0EC8h]; void *
0x1400421ff  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x140042202  mov     [rsp+88h+arg_8], rbp
0x14004220a  mov     rcx, rsi; struct _IRP *
0x14004220d  mov     [rsp+88h+var_20], r12
0x140042212  xor     r12b, r12b
0x140042215  mov     [rsp+88h+var_28], r13
0x14004221a  xor     r13b, r13b
0x14004221d  mov     [rsp+88h+var_30], r14
0x140042222  xor     r14d, r14d
0x140042225  mov     [rsp+88h+var_47], r13b
0x14004222a  mov     [rsp+88h+arg_10], r13b
0x140042232  mov     [rsp+88h+var_48], r12b
0x140042237  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x14004223c  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140042243  movzx   r15d, al
0x140042247  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14004224c  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14004224f  lea     rbp, [rdi+1150h]
0x140042256  call    ?ndisMIsCompartmentAccessibleByClient@@YA_NPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMIsCompartmentAccessibleByClient(_NDIS_MINIPORT_BLOCK *)
0x14004225b  test    al, al
0x14004225d  jz      loc_14004260B
0x140042263  mov     rcx, rbp; SpinLock
0x140042266  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004226d  nop     dword ptr [rax+rax+00h]
0x140042272  mov     [rsp+88h+arg_18], al
0x140042279  movzx   edx, al; NewIrql
0x14004227c  test    r15b, r15b
0x14004227f  jnz     loc_140042615
0x140042285  mov     eax, [rdi+0E5Ch]
0x14004228b  cmp     eax, 1000000h
0x140042290  jb      short loc_1400422C8
0x140042292  mov     rcx, rbp; SpinLock
0x140042295  mov     ebx, 0C000009Ah
0x14004229a  call    cs:__imp_KeReleaseSpinLock
0x1400422a1  nop     dword ptr [rax+rax+00h]
0x1400422a6  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x1400422ad  mov     r12, rbp
0x1400422b0  call    cs:__imp_MmUnlockPagableImageSection
0x1400422b7  nop     dword ptr [rax+rax+00h]
0x1400422bc  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x1400422c3  jmp     loc_14004246A
0x1400422c8  inc     eax
0x1400422ca  mov     r12b, 1
0x1400422cd  mov     [rdi+0E5Ch], eax
0x1400422d3  mov     [rsp+88h+var_48], r12b
0x1400422d8  mov     rcx, rbp; SpinLock
0x1400422db  call    cs:__imp_KeReleaseSpinLock
0x1400422e2  nop     dword ptr [rax+rax+00h]
0x1400422e7  test    dword ptr [rdi+7Ch], 20100h
0x1400422ee  jnz     loc_140042638
0x1400422f4  lea     rcx, [rdi+0E90h]; Event
0x1400422fb  mov     edx, 32h ; '2'; MsToWait
0x140042300  call    NdisWaitEvent
0x140042305  mov     dl, 56h ; 'V'; enum _NDIS_MP_REFTAG
0x140042307  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14004230a  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14004230f  movzx   r13d, al
0x140042313  test    al, al
0x140042315  jz      loc_140042642
0x14004231b  lea     rcx, [rdi+60h]; SpinLock
0x14004231f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140042326  nop     dword ptr [rax+rax+00h]
0x14004232b  mov     [rsp+88h+arg_18], al
0x140042332  movzx   ecx, al
0x140042335  mov     [rdi+208h], r14
0x14004233c  lea     rcx, [rdi+60h]; SpinLock
0x140042340  cmp     dword ptr [rdi+5F0h], 2
0x140042347  movzx   edx, al; NewIrql
0x14004234a  jz      loc_14004264C
0x140042350  movzx   eax, [rsp+88h+arg_10]
0x140042358  inc     dword ptr [rdi+708h]
0x14004235e  mov     [rsp+88h+arg_10], al
0x140042365  mov     [rsp+88h+var_48], r12b
0x14004236a  call    cs:__imp_KeReleaseSpinLock
0x140042371  nop     dword ptr [rax+rax+00h]
0x140042376  mov     edx, 60h ; '`'
0x14004237b  mov     ecx, 40h ; '@'
0x140042380  mov     r8d, 636F444Eh
0x140042386  call    cs:__imp_ExAllocatePool2
0x14004238d  nop     dword ptr [rax+rax+00h]
0x140042392  mov     r14, rax
0x140042395  test    rax, rax
0x140042398  jz      loc_140042662
0x14004239e  mov     rax, qword ptr [rsp+88h+arg_0]
0x1400423a6  mov     [r14], rax
0x1400423a9  mov     [r14+8], rdi
0x1400423ad  mov     qword ptr [r14+10h], 0
0x1400423b5  mov     [r14+18h], r15b
0x1400423b9  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x1400423be  test    eax, eax
0x1400423c0  jz      short loc_140042408
0x1400423c2  mov     edx, 80h; unsigned int
0x1400423c7  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400423ca  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400423cf  lea     rcx, [r14+20h]; SpinLock
0x1400423d3  mov     [r14+19h], al
0x1400423d7  call    cs:__imp_KeInitializeSpinLock
0x1400423de  nop     dword ptr [rax+rax+00h]
0x1400423e3  lea     rcx, [r14+58h]; RunRef
0x1400423e7  call    cs:__imp_ExInitializeRundownProtection
0x1400423ee  nop     dword ptr [rax+rax+00h]
0x1400423f3  lea     rcx, [r14+30h]; Event
0x1400423f7  xor     r8d, r8d; State
0x1400423fa  xor     edx, edx; Type
0x1400423fc  call    cs:__imp_KeInitializeEvent
0x140042403  nop     dword ptr [rax+rax+00h]
0x140042408  mov     rax, [rbx+30h]
0x14004240c  mov     r15d, 0C0000001h
0x140042412  xor     ebx, ebx
0x140042414  mov     [rax+18h], r14
0x140042418  mov     rax, [rdi+6F0h]
0x14004241f  test    rax, rax
0x140042422  jz      loc_140042672
0x140042428  mov     [r14+10h], rax
0x14004242c  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x140042433  call    cs:__imp_MmUnlockPagableImageSection
0x14004243a  nop     dword ptr [rax+rax+00h]
0x14004243f  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x140042446  test    ebx, ebx
0x140042448  jns     loc_14004267F
0x14004244e  movzx   eax, [rsp+88h+arg_10]
0x140042456  mov     [rsp+88h+var_48], r12b
0x14004245b  mov     r12, rbp
0x14004245e  mov     [rsp+88h+arg_10], al
0x140042465  mov     [rsp+88h+var_47], 1
0x14004246a  mov     r15, rbp
0x14004246d  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x140042472  mov     rbp, [rsp+88h+arg_8]
0x14004247a  test    eax, eax
0x14004247c  jz      short loc_1400424ED
0x14004247e  test    ebx, ebx
0x140042480  js      loc_1400426BD
0x140042486  mov     edx, 80h; unsigned int
0x14004248b  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14004248e  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140042493  test    al, al
0x140042495  jz      short loc_1400424ED
0x140042497  lea     rdx, [rsp+88h+arg_18]; unsigned __int8 *
0x14004249f  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x1400424a4  cmp     dword ptr [rdi+5F0h], 1
0x1400424ab  jz      loc_1400425BA
0x1400424b1  mov     ebx, 0C0010006h
0x1400424b6  jmp     short loc_1400424CA
0x1400424b8  lea     rax, [r14+48h]
0x1400424bc  mov     [rax], rcx
0x1400424bf  mov     [rax+8], rdx
0x1400424c3  mov     [rdx], rax
0x1400424c6  mov     [rcx+8], rax
0x1400424ca  movzx   edx, [rsp+88h+arg_18]; NewIrql
0x1400424d2  lea     rcx, [rdi+60h]; SpinLock
0x1400424d6  mov     qword ptr [rdi+208h], 0
0x1400424e1  call    cs:__imp_KeReleaseSpinLock
0x1400424e8  nop     dword ptr [rax+rax+00h]
0x1400424ed  mov     r15, r12
0x1400424f0  test    ebx, ebx
0x1400424f2  js      loc_1400426BD
0x1400424f8  mov     dl, 2; PriorityBoost
0x1400424fa  mov     [rsi+30h], ebx
0x1400424fd  mov     rcx, rsi; Irp
0x140042500  call    cs:__imp_IofCompleteRequest
0x140042507  nop     dword ptr [rax+rax+00h]
0x14004250c  lea     rax, WPP_RECORDER_INITIALIZED
0x140042513  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004251a  jnz     short loc_140042575
0x14004251c  mov     r13, [rsp+88h+var_28]
0x140042521  mov     eax, ebx
0x140042523  mov     r12, [rsp+88h+var_20]
0x140042528  mov     r14, [rsp+88h+var_30]
0x14004252d  mov     r15, [rsp+88h+var_38]
0x140042532  add     rsp, 70h
0x140042536  pop     rdi
0x140042537  pop     rsi
0x140042538  pop     rbx
0x140042539  retn
0x14004253b  mov     rcx, cs:WPP_GLOBAL_Control
0x140042542  mov     r9d, 0Fh; int
0x140042548  mov     qword ptr [rsp+88h+var_58], rsi; char
0x14004254d  mov     r8d, 0Bh; int
0x140042553  mov     qword ptr [rsp+88h+var_60], rax; char
0x140042558  mov     [rsp+88h+var_68], rdx; struct _GUID *
0x14004255d  mov     dl, 4; int
0x14004255f  mov     rcx, [rcx+40h]; int
0x140042563  call    WPP_RECORDER_SF_qq
0x140042568  mov     rax, qword ptr [rsp+88h+arg_0]
0x140042570  jmp     loc_1400421D8
0x140042575  mov     rcx, cs:WPP_GLOBAL_Control
0x14004257c  mov     r9d, 10h; int
0x140042582  mov     rax, qword ptr [rsp+88h+arg_0]
0x14004258a  mov     r8d, 0Bh; int
0x140042590  mov     dword ptr [rsp+88h+var_50], ebx; char
0x140042594  mov     dl, 4; int
0x140042596  mov     qword ptr [rsp+88h+var_58], rsi; char
0x14004259b  mov     rcx, [rcx+40h]; int
0x14004259f  mov     qword ptr [rsp+88h+var_60], rax; char
0x1400425a4  lea     rax, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x1400425ab  mov     [rsp+88h+var_68], rax; struct _GUID *
0x1400425b0  call    WPP_RECORDER_SF_qqL
0x1400425b5  jmp     loc_14004251C
0x1400425ba  lea     rcx, [rdi+17D8h]
0x1400425c1  mov     rdx, [rcx+8]
0x1400425c5  cmp     [rdx], rcx
0x1400425c8  jz      loc_1400424B8
0x1400425ce  mov     ecx, 3
0x1400425d3  int     29h; Win8: RtlFailFast(ecx)
0x1400425d5  mov     r15d, 0C0000001h
0x1400425db  mov     dl, 2; PriorityBoost
0x1400425dd  mov     rcx, rsi; Irp
0x1400425e0  mov     [rsi+30h], r15d
0x1400425e4  call    cs:__imp_IofCompleteRequest
0x1400425eb  nop     dword ptr [rax+rax+00h]
0x1400425f0  mov     eax, r15d
0x1400425f3  jmp     loc_14004252D
0x1400425f8  mov     r8, rsi; struct _IRP *
0x1400425fb  mov     rdx, rdi; struct _NDIS_OBJECT_HEADER *
0x1400425fe  mov     rcx, rax; struct _DEVICE_OBJECT *
0x140042601  call    ?ndisDummyHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_OBJECT_HEADER@@PEAU_IRP@@@Z; ndisDummyHandler(_DEVICE_OBJECT *,_NDIS_OBJECT_HEADER *,_IRP *)
0x140042606  jmp     loc_14004252D
0x14004260b  mov     ebx, 0C0000034h
0x140042610  jmp     loc_1400422A6
0x140042615  cmp     dword ptr [rdi+0EA8h], 1000000h
0x14004261f  jnb     loc_140042292
0x140042625  inc     dword ptr [rdi+0EA8h]
0x14004262b  mov     [rsp+88h+arg_10], 1
0x140042633  jmp     loc_1400422D8
0x140042638  mov     ebx, 0C0000001h
0x14004263d  jmp     loc_1400422A6
0x140042642  mov     ebx, 0C0010006h
0x140042647  jmp     loc_1400422A6
0x14004264c  mov     ebx, 0C0010006h
0x140042651  call    cs:__imp_KeReleaseSpinLock
0x140042658  nop     dword ptr [rax+rax+00h]
0x14004265d  jmp     loc_1400422A6
0x140042662  mov     ebx, 0C000009Ah
0x140042667  mov     r15d, 0C0000001h
0x14004266d  jmp     loc_14004242C
0x140042672  cmp     byte ptr [rsi+40h], 1
0x140042676  cmovz   ebx, r15d
0x14004267a  jmp     loc_14004242C
0x14004267f  test    dword ptr [rdi+7Ch], 2000h
0x140042686  jz      loc_14004244E
0x14004268c  mov     rcx, [rdi+0F90h]
0x140042693  test    rcx, rcx
0x140042696  jz      loc_1400EF9EA
0x14004269c  mov     rax, [rcx+20h]
0x1400426a0  mov     rcx, [rcx+8]
0x1400426a4  call    _guard_dispatch_icall
0x1400426a9  lea     r15, [rdi+1150h]
0x1400426b0  mov     [rsp+88h+var_47], 1
0x1400426b5  mov     r12, rbp
0x1400426b8  jmp     loc_14004246D
0x1400426bd  cmp     [rsp+88h+arg_10], 0
0x1400426c5  jz      loc_1400EF9F2
0x1400426cb  mov     rcx, r15; SpinLock
0x1400426ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400426d5  nop     dword ptr [rax+rax+00h]
0x1400426da  dec     dword ptr [rdi+0EA8h]
0x1400426e0  mov     rcx, r15; SpinLock
0x1400426e3  movzx   edx, al; NewIrql
0x1400426e6  mov     [rsp+88h+arg_18], al
0x1400426ed  call    cs:__imp_KeReleaseSpinLock
0x1400426f4  nop     dword ptr [rax+rax+00h]
0x1400426f9  nop
0x1400426fa  jmp     loc_1400EF9F2
0x1400ef9ea  mov     ebx, r15d
0x1400ef9ed  jmp     loc_14004244E
0x1400ef9f2  cmp     [rsp+88h+var_48], 0
0x1400ef9f7  jz      short loc_1400EFA27
0x1400ef9f9  mov     rcx, r15; SpinLock
0x1400ef9fc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400efa03  nop     dword ptr [rax+rax+00h]
0x1400efa08  dec     dword ptr [rdi+0E5Ch]
0x1400efa0e  mov     rcx, r15; SpinLock
0x1400efa11  movzx   edx, al; NewIrql
0x1400efa14  mov     [rsp+88h+arg_18], al
0x1400efa1b  call    cs:__imp_KeReleaseSpinLock
0x1400efa22  nop     dword ptr [rax+rax+00h]
0x1400efa27  cmp     [rsp+88h+var_47], 0
0x1400efa2c  jz      short loc_1400EFA8D
0x1400efa2e  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400efa35  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
  ... truncated ...
```
