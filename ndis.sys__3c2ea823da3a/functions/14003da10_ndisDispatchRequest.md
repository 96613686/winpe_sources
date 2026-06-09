# ndisDispatchRequest

- ea: `0x14003da10`
- end: `0x14003e042`
- name: `ndisDispatchRequest`
- size: `1586`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003d0f0`

## callees

- `0x14001cc80`
- `0x14001e4b0`
- `0x14003d920`
- `0x14003da10`
- `0x14003e760`
- `0x140041940`
- `0x14005f610`
- `0x140083e90`
- `0x14009febc`
- `0x1400cc3ac`
- `0x1400e6240`
- `0x14017b220`

## import_xrefs

- `ntoskrnl!MmUnlockPagableImageSection` at `0x14003e01a`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14003e01a`
- `ntoskrnl!IofCompleteRequest` at `0x14003e007`
- `ntoskrnl!IofCompleteRequest` at `0x14003e007`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dfc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dfc2`
- `ntoskrnl!ExAllocatePool2` at `0x14003da82`
- `ntoskrnl!ExAllocatePool2` at `0x14003da82`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003db63`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dbfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dc34`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dc50`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dc7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dca5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dd7b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003de21`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dee2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003db63`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dbfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dc34`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dc50`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dc7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dca5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dd7b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003de21`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003dee2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003db3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003db76`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dc11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dc63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dc8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dcdd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003db3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003db76`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dc11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dc63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dc8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003dcdd`

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
        v8[1] = ndisCheckAccess(a2, CurrentStackLocation, qword_1400FABB0);
        v8[2] = ndisCheckAccess(a2, CurrentStackLocation, qword_14011C800);
        CurrentStackLocation->FileObject->FsContext = v8;
        _InterlockedIncrement(&dword_14011CE60);
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
      _InterlockedDecrement(&dword_14011CE60);
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
0x14003da10  push    rbx
0x14003da12  push    rbp
0x14003da13  push    rsi
0x14003da14  push    rdi
0x14003da15  push    r12
0x14003da17  push    r13
0x14003da19  push    r14
0x14003da1b  push    r15
0x14003da1d  sub     rsp, 38h
0x14003da21  mov     rbx, [rdx+0B8h]
0x14003da28  mov     rdi, rcx
0x14003da2b  xor     esi, esi
0x14003da2d  mov     dword ptr [rdx+30h], 103h
0x14003da34  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14003da3b  mov     [rdx+38h], rsi
0x14003da3f  mov     r13, rdx
0x14003da42  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14003da47  movzx   eax, byte ptr [rbx]
0x14003da4a  cmp     eax, 17h; switch 24 cases
0x14003da4d  ja      def_14003DA6F; jumptable 000000014003DA6F default case, cases 1,3-13,16,17,19-22
0x14003da53  lea     rdx, cs:140000000h
0x14003da5a  mov     r12d, esi
0x14003da5d  movzx   eax, ds:(byte_1400FF155 - 140000000h)[rdx+rax]
0x14003da65  mov     ecx, ds:(jpt_14003DA6F - 140000000h)[rdx+rax*4]
0x14003da6c  add     rcx, rdx
0x14003da6f  jmp     rcx; switch jump
0x14003da75  mov     edx, 40h ; '@'; jumptable 000000014003DA6F case 0
0x14003da7a  mov     r8d, 636F444Eh
0x14003da80  mov     ecx, edx
0x14003da82  call    cs:__imp_ExAllocatePool2
0x14003da89  nop     dword ptr [rax+rax+00h]
0x14003da8e  mov     rdi, rax
0x14003da91  test    rax, rax
0x14003da94  jnz     short loc_14003DAA1
0x14003da96  mov     r12d, 0C000009Ah
0x14003da9c  jmp     loc_14003DFFE; jumptable 000000014003DA6F case 15
0x14003daa1  mov     r8, cs:?ndisSecurityDescriptor@@3PEAXEA; void *
0x14003daa8  xorps   xmm0, xmm0
0x14003daab  movups  xmmword ptr [rax], xmm0
0x14003daae  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x14003dab1  mov     rcx, r13; struct _IRP *
0x14003dab4  movups  xmmword ptr [rax+10h], xmm0
0x14003dab8  movups  xmmword ptr [rax+20h], xmm0
0x14003dabc  movups  xmmword ptr [rax+30h], xmm0
0x14003dac0  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x14003dac5  lea     r8, qword_1400FABB0; void *
0x14003dacc  mov     [rdi], al
0x14003dace  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x14003dad1  mov     rcx, r13; struct _IRP *
0x14003dad4  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x14003dad9  lea     r8, qword_14011C800; void *
0x14003dae0  mov     [rdi+1], al
0x14003dae3  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x14003dae6  mov     rcx, r13; struct _IRP *
0x14003dae9  call    ?ndisCheckAccess@@YAEPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAX@Z; ndisCheckAccess(_IRP *,_IO_STACK_LOCATION *,void *)
0x14003daee  mov     [rdi+2], al
0x14003daf1  mov     rax, [rbx+30h]
0x14003daf5  mov     [rax+18h], rdi
0x14003daf9  lock inc cs:dword_14011CE60
0x14003db00  jmp     loc_14003DFFE; jumptable 000000014003DA6F case 15
0x14003db05  mov     rax, [rbx+30h]; jumptable 000000014003DA6F case 18
0x14003db09  mov     rbx, [rax+18h]
0x14003db0d  mov     rcx, rbx; struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *
0x14003db10  call    ?ndisNicActiveHandleCleanup@@YAXPEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@@Z; ndisNicActiveHandleCleanup(_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *)
0x14003db15  mov     rcx, [rbx+30h]; void *
0x14003db19  test    rcx, rcx
0x14003db1c  jz      short loc_14003DB27
0x14003db1e  call    ?ndisIfDereferenceCompartmentForUser@@YAJPEAX@Z; ndisIfDereferenceCompartmentForUser(void *)
0x14003db23  mov     [rbx+30h], rsi
0x14003db27  mov     rbx, [rbx+20h]
0x14003db2b  test    rbx, rbx
0x14003db2e  jz      loc_14003DFFE; jumptable 000000014003DA6F case 15
0x14003db34  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003db3b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003db42  nop     dword ptr [rax+rax+00h]
0x14003db47  mov     rbp, cs:?ndisMiniDriverList@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA; _NDIS_M_DRIVER_BLOCK * ndisMiniDriverList
0x14003db4e  xchg    ax, ax
0x14003db50  test    rbp, rbp
0x14003db53  jz      loc_14003DC2A
0x14003db59  movzx   edx, al; NewIrql
0x14003db5c  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003db63  call    cs:__imp_KeReleaseSpinLock
0x14003db6a  nop     dword ptr [rax+rax+00h]
0x14003db6f  lea     rcx, [rbp+188h]; SpinLock
0x14003db76  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003db7d  nop     dword ptr [rax+rax+00h]
0x14003db82  mov     rdi, [rbp+10h]
0x14003db86  movzx   r15d, al
0x14003db8a  test    sil, sil
0x14003db8d  jnz     short loc_14003DBF3
0x14003db8f  nop
0x14003db90  test    rdi, rdi
0x14003db93  jz      short loc_14003DBF3
0x14003db95  cmp     rdi, rbx
0x14003db98  jnz     short loc_14003DBEA
0x14003db9a  mov     dl, 3; enum _NDIS_MP_REFTAG
0x14003db9c  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003db9f  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14003dba4  test    al, al
0x14003dba6  jnz     loc_14003DC71
0x14003dbac  mov     eax, [rbx+78h]
0x14003dbaf  test    eax, 80200020h
0x14003dbb4  jnz     loc_14003DC45
0x14003dbba  test    dword ptr [rbx+7Ch], 1084110h
0x14003dbc1  mov     sil, 1
0x14003dbc4  jnz     short loc_14003DBEA
0x14003dbc6  cmp     dword ptr [rbx+5F0h], 1
0x14003dbcd  jnz     short loc_14003DBEA
0x14003dbcf  cmp     dword ptr [rbx+0F1Ch], 1
0x14003dbd6  jnz     short loc_14003DBEA
0x14003dbd8  mov     dl, 3; enum _NDIS_MP_REFTAG
0x14003dbda  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003dbdd  call    ?ndisReferenceMiniport@@YAEPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14003dbe2  test    al, al
0x14003dbe4  jnz     loc_14003DC71
0x14003dbea  mov     rdi, [rdi+8]
0x14003dbee  test    sil, sil
0x14003dbf1  jz      short loc_14003DB90
0x14003dbf3  movzx   edx, r15b; NewIrql
0x14003dbf7  lea     rcx, [rbp+188h]; SpinLock
0x14003dbfe  call    cs:__imp_KeReleaseSpinLock
0x14003dc05  nop     dword ptr [rax+rax+00h]
0x14003dc0a  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003dc11  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003dc18  nop     dword ptr [rax+rax+00h]
0x14003dc1d  mov     rbp, [rbp+8]
0x14003dc21  test    sil, sil
0x14003dc24  jz      loc_14003DB50
0x14003dc2a  movzx   edx, al; NewIrql
0x14003dc2d  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003dc34  call    cs:__imp_KeReleaseSpinLock
0x14003dc3b  nop     dword ptr [rax+rax+00h]
0x14003dc40  jmp     loc_14003DFFE; jumptable 000000014003DA6F case 15
0x14003dc45  movzx   edx, r15b; NewIrql
0x14003dc49  lea     rcx, [rbp+188h]; SpinLock
0x14003dc50  call    cs:__imp_KeReleaseSpinLock
0x14003dc57  nop     dword ptr [rax+rax+00h]
0x14003dc5c  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003dc63  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003dc6a  nop     dword ptr [rax+rax+00h]
0x14003dc6f  jmp     short loc_14003DC2A
0x14003dc71  movzx   edx, r15b; NewIrql
0x14003dc75  lea     rcx, [rbp+188h]; SpinLock
0x14003dc7c  call    cs:__imp_KeReleaseSpinLock
0x14003dc83  nop     dword ptr [rax+rax+00h]
0x14003dc88  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003dc8f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003dc96  nop     dword ptr [rax+rax+00h]
0x14003dc9b  movzx   edx, al; NewIrql
0x14003dc9e  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14003dca5  call    cs:__imp_KeReleaseSpinLock
0x14003dcac  nop     dword ptr [rax+rax+00h]
0x14003dcb1  mov     eax, [rbx+78h]
0x14003dcb4  test    al, al
0x14003dcb6  jns     loc_14003DFA3
0x14003dcbc  mov     eax, [rbx+78h]
0x14003dcbf  bt      eax, 8
0x14003dcc3  jb      loc_14003DFA3
0x14003dcc9  mov     rax, [rbx+17C8h]
0x14003dcd0  mov     rdi, [rax]
0x14003dcd3  lea     rsi, [rdi+3E8h]
0x14003dcda  mov     rcx, rsi; SpinLock
0x14003dcdd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003dce4  nop     dword ptr [rax+rax+00h]
0x14003dce9  mov     [rsi+9], al
0x14003dcec  movzx   ebp, al
0x14003dcef  mov     ecx, [rdi+3E0h]
0x14003dcf5  mov     r10d, 4
0x14003dcfb  cmp     ecx, 5
0x14003dcfe  jnz     short loc_14003DD47
0x14003dd00  cmp     r10w, [rdi+370h]
0x14003dd08  jz      short loc_14003DD0F
0x14003dd0a  xor     r14b, r14b
0x14003dd0d  jmp     short loc_14003DD4E
0x14003dd0f  mov     r8, [rdi+3A0h]
0x14003dd16  test    r8, r8
0x14003dd19  jz      short loc_14003DD39
0x14003dd1b  mov     rax, [rdi+378h]
0x14003dd22  mov     rcx, [rdi+380h]
0x14003dd29  mov     rdx, [rax+10h]
0x14003dd2d  mov     rax, r8
0x14003dd30  movzx   edx, word ptr [rdx+10h]
0x14003dd34  call    _guard_dispatch_icall
0x14003dd39  xor     eax, eax
0x14003dd3b  mov     [rdi+370h], ax
0x14003dd42  jmp     loc_14003DF67
0x14003dd47  cmp     ecx, 1
0x14003dd4a  setz    r14b
0x14003dd4e  mov     rax, [rdi+378h]
0x14003dd55  mov     rcx, [rax+10h]
0x14003dd59  movzx   edx, byte ptr [rcx+12h]
0x14003dd5d  sub     edx, 1
0x14003dd60  jz      loc_14003DF4F
0x14003dd66  sub     edx, 1
0x14003dd69  jz      loc_14003DE75
0x14003dd6f  cmp     edx, 1
0x14003dd72  jz      short loc_14003DD96
0x14003dd74  movzx   edx, bpl; NewIrql
0x14003dd78  mov     rcx, rsi; SpinLock
0x14003dd7b  call    cs:__imp_KeReleaseSpinLock
0x14003dd82  nop     dword ptr [rax+rax+00h]
0x14003dd87  mov     dl, 3; enum _NDIS_MP_REFTAG
0x14003dd89  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003dd8c  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14003dd91  jmp     loc_14003DFFE; jumptable 000000014003DA6F case 15
0x14003dd96  movzx   r8d, byte ptr [rdi+3D2h]
0x14003dd9e  movzx   edx, byte ptr [rdi+3D3h]
0x14003dda5  movzx   ecx, r8b
0x14003dda9  cmp     r8b, dl
0x14003ddac  jz      short loc_14003DDC7
0x14003ddae  xchg    ax, ax
0x14003ddb0  movzx   eax, cl
0x14003ddb3  cmp     [rdi+rax*2+340h], r10w
0x14003ddbc  jz      short loc_14003DD74
0x14003ddbe  inc     cl
0x14003ddc0  and     cl, 0Fh
0x14003ddc3  cmp     cl, dl
0x14003ddc5  jnz     short loc_14003DDB0
0x14003ddc7  lea     ecx, [rdx+1]
0x14003ddca  and     cl, 0Fh
0x14003ddcd  cmp     cl, r8b
0x14003ddd0  jnz     loc_14003DE67
0x14003ddd6  movzx   eax, byte ptr [rdi+3D1h]
0x14003dddd  mov     dword ptr [rdi+rax*8+300h], 2
0x14003dde8  movzx   eax, byte ptr [rdi+3D1h]
0x14003ddef  mov     [rdi+rax*8+304h], r10w
0x14003ddf8  xor     eax, eax
0x14003ddfa  movzx   ecx, byte ptr [rdi+3D1h]
0x14003de01  mov     [rdi+rcx*8+306h], ax
0x14003de09  mov     rcx, rsi; SpinLock
0x14003de0c  movzx   eax, byte ptr [rdi+3D1h]
0x14003de13  inc     al
0x14003de15  and     al, 7
0x14003de17  mov     [rdi+3D1h], al
0x14003de1d  movzx   edx, byte ptr [rsi+9]; NewIrql
0x14003de21  call    cs:__imp_KeReleaseSpinLock
0x14003de28  nop     dword ptr [rax+rax+00h]
0x14003de2d  mov     r10, [rdi+398h]
0x14003de34  test    r10, r10
0x14003de37  jz      short loc_14003DE60
0x14003de39  mov     rax, [rdi+378h]
0x14003de40  xor     r9d, r9d
0x14003de43  mov     rcx, [rdi+380h]
0x14003de4a  mov     edx, 2
0x14003de4f  mov     r8, [rax+10h]
0x14003de53  mov     rax, r10
0x14003de56  movzx   r8d, word ptr [r8+10h]
0x14003de5b  call    _guard_dispatch_icall
0x14003de60  xor     al, al
0x14003de62  jmp     loc_14003DF5A
0x14003de67  mov     [rdi+rdx*2+340h], r10w
0x14003de70  jmp     loc_14003DF1B
0x14003de75  movzx   ecx, byte ptr [rdi+3D2h]
0x14003de7c  xor     r9b, r9b
0x14003de7f  movzx   eax, byte ptr [rdi+3D3h]
0x14003de86  movzx   edx, cl
0x14003de89  cmp     cl, al
0x14003de8b  jz      short loc_14003DEFD
0x14003de8d  nop     dword ptr [rax]
0x14003de90  movzx   eax, cl
0x14003de93  movzx   r8d, word ptr [rdi+rax*2+340h]
0x14003de9c  cmp     r8w, r10w
0x14003dea0  jz      short loc_14003DEB5
0x14003dea2  movzx   eax, dl
0x14003dea5  inc     dl
0x14003dea7  and     dl, 0Fh
0x14003deaa  mov     [rdi+rax*2+340h], r8w
0x14003deb3  jmp     short loc_14003DEB8
0x14003deb5  mov     r9b, 1
0x14003deb8  movzx   eax, byte ptr [rdi+3D3h]
0x14003debf  inc     cl
0x14003dec1  and     cl, 0Fh
0x14003dec4  cmp     cl, al
0x14003dec6  jnz     short loc_14003DE90
0x14003dec8  test    r9b, r9b
0x14003decb  jz      short loc_14003DEFD
0x14003decd  dec     al
0x14003decf  and     eax, 0Fh
0x14003ded2  mov     [rdi+rax*2+340h], r10w
0x14003dedb  movzx   edx, byte ptr [rsi+9]; NewIrql
0x14003dedf  mov     rcx, rsi; SpinLock
0x14003dee2  call    cs:__imp_KeReleaseSpinLock
0x14003dee9  nop     dword ptr [rax+rax+00h]
0x14003deee  mov     dl, 3; enum _NDIS_MP_REFTAG
0x14003def0  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003def3  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14003def8  jmp     loc_14003DFFE; jumptable 000000014003DA6F case 15
0x14003defd  lea     ecx, [rax+1]
0x14003df00  and     cl, 0Fh
0x14003df03  cmp     cl, [rdi+3D2h]
0x14003df09  jz      loc_14003DDD6
0x14003df0f  movzx   eax, al
0x14003df12  mov     [rdi+rax*2+340h], r10w
0x14003df1b  mov     r8, [rdi+3A0h]
0x14003df22  mov     [rdi+3D3h], cl
0x14003df28  test    r8, r8
0x14003df2b  jz      short loc_14003DF4B
0x14003df2d  mov     rax, [rdi+378h]
0x14003df34  mov     rcx, [rdi+380h]
0x14003df3b  mov     rdx, [rax+10h]
  ... truncated ...
```
