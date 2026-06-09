# ndisDispatchRequest

- ea: `0x1400401c0`
- end: `0x1400407f2`
- name: `ndisDispatchRequest`
- size: `1586`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003f8a0`

## callees

- `0x140010d20`
- `0x140012610`
- `0x1400400d0`
- `0x1400401c0`
- `0x140040f10`
- `0x140043d80`
- `0x140063bb0`
- `0x140089110`
- `0x1400a52fc`
- `0x1400d155c`
- `0x1400eb460`
- `0x1401811f0`

## import_xrefs

- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400407ca`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400407ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400407b7`
- `ntoskrnl!IofCompleteRequest` at `0x1400407b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040772`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040772`
- `ntoskrnl!ExAllocatePool2` at `0x140040232`
- `ntoskrnl!ExAllocatePool2` at `0x140040232`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040313`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400403ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400403e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040400`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004042c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040455`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004052b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400405d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040692`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040313`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400403ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400403e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040400`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004042c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040455`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004052b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400405d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040692`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400402eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040326`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400403c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040413`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004043f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004048d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400402eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040326`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400403c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040413`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004043f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004048d`

## pseudocode

```c
__int64 __fastcall ndisDispatchRequest(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  char v4; // si
  unsigned int v6; // r12d
  _OWORD *Pool2; // rax
  _BYTE *v8; // rdi
  void *v9; // r8
  struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *v10; // rbx
  void *v11; // rcx
  __int64 v12; // rbx
  KIRQL v13; // al
  struct _NDIS_M_DRIVER_BLOCK *v14; // rbp
  KIRQL v15; // al
  _NDIS_MINIPORT_BLOCK *MiniportQueue; // rdi
  KIRQL v17; // r15
  KIRQL v18; // al
  __int64 v19; // rdi
  KIRQL v20; // al
  KIRQL v21; // bp
  int v22; // ecx
  bool v23; // r14
  unsigned __int8 v24; // r8
  __int64 v25; // rdx
  unsigned __int8 v26; // cl
  char v27; // cl
  bool v28; // al
  unsigned __int8 v29; // cl
  char v30; // r9
  unsigned __int8 v31; // al
  unsigned __int8 v32; // dl
  __int16 v33; // r8
  __int64 v34; // rax
  void (__fastcall *v35)(_QWORD, _QWORD); // r8
  _FILE_OBJECT *FileObject; // rax
  void *FsContext; // rcx
  unsigned int v38; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  a2->IoStatus.Status = 259;
  a2->IoStatus.Information = 0;
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  v6 = 0;
  switch ( CurrentStackLocation->MajorFunction )
  {
    case 0u:
      Pool2 = (_OWORD *)ExAllocatePool2(64, 64, 1668236366);
      v8 = Pool2;
      if ( Pool2 )
      {
        v9 = ndisSecurityDescriptor;
        *Pool2 = 0;
        Pool2[1] = 0;
        Pool2[2] = 0;
        Pool2[3] = 0;
        *(_BYTE *)Pool2 = ndisCheckAccess(a2, CurrentStackLocation, v9);
        v8[1] = ndisCheckAccess(a2, CurrentStackLocation, qword_1400FFBF0);
        v8[2] = ndisCheckAccess(a2, CurrentStackLocation, qword_140122800);
        CurrentStackLocation->FileObject->FsContext = v8;
        _InterlockedIncrement(&dword_140122E60);
      }
      else
      {
        v6 = -1073741670;
      }
      goto LABEL_73;
    case 2u:
      FileObject = CurrentStackLocation->FileObject;
      FsContext = FileObject->FsContext;
      FileObject->FsContext = 0;
      if ( FsContext )
        ExFreePoolWithTag(FsContext, 0);
      _InterlockedDecrement(&dword_140122E60);
      goto LABEL_73;
    case 0xEu:
      v38 = ndisHandlePnPRequest(a2);
      goto LABEL_70;
    case 0xFu:
      goto LABEL_73;
    case 0x12u:
      v10 = (struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *)CurrentStackLocation->FileObject->FsContext;
      ndisNicActiveHandleCleanup(v10);
      v11 = (void *)*((_QWORD *)v10 + 6);
      if ( v11 )
      {
        ndisIfDereferenceCompartmentForUser(v11);
        *((_QWORD *)v10 + 6) = 0;
      }
      v12 = *((_QWORD *)v10 + 4);
      if ( !v12 )
        goto LABEL_73;
      v13 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
      v14 = ndisMiniDriverList;
      break;
    case 0x17u:
      v38 = ndisDriverSystemDispatch(a1, a2);
LABEL_70:
      v6 = v38;
      if ( v38 != 259 )
        goto LABEL_73;
      goto LABEL_74;
    default:
      v6 = -1073741822;
      goto LABEL_73;
  }
LABEL_9:
  if ( !v14 )
    goto LABEL_21;
  KeReleaseSpinLock(&ndisMiniDriverListLock, v13);
  v15 = KeAcquireSpinLockRaiseToDpc(&v14->Ref.SpinLock);
  MiniportQueue = v14->MiniportQueue;
  v17 = v15;
  while ( 1 )
  {
    if ( !MiniportQueue )
    {
LABEL_20:
      KeReleaseSpinLock(&v14->Ref.SpinLock, v17);
      v13 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
      v14 = v14->NextDriver;
      if ( !v4 )
        goto LABEL_9;
LABEL_21:
      KeReleaseSpinLock(&ndisMiniDriverListLock, v13);
      goto LABEL_73;
    }
    if ( MiniportQueue == (_NDIS_MINIPORT_BLOCK *)v12 )
    {
      if ( ndisReferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v12, MPREF_AOAC_CLEANUP) )
        break;
      if ( (*(_DWORD *)(v12 + 120) & 0x80200020) != 0 )
      {
        KeReleaseSpinLock(&v14->Ref.SpinLock, v17);
        v13 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
        goto LABEL_21;
      }
      v4 = 1;
      if ( (*(_DWORD *)(v12 + 124) & 0x1084110) == 0
        && *(_DWORD *)(v12 + 1520) == 1
        && *(_DWORD *)(v12 + 3868) == 1
        && ndisReferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v12, MPREF_AOAC_CLEANUP) )
      {
        break;
      }
    }
    MiniportQueue = MiniportQueue->NextMiniport;
    if ( v4 )
      goto LABEL_20;
  }
  KeReleaseSpinLock(&v14->Ref.SpinLock, v17);
  v18 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
  KeReleaseSpinLock(&ndisMiniDriverListLock, v18);
  if ( (*(_DWORD *)(v12 + 120) & 0x80u) == 0 || (*(_DWORD *)(v12 + 120) & 0x100) != 0 )
    goto LABEL_64;
  v19 = **(_QWORD **)(v12 + 6088);
  v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v19 + 1000));
  *(_BYTE *)(v19 + 1009) = v20;
  v21 = v20;
  v22 = *(_DWORD *)(v19 + 992);
  if ( v22 != 5 )
  {
    v23 = v22 == 1;
LABEL_32:
    switch ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v19 + 888) + 16LL) + 18LL) )
    {
      case 1:
        v28 = SmFx::StateMachineEngine::StateMachineEngineImpl::AddEventToEventQueue(
                (SmFx::StateMachineEngine::StateMachineEngineImpl *)v19,
                4u);
LABEL_58:
        if ( !v28 )
          goto LABEL_64;
        if ( v23 )
          goto LABEL_60;
        goto LABEL_51;
      case 2:
        v29 = *(_BYTE *)(v19 + 978);
        v30 = 0;
        v31 = *(_BYTE *)(v19 + 979);
        v32 = v29;
        if ( v29 != v31 )
        {
          do
          {
            v33 = *(_WORD *)(v19 + 2LL * v29 + 832);
            if ( v33 == 4 )
            {
              v30 = 1;
            }
            else
            {
              v34 = v32;
              v32 = (v32 + 1) & 0xF;
              *(_WORD *)(v19 + 2 * v34 + 832) = v33;
            }
            v31 = *(_BYTE *)(v19 + 979);
            v29 = (v29 + 1) & 0xF;
          }
          while ( v29 != v31 );
          if ( v30 )
          {
            *(_WORD *)(v19 + 2LL * ((v31 - 1) & 0xF) + 832) = 4;
LABEL_51:
            KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 1000), *(_BYTE *)(v19 + 1009));
            ndisDereferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v12, MPREF_AOAC_CLEANUP);
            goto LABEL_73;
          }
        }
        v27 = (v31 + 1) & 0xF;
        if ( v27 == *(_BYTE *)(v19 + 978) )
          goto LABEL_40;
        *(_WORD *)(v19 + 2LL * v31 + 832) = 4;
        break;
      case 3:
        v24 = *(_BYTE *)(v19 + 978);
        v25 = *(unsigned __int8 *)(v19 + 979);
        v26 = v24;
        if ( v24 != (_BYTE)v25 )
        {
          while ( *(_WORD *)(v19 + 2LL * v26 + 832) != 4 )
          {
            v26 = (v26 + 1) & 0xF;
            if ( v26 == (_BYTE)v25 )
              goto LABEL_39;
          }
          goto LABEL_35;
        }
LABEL_39:
        v27 = (v25 + 1) & 0xF;
        if ( v27 == v24 )
        {
LABEL_40:
          *(_DWORD *)(v19 + 8LL * *(unsigned __int8 *)(v19 + 977) + 768) = 2;
          *(_DWORD *)(v19 + 8LL * *(unsigned __int8 *)(v19 + 977) + 772) = 4;
          *(_BYTE *)(v19 + 977) = (*(_BYTE *)(v19 + 977) + 1) & 7;
          KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 1000), *(_BYTE *)(v19 + 1009));
          if ( *(_QWORD *)(v19 + 920) )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v19 + 920))(
              *(_QWORD *)(v19 + 896),
              2,
              *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v19 + 888) + 16LL) + 16LL),
              0);
          v28 = 0;
          goto LABEL_58;
        }
        *(_WORD *)(v19 + 2 * v25 + 832) = 4;
        break;
      default:
LABEL_35:
        KeReleaseSpinLock((PKSPIN_LOCK)(v19 + 1000), v20);
        ndisDereferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v12, MPREF_AOAC_CLEANUP);
        goto LABEL_73;
    }
    v35 = *(void (__fastcall **)(_QWORD, _QWORD))(v19 + 928);
    *(_BYTE *)(v19 + 979) = v27;
    if ( v35 )
      v35(*(_QWORD *)(v19 + 896), *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v19 + 888) + 16LL) + 16LL));
    v28 = 1;
    goto LABEL_58;
  }
  if ( *(_WORD *)(v19 + 880) != 4 )
  {
    v23 = 0;
    goto LABEL_32;
  }
  if ( *(_QWORD *)(v19 + 928) )
    (*(void (__fastcall **)(_QWORD, _QWORD))(v19 + 928))(
      *(_QWORD *)(v19 + 896),
      *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v19 + 888) + 16LL) + 16LL));
  *(_WORD *)(v19 + 880) = 0;
LABEL_60:
  *(_BYTE *)(v19 + 983) = v21;
  *(_BYTE *)(v19 + 982) = 0;
  if ( v21 >= 2u )
    *(_DWORD *)(v19 + 984) = KeGetPcr()->Prcb.Number;
  else
    *(_QWORD *)(v19 + 984) = KeGetCurrentThread();
  SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue((SmFx::StateMachineEngine::StateMachineEngineImpl *)v19);
LABEL_64:
  ndisDereferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v12, MPREF_AOAC_CLEANUP);
LABEL_73:
  a2->IoStatus.Status = v6;
  IofCompleteRequest(a2, 2);
LABEL_74:
  MmUnlockPagableImageSection(ImageSectionHandle);
  _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
  return v6;
}

```

## disassembly

```asm
0x1400401c0  push    rbx
0x1400401c2  push    rbp
0x1400401c3  push    rsi
0x1400401c4  push    rdi
0x1400401c5  push    r12
0x1400401c7  push    r13
0x1400401c9  push    r14
0x1400401cb  push    r15
0x1400401cd  sub     rsp, 38h
0x1400401d1  mov     rbx, [rdx+0B8h]
0x1400401d8  mov     rdi, rcx
0x1400401db  xor     esi, esi
0x1400401dd  mov     dword ptr [rdx+30h], 103h
0x1400401e4  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400401eb  mov     [rdx+38h], rsi
0x1400401ef  mov     r13, rdx
0x1400401f2  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1400401f7  movzx   eax, byte ptr [rbx]
0x1400401fa  cmp     eax, 17h; switch 24 cases
0x1400401fd  ja      def_14004021F; jumptable 000000014004021F default case, cases 1,3-13,16,17,19-22
0x140040203  lea     rdx, cs:140000000h
0x14004020a  mov     r12d, esi
0x14004020d  movzx   eax, ds:(byte_14010415D - 140000000h)[rdx+rax]
0x140040215  mov     ecx, ds:(jpt_14004021F - 140000000h)[rdx+rax*4]
0x14004021c  add     rcx, rdx
0x14004021f  jmp     rcx; switch jump
0x140040225  mov     edx, 40h ; '@'; jumptable 000000014004021F case 0
0x14004022a  mov     r8d, 636F444Eh
0x140040230  mov     ecx, edx
0x140040232  call    cs:__imp_ExAllocatePool2
0x140040239  nop     dword ptr [rax+rax+00h]
0x14004023e  mov     rdi, rax
0x140040241  test    rax, rax
0x140040244  jnz     short loc_140040251
0x140040246  mov     r12d, 0C000009Ah
0x14004024c  jmp     loc_1400407AE; jumptable 000000014004021F case 15
0x140040251  mov     r8, cs:?ndisSecurityDescriptor@@3PEAXEA; void *
0x140040258  xorps   xmm0, xmm0
0x14004025b  movups  xmmword ptr [rax], xmm0
0x14004025e  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x140040261  mov     rcx, r13; struct _IRP *
0x140040264  movups  xmmword ptr [rax+10h], xmm0
0x140040268  movups  xmmword ptr [rax+20h], xmm0
0x14004026c  movups  xmmword ptr [rax+30h], xmm0
0x140040270  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x140040275  lea     r8, qword_1400FFBF0; void *
0x14004027c  mov     [rdi], al
0x14004027e  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x140040281  mov     rcx, r13; struct _IRP *
0x140040284  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x140040289  lea     r8, qword_140122800; void *
0x140040290  mov     [rdi+1], al
0x140040293  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x140040296  mov     rcx, r13; struct _IRP *
0x140040299  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x14004029e  mov     [rdi+2], al
0x1400402a1  mov     rax, [rbx+30h]
0x1400402a5  mov     [rax+18h], rdi
0x1400402a9  lock inc cs:dword_140122E60
0x1400402b0  jmp     loc_1400407AE; jumptable 000000014004021F case 15
0x1400402b5  mov     rax, [rbx+30h]; jumptable 000000014004021F case 18
0x1400402b9  mov     rbx, [rax+18h]
0x1400402bd  mov     rcx, rbx; struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *
0x1400402c0  call    ?ndisNicActiveHandleCleanup@@YAXPEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@@Z; ndisNicActiveHandleCleanup(_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *)
0x1400402c5  mov     rcx, [rbx+30h]; void *
0x1400402c9  test    rcx, rcx
0x1400402cc  jz      short loc_1400402D7
0x1400402ce  call    ?ndisIfDereferenceCompartmentForUser@@YAJPEAX@Z; ndisIfDereferenceCompartmentForUser(void *)
0x1400402d3  mov     [rbx+30h], rsi
0x1400402d7  mov     rbx, [rbx+20h]
0x1400402db  test    rbx, rbx
0x1400402de  jz      loc_1400407AE; jumptable 000000014004021F case 15
0x1400402e4  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1400402eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400402f2  nop     dword ptr [rax+rax+00h]
0x1400402f7  mov     rbp, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x1400402fe  xchg    ax, ax
0x140040300  test    rbp, rbp
0x140040303  jz      loc_1400403DA
0x140040309  movzx   edx, al; NewIrql
0x14004030c  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140040313  call    cs:__imp_KeReleaseSpinLock
0x14004031a  nop     dword ptr [rax+rax+00h]
0x14004031f  lea     rcx, [rbp+188h]; SpinLock
0x140040326  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004032d  nop     dword ptr [rax+rax+00h]
0x140040332  mov     rdi, [rbp+10h]
0x140040336  movzx   r15d, al
0x14004033a  test    sil, sil
0x14004033d  jnz     short loc_1400403A3
0x14004033f  nop
0x140040340  test    rdi, rdi
0x140040343  jz      short loc_1400403A3
0x140040345  cmp     rdi, rbx
0x140040348  jnz     short loc_14004039A
0x14004034a  mov     dl, 3; enum _NDIS_MP_REFTAG
0x14004034c  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14004034f  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140040354  test    al, al
0x140040356  jnz     loc_140040421
0x14004035c  mov     eax, [rbx+78h]
0x14004035f  test    eax, 80200020h
0x140040364  jnz     loc_1400403F5
0x14004036a  test    dword ptr [rbx+7Ch], 1084110h
0x140040371  mov     sil, 1
0x140040374  jnz     short loc_14004039A
0x140040376  cmp     dword ptr [rbx+5F0h], 1
0x14004037d  jnz     short loc_14004039A
0x14004037f  cmp     dword ptr [rbx+0F1Ch], 1
0x140040386  jnz     short loc_14004039A
0x140040388  mov     dl, 3; enum _NDIS_MP_REFTAG
0x14004038a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14004038d  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140040392  test    al, al
0x140040394  jnz     loc_140040421
0x14004039a  mov     rdi, [rdi+8]
0x14004039e  test    sil, sil
0x1400403a1  jz      short loc_140040340
0x1400403a3  movzx   edx, r15b; NewIrql
0x1400403a7  lea     rcx, [rbp+188h]; SpinLock
0x1400403ae  call    cs:__imp_KeReleaseSpinLock
0x1400403b5  nop     dword ptr [rax+rax+00h]
0x1400403ba  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1400403c1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400403c8  nop     dword ptr [rax+rax+00h]
0x1400403cd  mov     rbp, [rbp+8]
0x1400403d1  test    sil, sil
0x1400403d4  jz      loc_140040300
0x1400403da  movzx   edx, al; NewIrql
0x1400403dd  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x1400403e4  call    cs:__imp_KeReleaseSpinLock
0x1400403eb  nop     dword ptr [rax+rax+00h]
0x1400403f0  jmp     loc_1400407AE; jumptable 000000014004021F case 15
0x1400403f5  movzx   edx, r15b; NewIrql
0x1400403f9  lea     rcx, [rbp+188h]; SpinLock
0x140040400  call    cs:__imp_KeReleaseSpinLock
0x140040407  nop     dword ptr [rax+rax+00h]
0x14004040c  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140040413  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004041a  nop     dword ptr [rax+rax+00h]
0x14004041f  jmp     short loc_1400403DA
0x140040421  movzx   edx, r15b; NewIrql
0x140040425  lea     rcx, [rbp+188h]; SpinLock
0x14004042c  call    cs:__imp_KeReleaseSpinLock
0x140040433  nop     dword ptr [rax+rax+00h]
0x140040438  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14004043f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040446  nop     dword ptr [rax+rax+00h]
0x14004044b  movzx   edx, al; NewIrql
0x14004044e  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140040455  call    cs:__imp_KeReleaseSpinLock
0x14004045c  nop     dword ptr [rax+rax+00h]
0x140040461  mov     eax, [rbx+78h]
0x140040464  test    al, al
0x140040466  jns     loc_140040753
0x14004046c  mov     eax, [rbx+78h]
0x14004046f  bt      eax, 8
0x140040473  jb      loc_140040753
0x140040479  mov     rax, [rbx+17C8h]
0x140040480  mov     rdi, [rax]
0x140040483  lea     rsi, [rdi+3E8h]
0x14004048a  mov     rcx, rsi; SpinLock
0x14004048d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140040494  nop     dword ptr [rax+rax+00h]
0x140040499  mov     [rsi+9], al
0x14004049c  movzx   ebp, al
0x14004049f  mov     ecx, [rdi+3E0h]
0x1400404a5  mov     r10d, 4
0x1400404ab  cmp     ecx, 5
0x1400404ae  jnz     short loc_1400404F7
0x1400404b0  cmp     r10w, [rdi+370h]
0x1400404b8  jz      short loc_1400404BF
0x1400404ba  xor     r14b, r14b
0x1400404bd  jmp     short loc_1400404FE
0x1400404bf  mov     r8, [rdi+3A0h]
0x1400404c6  test    r8, r8
0x1400404c9  jz      short loc_1400404E9
0x1400404cb  mov     rax, [rdi+378h]
0x1400404d2  mov     rcx, [rdi+380h]
0x1400404d9  mov     rdx, [rax+10h]
0x1400404dd  mov     rax, r8
0x1400404e0  movzx   edx, word ptr [rdx+10h]
0x1400404e4  call    _guard_dispatch_icall
0x1400404e9  xor     eax, eax
0x1400404eb  mov     [rdi+370h], ax
0x1400404f2  jmp     loc_140040717
0x1400404f7  cmp     ecx, 1
0x1400404fa  setz    r14b
0x1400404fe  mov     rax, [rdi+378h]
0x140040505  mov     rcx, [rax+10h]
0x140040509  movzx   edx, byte ptr [rcx+12h]
0x14004050d  sub     edx, 1
0x140040510  jz      loc_1400406FF
0x140040516  sub     edx, 1
0x140040519  jz      loc_140040625
0x14004051f  cmp     edx, 1
0x140040522  jz      short loc_140040546
0x140040524  movzx   edx, bpl; NewIrql
0x140040528  mov     rcx, rsi; SpinLock
0x14004052b  call    cs:__imp_KeReleaseSpinLock
0x140040532  nop     dword ptr [rax+rax+00h]
0x140040537  mov     dl, 3; enum _NDIS_MP_REFTAG
0x140040539  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14004053c  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140040541  jmp     loc_1400407AE; jumptable 000000014004021F case 15
0x140040546  movzx   r8d, byte ptr [rdi+3D2h]
0x14004054e  movzx   edx, byte ptr [rdi+3D3h]
0x140040555  movzx   ecx, r8b
0x140040559  cmp     r8b, dl
0x14004055c  jz      short loc_140040577
0x14004055e  xchg    ax, ax
0x140040560  movzx   eax, cl
0x140040563  cmp     [rdi+rax*2+340h], r10w
0x14004056c  jz      short loc_140040524
0x14004056e  inc     cl
0x140040570  and     cl, 0Fh
0x140040573  cmp     cl, dl
0x140040575  jnz     short loc_140040560
0x140040577  lea     ecx, [rdx+1]
0x14004057a  and     cl, 0Fh
0x14004057d  cmp     cl, r8b
0x140040580  jnz     loc_140040617
0x140040586  movzx   eax, byte ptr [rdi+3D1h]
0x14004058d  mov     dword ptr [rdi+rax*8+300h], 2
0x140040598  movzx   eax, byte ptr [rdi+3D1h]
0x14004059f  mov     [rdi+rax*8+304h], r10w
0x1400405a8  xor     eax, eax
0x1400405aa  movzx   ecx, byte ptr [rdi+3D1h]
0x1400405b1  mov     [rdi+rcx*8+306h], ax
0x1400405b9  mov     rcx, rsi; SpinLock
0x1400405bc  movzx   eax, byte ptr [rdi+3D1h]
0x1400405c3  inc     al
0x1400405c5  and     al, 7
0x1400405c7  mov     [rdi+3D1h], al
0x1400405cd  movzx   edx, byte ptr [rsi+9]; NewIrql
0x1400405d1  call    cs:__imp_KeReleaseSpinLock
0x1400405d8  nop     dword ptr [rax+rax+00h]
0x1400405dd  mov     r10, [rdi+398h]
0x1400405e4  test    r10, r10
0x1400405e7  jz      short loc_140040610
0x1400405e9  mov     rax, [rdi+378h]
0x1400405f0  xor     r9d, r9d
0x1400405f3  mov     rcx, [rdi+380h]
0x1400405fa  mov     edx, 2
0x1400405ff  mov     r8, [rax+10h]
0x140040603  mov     rax, r10
0x140040606  movzx   r8d, word ptr [r8+10h]
0x14004060b  call    _guard_dispatch_icall
0x140040610  xor     al, al
0x140040612  jmp     loc_14004070A
0x140040617  mov     [rdi+rdx*2+340h], r10w
0x140040620  jmp     loc_1400406CB
0x140040625  movzx   ecx, byte ptr [rdi+3D2h]
0x14004062c  xor     r9b, r9b
0x14004062f  movzx   eax, byte ptr [rdi+3D3h]
0x140040636  movzx   edx, cl
0x140040639  cmp     cl, al
0x14004063b  jz      short loc_1400406AD
0x14004063d  nop     dword ptr [rax]
0x140040640  movzx   eax, cl
0x140040643  movzx   r8d, word ptr [rdi+rax*2+340h]
0x14004064c  cmp     r8w, r10w
0x140040650  jz      short loc_140040665
0x140040652  movzx   eax, dl
0x140040655  inc     dl
0x140040657  and     dl, 0Fh
0x14004065a  mov     [rdi+rax*2+340h], r8w
0x140040663  jmp     short loc_140040668
0x140040665  mov     r9b, 1
0x140040668  movzx   eax, byte ptr [rdi+3D3h]
0x14004066f  inc     cl
0x140040671  and     cl, 0Fh
0x140040674  cmp     cl, al
0x140040676  jnz     short loc_140040640
0x140040678  test    r9b, r9b
0x14004067b  jz      short loc_1400406AD
0x14004067d  dec     al
0x14004067f  and     eax, 0Fh
0x140040682  mov     [rdi+rax*2+340h], r10w
0x14004068b  movzx   edx, byte ptr [rsi+9]; NewIrql
0x14004068f  mov     rcx, rsi; SpinLock
0x140040692  call    cs:__imp_KeReleaseSpinLock
0x140040699  nop     dword ptr [rax+rax+00h]
0x14004069e  mov     dl, 3; enum _NDIS_MP_REFTAG
0x1400406a0  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400406a3  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x1400406a8  jmp     loc_1400407AE; jumptable 000000014004021F case 15
0x1400406ad  lea     ecx, [rax+1]
0x1400406b0  and     cl, 0Fh
0x1400406b3  cmp     cl, [rdi+3D2h]
0x1400406b9  jz      loc_140040586
0x1400406bf  movzx   eax, al
0x1400406c2  mov     [rdi+rax*2+340h], r10w
0x1400406cb  mov     r8, [rdi+3A0h]
0x1400406d2  mov     [rdi+3D3h], cl
0x1400406d8  test    r8, r8
0x1400406db  jz      short loc_1400406FB
0x1400406dd  mov     rax, [rdi+378h]
0x1400406e4  mov     rcx, [rdi+380h]
0x1400406eb  mov     rdx, [rax+10h]
  ... truncated ...
```
