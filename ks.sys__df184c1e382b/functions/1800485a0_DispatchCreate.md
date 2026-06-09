# DispatchCreate

- ea: `0x1800485a0`
- end: `0x180048ae2`
- name: `DispatchCreate`
- size: `1346`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047fe0`
- `0x1800481d0`

## callees

- `0x180019cb0`
- `0x1800485a0`
- `0x180048ae8`
- `0x180048b60`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180048725`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x18004898e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x180048725`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x18004898e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180048a4f`
- `ntoskrnl!RtlInitUnicodeString` at `0x180048a4f`
- `ntoskrnl!ExGetPreviousMode` at `0x1800486d8`
- `ntoskrnl!ExGetPreviousMode` at `0x1800486d8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800485f6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800487f6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800485f6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800487f6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800485e3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800486f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800487e3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800485e3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800486f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800487e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18004876d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18004876d`
- `ntoskrnl!_wcsnicmp` at `0x180048662`
- `ntoskrnl!_wcsnicmp` at `0x180048662`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1800486a1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18004882a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1800486a1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18004882a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800486ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180048779`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180048836`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800486ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180048779`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180048836`
- `ntoskrnl!SeAppendPrivileges` at `0x1800489ff`
- `ntoskrnl!SeAppendPrivileges` at `0x1800489ff`
- `ntoskrnl!SeFreePrivileges` at `0x180048a10`
- `ntoskrnl!SeFreePrivileges` at `0x180048a10`
- `ntoskrnl!RtlMapGenericMask` at `0x180048738`
- `ntoskrnl!RtlMapGenericMask` at `0x180048738`
- `ntoskrnl!SeAccessCheck` at `0x1800489dd`
- `ntoskrnl!SeAccessCheck` at `0x1800489dd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180048709`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180048709`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x180048a9c`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x180048a9c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x180048ab0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x180048ab0`
- `ntoskrnl!SeLockSubjectContext` at `0x180048976`
- `ntoskrnl!SeLockSubjectContext` at `0x180048976`
- `ntoskrnl!IofCompleteRequest` at `0x1800488cf`
- `ntoskrnl!IofCompleteRequest` at `0x180048ad1`
- `ntoskrnl!IofCompleteRequest` at `0x1800488cf`
- `ntoskrnl!IofCompleteRequest` at `0x180048ad1`

## pseudocode

```c
__int64 __fastcall DispatchCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  IRP *v3; // rbp
  PFILE_OBJECT FileObject; // rcx
  struct _FILE_OBJECT *RelatedFileObject; // r8
  __int64 v6; // r14
  PFILE_OBJECT v7; // rax
  int Length; // ecx
  unsigned int v9; // ebp
  __int64 Item; // rbx
  const wchar_t *v11; // r15
  __int64 v12; // r13
  __int64 v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // rsi
  __int64 v16; // r12
  struct _IO_STACK_LOCATION *v17; // r13
  __int64 v18; // r15
  PIO_SECURITY_CONTEXT v19; // rdi
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  unsigned int v21; // edi
  __int64 v23; // rdx
  __int64 *v24; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rsi
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // rcx
  ACCESS_MASK DesiredAccess; // edi
  struct _SECURITY_SUBJECT_CONTEXT *AccessState; // rsi
  void *v29; // rbp
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v31; // si
  __int64 v32; // rdi
  UNICODE_STRING *p_DestinationString; // r8
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-78h] BYREF
  __int128 v35; // [rsp+58h] [rbp-70h] BYREF
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-60h] BYREF
  DWORD GrantedAccess; // [rsp+E0h] [rbp+18h] BYREF
  int AccessStatus; // [rsp+E8h] [rbp+20h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = a2;
  FileObject = CurrentStackLocation->FileObject;
  RelatedFileObject = FileObject->RelatedFileObject;
  if ( RelatedFileObject )
  {
    if ( (RelatedFileObject->Flags & 0x800) == 0 && RelatedFileObject->FsContext )
    {
      v6 = *(_QWORD *)CurrentStackLocation->DeviceObject->DeviceExtension;
      Item = FindAndReferenceCreateItem(FileObject->FileName.Buffer);
      goto LABEL_18;
    }
    goto LABEL_35;
  }
  v6 = *(_QWORD *)CurrentStackLocation->DeviceObject->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 208));
  v7 = CurrentStackLocation->FileObject;
  Length = v7->FileName.Length;
  if ( !(_WORD)Length )
  {
    Item = FindAndReferenceCreateItem(0);
    goto LABEL_17;
  }
  v9 = Length - 2;
  Item = *(_QWORD *)v6;
  v11 = v7->FileName.Buffer + 1;
  v12 = 0;
  while ( Item != v6 )
  {
    v13 = *(_QWORD *)(Item + 16);
    if ( !*(_QWORD *)v13 )
      goto LABEL_6;
    if ( (*(_DWORD *)(v13 + 40) & 2) != 0 )
    {
      v12 = Item;
    }
    else
    {
      v14 = *(unsigned __int16 *)(v13 + 16);
      if ( v9 < v14 )
        goto LABEL_6;
      if ( *(_WORD *)(v13 + 16) )
      {
        v15 = *(unsigned __int16 *)(v13 + 16);
        if ( _wcsnicmp(v11, *(const wchar_t **)(v13 + 24), v15 >> 1) )
          goto LABEL_6;
      }
      else
      {
        v15 = 0;
      }
      if ( (v9 == v14 || v11 && v11[v15 >> 1] == 92)
        && ((*(_DWORD *)(*(_QWORD *)(Item + 16) + 40LL) & 4) == 0 || v9 <= v14 + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(Item + 32));
        goto LABEL_16;
      }
    }
LABEL_6:
    Item = *(_QWORD *)Item;
  }
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 32));
  Item = v12;
LABEL_16:
  v3 = a2;
LABEL_17:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 208));
  KeLeaveCriticalRegion();
LABEL_18:
  if ( !Item )
  {
LABEL_35:
    v3->IoStatus.Status = -1073741772;
    IofCompleteRequest(v3, 0);
    return 3221225524LL;
  }
  v16 = *(_QWORD *)(Item + 16);
  v17 = v3->Tail.Overlay.CurrentStackLocation;
  AccessStatus = 0;
  if ( !ExGetPreviousMode() && (v17->Flags & 1) == 0 )
    goto LABEL_23;
  v18 = *(_QWORD *)v17->DeviceObject->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(v18 + 16), 1u);
  if ( *(_QWORD *)(v16 + 32) && *(_WORD *)(v16 + 16) )
  {
    SecurityContext = v17->Parameters.Create.SecurityContext;
    GrantedAccess = 0;
    DestinationString = 0;
    Privileges = 0;
    p_SubjectSecurityContext = &SecurityContext->AccessState->SubjectSecurityContext;
    *(_QWORD *)&v35 = SecurityContext;
    SeLockSubjectContext(p_SubjectSecurityContext);
    DesiredAccess = SecurityContext->DesiredAccess;
    AccessState = (struct _SECURITY_SUBJECT_CONTEXT *)SecurityContext->AccessState;
    v29 = *(void **)(v16 + 32);
    GenericMapping = IoGetFileObjectGenericMapping();
    v31 = SeAccessCheck(
            v29,
            AccessState + 1,
            1u,
            DesiredAccess,
            0,
            &Privileges,
            GenericMapping,
            1,
            &GrantedAccess,
            &AccessStatus);
    v32 = v35;
    if ( Privileges )
    {
      SeAppendPrivileges(*(PACCESS_STATE *)(v35 + 8), Privileges);
      SeFreePrivileges(Privileges);
    }
    if ( v31 )
    {
      *(_DWORD *)(*(_QWORD *)(v32 + 8) + 20LL) |= GrantedAccess;
      *(_DWORD *)(*(_QWORD *)(v32 + 8) + 16LL) &= ~(GrantedAccess | 0x2000000);
    }
    RtlInitUnicodeString(&DestinationString, L"File");
    p_DestinationString = &DestinationString;
    if ( *(_WORD *)(v16 + 16) )
      p_DestinationString = (UNICODE_STRING *)(v16 + 16);
    SeOpenObjectAuditAlarm(
      &DestinationString,
      v17->DeviceObject,
      p_DestinationString,
      *(PSECURITY_DESCRIPTOR *)(v16 + 32),
      *(PACCESS_STATE *)(v32 + 8),
      0,
      v31,
      1,
      (PBOOLEAN)(*(_QWORD *)(v32 + 8) + 10LL));
    SeUnlockSubjectContext((PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(v32 + 8) + 32LL));
    v3 = a2;
  }
  else
  {
    v19 = v17->Parameters.Create.SecurityContext;
    FileObjectGenericMapping = IoGetFileObjectGenericMapping();
    RtlMapGenericMask(&v19->DesiredAccess, FileObjectGenericMapping);
    v19->AccessState->PreviouslyGrantedAccess |= v19->DesiredAccess;
    v19->AccessState->RemainingDesiredAccess &= ~(v19->DesiredAccess | 0x2000000);
    AccessStatus = 0;
  }
  ExReleaseResourceLite((PERESOURCE)(v18 + 16));
  KeLeaveCriticalRegion();
  v21 = AccessStatus;
  if ( AccessStatus < 0 )
  {
    v3->IoStatus.Status = AccessStatus;
    IofCompleteRequest(v3, 0);
  }
  else
  {
LABEL_23:
    v3->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = *(struct _LIST_ENTRY **)(Item + 16);
    v21 = (**(__int64 (__fastcall ***)(__int64, IRP *))(Item + 16))(a1, v3);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Item + 32), 0xFFFFFFFF) == 1 )
  {
    v35 = 0;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 208));
    v23 = *(_QWORD *)Item;
    if ( *(_QWORD *)(*(_QWORD *)Item + 8LL) != Item || (v24 = *(__int64 **)(Item + 8), *v24 != Item) )
      __fastfail(3u);
    *v24 = v23;
    *(_QWORD *)(v23 + 8) = v24;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 208));
    KeLeaveCriticalRegion();
    *((_QWORD *)&v35 + 1) = Item;
    *(_QWORD *)Item = &v35;
    *(_QWORD *)&v35 = Item;
    *(_QWORD *)(Item + 8) = &v35;
    FreeCreateEntries(&v35);
  }
  return v21;
}

```

## disassembly

```asm
0x1800485a0  mov     [rsp+Irp], rdx
0x1800485a5  mov     [rsp+arg_0], rcx
0x1800485aa  push    rbx
0x1800485ab  push    rbp
0x1800485ac  push    rsi
0x1800485ad  push    rdi
0x1800485ae  push    r12
0x1800485b0  push    r13
0x1800485b2  push    r14
0x1800485b4  push    r15
0x1800485b6  sub     rsp, 88h
0x1800485bd  mov     rbx, [rdx+0B8h]
0x1800485c4  mov     rbp, rdx
0x1800485c7  mov     rcx, [rbx+30h]
0x1800485cb  mov     r8, [rcx+40h]
0x1800485cf  test    r8, r8
0x1800485d2  jnz     loc_18004886C
0x1800485d8  mov     rax, [rbx+28h]
0x1800485dc  mov     rcx, [rax+40h]
0x1800485e0  mov     r14, [rcx]
0x1800485e3  call    cs:__imp_KeEnterCriticalRegion
0x1800485ea  nop     dword ptr [rax+rax+00h]
0x1800485ef  lea     rcx, [r14+0D0h]; FastMutex
0x1800485f6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1800485fd  nop     dword ptr [rax+rax+00h]
0x180048602  mov     rax, [rbx+30h]
0x180048606  movzx   ecx, word ptr [rax+58h]
0x18004860a  test    cx, cx
0x18004860d  jz      loc_180048928
0x180048613  mov     r15, [rax+60h]
0x180048617  lea     ebp, [rcx-2]
0x18004861a  mov     rbx, [r14]
0x18004861d  add     r15, 2
0x180048621  xor     r13d, r13d
0x180048624  cmp     rbx, r14
0x180048627  jz      loc_1800488E5
0x18004862d  mov     rdx, [rbx+10h]
0x180048631  cmp     qword ptr [rdx], 0
0x180048635  jnz     short loc_18004863C
0x180048637  mov     rbx, [rbx]
0x18004863a  jmp     short loc_180048624
0x18004863c  mov     eax, [rdx+28h]
0x18004863f  test    al, 2
0x180048641  jnz     loc_180048919
0x180048647  movzx   edi, word ptr [rdx+10h]
0x18004864b  cmp     ebp, edi
0x18004864d  jb      short loc_180048637
0x18004864f  test    edi, edi
0x180048651  jz      short loc_180048674
0x180048653  mov     rdx, [rdx+18h]; Str2
0x180048657  mov     r8d, edi
0x18004865a  shr     r8, 1; MaxCount
0x18004865d  mov     rcx, r15; Str1
0x180048660  mov     esi, edi
0x180048662  call    cs:__imp__wcsnicmp
0x180048669  nop     dword ptr [rax+rax+00h]
0x18004866e  test    eax, eax
0x180048670  jnz     short loc_180048637
0x180048672  jmp     short loc_180048676
0x180048674  xor     esi, esi
0x180048676  cmp     ebp, edi
0x180048678  jnz     loc_1800488A6
0x18004867e  mov     rax, [rbx+10h]
0x180048682  mov     ecx, [rax+28h]
0x180048685  test    cl, 4
0x180048688  jnz     loc_1800488F2
0x18004868e  lock inc dword ptr [rbx+20h]
0x180048692  mov     rbp, [rsp+0C8h+Irp]
0x18004869a  lea     rcx, [r14+0D0h]; FastMutex
0x1800486a1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1800486a8  nop     dword ptr [rax+rax+00h]
0x1800486ad  call    cs:__imp_KeLeaveCriticalRegion
0x1800486b4  nop     dword ptr [rax+rax+00h]
0x1800486b9  test    rbx, rbx
0x1800486bc  jz      loc_1800488C3
0x1800486c2  mov     r12, [rbx+10h]
0x1800486c6  mov     r13, [rbp+0B8h]
0x1800486cd  mov     [rsp+0C8h+arg_18], 0
0x1800486d8  call    cs:__imp_ExGetPreviousMode
0x1800486df  nop     dword ptr [rax+rax+00h]
0x1800486e4  test    al, al
0x1800486e6  jz      loc_180048909
0x1800486ec  mov     rax, [r13+28h]
0x1800486f0  mov     rcx, [rax+40h]
0x1800486f4  mov     r15, [rcx]
0x1800486f7  call    cs:__imp_KeEnterCriticalRegion
0x1800486fe  nop     dword ptr [rax+rax+00h]
0x180048703  mov     dl, 1; Wait
0x180048705  lea     rcx, [r15+10h]; Resource
0x180048709  call    cs:__imp_ExAcquireResourceSharedLite
0x180048710  nop     dword ptr [rax+rax+00h]
0x180048715  cmp     qword ptr [r12+20h], 0
0x18004871b  jnz     loc_18004893C
0x180048721  mov     rdi, [r13+8]
0x180048725  call    cs:__imp_IoGetFileObjectGenericMapping
0x18004872c  nop     dword ptr [rax+rax+00h]
0x180048731  mov     rdx, rax; GenericMapping
0x180048734  lea     rcx, [rdi+10h]; AccessMask
0x180048738  call    cs:__imp_RtlMapGenericMask
0x18004873f  nop     dword ptr [rax+rax+00h]
0x180048744  mov     rdx, [rdi+8]
0x180048748  mov     eax, [rdi+10h]
0x18004874b  or      [rdx+14h], eax
0x18004874e  mov     eax, [rdi+10h]
0x180048751  mov     rdx, [rdi+8]
0x180048755  bts     eax, 19h
0x180048759  not     eax
0x18004875b  and     [rdx+10h], eax
0x18004875e  mov     [rsp+0C8h+arg_18], 0
0x180048769  lea     rcx, [r15+10h]; Resource
0x18004876d  call    cs:__imp_ExReleaseResourceLite
0x180048774  nop     dword ptr [rax+rax+00h]
0x180048779  call    cs:__imp_KeLeaveCriticalRegion
0x180048780  nop     dword ptr [rax+rax+00h]
0x180048785  mov     edi, [rsp+0C8h+arg_18]
0x18004878c  test    edi, edi
0x18004878e  js      loc_180048AC9
0x180048794  mov     rax, [rbx+10h]
0x180048798  mov     rdx, rbp
0x18004879b  mov     rcx, [rsp+0C8h+arg_0]
0x1800487a3  mov     [rbp+78h], rax
0x1800487a7  mov     rax, [rbx+10h]
0x1800487ab  mov     rax, [rax]
0x1800487ae  call    _guard_dispatch_icall
0x1800487b3  mov     edi, eax
0x1800487b5  mov     eax, 0FFFFFFFFh
0x1800487ba  lock xadd [rbx+20h], eax
0x1800487bf  cmp     eax, 1
0x1800487c2  jz      short loc_1800487DB
0x1800487c4  mov     eax, edi
0x1800487c6  add     rsp, 88h
0x1800487cd  pop     r15
0x1800487cf  pop     r14
0x1800487d1  pop     r13
0x1800487d3  pop     r12
0x1800487d5  pop     rdi
0x1800487d6  pop     rsi
0x1800487d7  pop     rbp
0x1800487d8  pop     rbx
0x1800487d9  retn
0x1800487db  xorps   xmm0, xmm0
0x1800487de  movups  [rsp+0C8h+var_70], xmm0
0x1800487e3  call    cs:__imp_KeEnterCriticalRegion
0x1800487ea  nop     dword ptr [rax+rax+00h]
0x1800487ef  lea     rcx, [r14+0D0h]; FastMutex
0x1800487f6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1800487fd  nop     dword ptr [rax+rax+00h]
0x180048802  mov     rdx, [rbx]
0x180048805  cmp     [rdx+8], rbx
0x180048809  jnz     loc_180048902
0x18004880f  mov     rax, [rbx+8]
0x180048813  cmp     [rax], rbx
0x180048816  jnz     loc_180048902
0x18004881c  mov     [rax], rdx
0x18004881f  lea     rcx, [r14+0D0h]; FastMutex
0x180048826  mov     [rdx+8], rax
0x18004882a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180048831  nop     dword ptr [rax+rax+00h]
0x180048836  call    cs:__imp_KeLeaveCriticalRegion
0x18004883d  nop     dword ptr [rax+rax+00h]
0x180048842  lea     rax, [rsp+0C8h+var_70]
0x180048847  mov     qword ptr [rsp+0C8h+var_70+8], rbx
0x18004884c  mov     [rbx], rax
0x18004884f  lea     rcx, [rsp+0C8h+var_70]
0x180048854  lea     rax, [rsp+0C8h+var_70]
0x180048859  mov     qword ptr [rsp+0C8h+var_70], rbx
0x18004885e  mov     [rbx+8], rax
0x180048862  call    FreeCreateEntries
0x180048867  jmp     loc_1800487C4
0x18004886c  test    dword ptr [r8+50h], 800h
0x180048874  jnz     short loc_1800488C3
0x180048876  mov     r8, [r8+18h]
0x18004887a  test    r8, r8
0x18004887d  jz      short loc_1800488C3
0x18004887f  mov     rax, [rbx+28h]
0x180048883  mov     r8, [r8]
0x180048886  add     r8, 8
0x18004888a  mov     rdx, [rax+40h]
0x18004888e  mov     r14, [rdx]
0x180048891  movzx   edx, word ptr [rcx+58h]
0x180048895  mov     rcx, [rcx+60h]; Str1
0x180048899  call    FindAndReferenceCreateItem
0x18004889e  mov     rbx, rax
0x1800488a1  jmp     loc_1800486B9
0x1800488a6  test    r15, r15
0x1800488a9  jz      loc_180048637
0x1800488af  shr     rsi, 1
0x1800488b2  cmp     word ptr [r15+rsi*2], 5Ch ; '\'
0x1800488b8  jz      loc_18004867E
0x1800488be  jmp     loc_180048637
0x1800488c3  xor     edx, edx; PriorityBoost
0x1800488c5  mov     dword ptr [rbp+30h], 0C0000034h
0x1800488cc  mov     rcx, rbp; Irp
0x1800488cf  call    cs:__imp_IofCompleteRequest
0x1800488d6  nop     dword ptr [rax+rax+00h]
0x1800488db  mov     eax, 0C0000034h
0x1800488e0  jmp     loc_1800487C6
0x1800488e5  test    r13, r13
0x1800488e8  jnz     short loc_180048921
0x1800488ea  mov     rbx, r13
0x1800488ed  jmp     loc_180048692
0x1800488f2  lea     eax, [rdi+1]
0x1800488f5  cmp     ebp, eax
0x1800488f7  ja      loc_180048637
0x1800488fd  jmp     loc_18004868E
0x180048902  mov     ecx, 3
0x180048907  int     29h; Win8: RtlFailFast(ecx)
0x180048909  test    byte ptr [r13+2], 1
0x18004890e  jz      loc_180048794
0x180048914  jmp     loc_1800486EC
0x180048919  mov     r13, rbx
0x18004891c  jmp     loc_180048637
0x180048921  lock inc dword ptr [r13+20h]
0x180048926  jmp     short loc_1800488EA
0x180048928  mov     r8, r14
0x18004892b  xor     edx, edx
0x18004892d  xor     ecx, ecx; Str1
0x18004892f  call    FindAndReferenceCreateItem
0x180048934  mov     rbx, rax
0x180048937  jmp     loc_18004869A
0x18004893c  cmp     word ptr [r12+10h], 0
0x180048943  jz      loc_180048721
0x180048949  mov     rsi, [r13+8]
0x18004894d  xorps   xmm0, xmm0
0x180048950  mov     [rsp+0C8h+arg_10], 0
0x18004895b  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x180048960  mov     [rsp+0C8h+var_78], 0
0x180048969  mov     rcx, [rsi+8]
0x18004896d  add     rcx, 20h ; ' '; SubjectContext
0x180048971  mov     qword ptr [rsp+0C8h+var_70], rsi
0x180048976  call    cs:__imp_SeLockSubjectContext
0x18004897d  nop     dword ptr [rax+rax+00h]
0x180048982  mov     edi, [rsi+10h]
0x180048985  mov     rsi, [rsi+8]
0x180048989  mov     rbp, [r12+20h]
0x18004898e  call    cs:__imp_IoGetFileObjectGenericMapping
0x180048995  nop     dword ptr [rax+rax+00h]
0x18004899a  lea     rcx, [rsp+0C8h+arg_18]
0x1800489a2  mov     r9d, edi; DesiredAccess
0x1800489a5  mov     [rsp+0C8h+AccessStatus], rcx; AccessStatus
0x1800489aa  lea     rdx, [rsi+20h]; SubjectSecurityContext
0x1800489ae  lea     rcx, [rsp+0C8h+arg_10]
0x1800489b6  mov     r8b, 1; SubjectContextLocked
0x1800489b9  mov     [rsp+0C8h+GrantedAccess], rcx; GrantedAccess
0x1800489be  mov     rcx, rbp; SecurityDescriptor
0x1800489c1  mov     [rsp+0C8h+AccessMode], 1; AccessMode
0x1800489c6  mov     [rsp+0C8h+GenericMapping], rax; GenericMapping
0x1800489cb  lea     rax, [rsp+0C8h+var_78]
0x1800489d0  mov     [rsp+0C8h+Privileges], rax; Privileges
0x1800489d5  mov     [rsp+0C8h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1800489dd  call    cs:__imp_SeAccessCheck
0x1800489e4  nop     dword ptr [rax+rax+00h]
0x1800489e9  mov     rdx, [rsp+0C8h+var_78]; Privileges
0x1800489ee  movzx   esi, al
0x1800489f1  mov     rdi, qword ptr [rsp+0C8h+var_70]
0x1800489f6  test    rdx, rdx
0x1800489f9  jz      short loc_180048A1C
0x1800489fb  mov     rcx, [rdi+8]; AccessState
0x1800489ff  call    cs:__imp_SeAppendPrivileges
0x180048a06  nop     dword ptr [rax+rax+00h]
0x180048a0b  mov     rcx, [rsp+0C8h+var_78]; Privileges
0x180048a10  call    cs:__imp_SeFreePrivileges
0x180048a17  nop     dword ptr [rax+rax+00h]
0x180048a1c  test    sil, sil
0x180048a1f  jz      short loc_180048A43
0x180048a21  mov     rcx, [rdi+8]
0x180048a25  mov     eax, [rsp+0C8h+arg_10]
0x180048a2c  or      [rcx+14h], eax
0x180048a2f  mov     eax, [rsp+0C8h+arg_10]
0x180048a36  mov     rcx, [rdi+8]
0x180048a3a  bts     eax, 19h
0x180048a3e  not     eax
0x180048a40  and     [rcx+10h], eax
0x180048a43  lea     rdx, aFile; "File"
0x180048a4a  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x180048a4f  call    cs:__imp_RtlInitUnicodeString
0x180048a56  nop     dword ptr [rax+rax+00h]
0x180048a5b  mov     rcx, [rdi+8]
0x180048a5f  lea     rax, [r12+10h]
0x180048a64  cmp     word ptr [rax], 0
0x180048a68  lea     r8, [rsp+0C8h+DestinationString]
0x180048a6d  mov     r9, [r12+20h]; SecurityDescriptor
0x180048a72  mov     rdx, [r13+28h]; Object
0x180048a76  cmovnz  r8, rax; AbsoluteObjectName
0x180048a7a  lea     rax, [rcx+0Ah]
0x180048a7e  mov     [rsp+0C8h+GrantedAccess], rax; GenerateOnClose
0x180048a83  mov     [rsp+0C8h+AccessMode], 1; AccessMode
0x180048a88  mov     byte ptr [rsp+0C8h+GenericMapping], sil; AccessGranted
0x180048a8d  mov     byte ptr [rsp+0C8h+Privileges], 0; ObjectCreated
0x180048a92  mov     qword ptr [rsp+0C8h+PreviouslyGrantedAccess], rcx; AccessState
0x180048a97  lea     rcx, [rsp+0C8h+DestinationString]; ObjectTypeName
0x180048a9c  call    cs:__imp_SeOpenObjectAuditAlarm
0x180048aa3  nop     dword ptr [rax+rax+00h]
0x180048aa8  mov     rcx, [rdi+8]
0x180048aac  add     rcx, 20h ; ' '; SubjectContext
0x180048ab0  call    cs:__imp_SeUnlockSubjectContext
0x180048ab7  nop     dword ptr [rax+rax+00h]
0x180048abc  mov     rbp, [rsp+0C8h+Irp]
0x180048ac4  jmp     loc_180048769
0x180048ac9  xor     edx, edx; PriorityBoost
  ... truncated ...
```
