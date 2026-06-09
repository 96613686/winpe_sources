# RefsCacheSharedSecurityForCreate(_IRP_CONTEXT *,_FCB *)

- ea: `0x14032f1a0`
- end: `0x14032f608`
- name: `?RefsCacheSharedSecurityForCreate@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1128`
- prototype: `struct _SHARED_SECURITY *__fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140291760`

## callees

- `0x140081670`
- `0x14008dbd0`
- `0x1400ca788`
- `0x140285008`
- `0x1402873f8`
- `0x1402d09d0`
- `0x1402d0dd4`
- `0x14032f1a0`
- `0x14033783c`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x14032f227`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14032f352`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14032f352`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14032f4f0`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14032f532`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403417a3`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14032f4f0`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14032f532`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403417a3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14032f41d`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14032f41d`
- `ntoskrnl!ExGetPreviousMode` at `0x14032f250`
- `ntoskrnl!ExGetPreviousMode` at `0x14032f250`
- `ntoskrnl!SeDeassignSecurity` at `0x14032f5e5`
- `ntoskrnl!SeDeassignSecurity` at `0x140341872`
- `ntoskrnl!SeDeassignSecurity` at `0x14032f5e5`
- `ntoskrnl!SeDeassignSecurity` at `0x140341872`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x14032f231`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x14032f231`
- `ntoskrnl!SeAssignSecurityEx` at `0x14032f39d`
- `ntoskrnl!SeAssignSecurityEx` at `0x14032f39d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14032f4ff`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14032f545`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403417b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14032f4ff`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14032f545`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403417b6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14032f57a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403417ff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14032f57a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403417ff`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14032f586`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14034180b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14032f586`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14034180b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f55e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f5b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403417d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341840`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f55e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032f5b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403417d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341840`

## pseudocode

```c
struct _SHARED_SECURITY *__fastcall RefsCacheSharedSecurityForCreate(struct _IRP_CONTEXT *a1, struct _FCB *a2)
{
  struct _SHARED_SECURITY *v4; // r14
  struct _SHARED_SECURITY_FOR_CREATE *v5; // rsi
  char v6; // r12
  char *v7; // rbx
  __int64 v8; // r15
  ULONG v9; // r8d
  __int64 v10; // rcx
  char PreviousMode; // al
  char v12; // al
  int v13; // edx
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  ULONG v16; // r8d
  struct _LIST_ENTRY *Flink; // rax
  PVOID *FileContextSupportPointer; // rcx
  struct _SHARED_SECURITY_FOR_CREATE *Unsafe; // rax
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v22; // eax
  unsigned int v23; // r8d
  NTSTATUS v24; // ebx
  ULONG v25; // eax
  unsigned int v26; // r8d
  struct _FAST_MUTEX *v27; // rbx
  struct _FAST_MUTEX *v28; // rbx
  PSECURITY_DESCRIPTOR v30; // rdi
  __int64 v31; // rbx
  void *v32; // rcx
  int v33; // eax
  unsigned int v34; // eax
  char v36; // [rsp+52h] [rbp-66h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+58h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-58h] BYREF
  struct _SHARED_SECURITY_FOR_CREATE *v39; // [rsp+68h] [rbp-50h]
  __int64 v40; // [rsp+70h] [rbp-48h]
  BOOLEAN IsDirectoryObject; // [rsp+C8h] [rbp+10h]
  struct _SHARED_SECURITY *v42; // [rsp+D0h] [rbp+18h] BYREF
  ULONG AutoInheritFlags; // [rsp+D8h] [rbp+20h]

  NewDescriptor = 0;
  v4 = 0;
  v42 = 0;
  v5 = 0;
  v39 = 0;
  v6 = 0;
  SecurityDescriptor = 0;
  v36 = 1;
  v7 = *(char **)(*((_QWORD *)a1 + 9) + 184LL);
  IsDirectoryObject = v7[16] & 1;
  v8 = *(_QWORD *)(*((_QWORD *)v7 + 1) + 8LL);
  v40 = v8;
  if ( !a2->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(a1, a2);
  v9 = SeComputeAutoInheritByObjectType(
         IoFileObjectType,
         *(PSECURITY_DESCRIPTOR *)(v8 + 64),
         (char *)&a2->ScavengerFinalizationList.Flink[1].Flink + 4);
  AutoInheritFlags = v9;
  v10 = *((_QWORD *)a1 + 9);
  if ( !v10 )
  {
    PreviousMode = ExGetPreviousMode();
    v9 = AutoInheritFlags;
    goto LABEL_18;
  }
  v12 = *v7;
  if ( !*v7 )
  {
LABEL_6:
    if ( (v7[2] & 1) != 0 )
    {
      PreviousMode = 1;
      goto LABEL_18;
    }
LABEL_17:
    PreviousMode = *(_BYTE *)(v10 + 64);
    goto LABEL_18;
  }
  if ( v12 == 6 )
  {
    v13 = *((_DWORD *)v7 + 4);
    v14 = (unsigned int)(v13 - 10);
    if ( (unsigned int)v14 <= 0x3E )
    {
      v15 = 0x4080000000000003LL;
      if ( _bittest64(&v15, v14) )
      {
        PreviousMode = (v7[2] & 1) == 0;
        goto LABEL_18;
      }
    }
    if ( v13 != 71 )
      goto LABEL_17;
    goto LABEL_6;
  }
  if ( v12 != 5 )
    goto LABEL_17;
  if ( *((_DWORD *)v7 + 4) != 71 )
    goto LABEL_17;
  PreviousMode = 1;
  if ( (v7[2] & 1) == 0 )
    goto LABEL_17;
LABEL_18:
  v16 = (PreviousMode != 0 ? 24576 : 16408) | v9;
  AutoInheritFlags = v16;
  if ( !*(_QWORD *)(v8 + 64) )
  {
    Flink = a2->ScavengerFinalizationList.Flink;
    if ( HIDWORD(Flink->Blink) )
    {
      FileContextSupportPointer = a2->Header.FileContextSupportPointer;
      if ( FileContextSupportPointer[22] )
      {
        Unsafe = GetSharedSecurityForCreateUnsafe(
                   (struct _VCB *)FileContextSupportPointer,
                   (struct _SECURITY_HASH_KEY *)&Flink->Blink,
                   v16,
                   (struct _SECURITY_SUBJECT_CONTEXT *)(v8 + 32),
                   IsDirectoryObject);
        v5 = Unsafe;
        v39 = Unsafe;
        if ( Unsafe )
        {
          if ( *((_DWORD *)Unsafe + 3) )
          {
            v4 = (struct _SHARED_SECURITY *)RefsCacheSharedSecurityBySecurityId(
                                              a1,
                                              a2->Header.FileContextSupportPointer,
                                              *((_QWORD *)Unsafe + 1),
                                              &v42);
            v42 = v4;
          }
        }
      }
    }
  }
  if ( !v4 )
  {
    PoolType = ::PoolType;
    GenericMapping = IoGetFileObjectGenericMapping();
    v22 = SeAssignSecurityEx(
            (char *)&a2->ScavengerFinalizationList.Flink[1].Flink + 4,
            *(PSECURITY_DESCRIPTOR *)(v8 + 64),
            &NewDescriptor,
            0,
            IsDirectoryObject,
            AutoInheritFlags,
            (PSECURITY_SUBJECT_CONTEXT)(v8 + 32),
            GenericMapping,
            PoolType);
    v24 = v22;
    if ( v22 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
          (unsigned int)v22);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v24, a1, "SecurSup.c", 0x1257u);
      RefsRaiseStatusInternal(a1, v24, v23);
    }
    v25 = RtlLengthSecurityDescriptor(NewDescriptor);
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids, 3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811, a1, "SecurSup.c", 0x127Eu);
      RefsRaiseStatusInternal(a1, -1073741811, v26);
    }
    v4 = RefsCacheSharedSecurityByDescriptor(a1, NewDescriptor, v25, 1u);
  }
  if ( v4 )
  {
    SecurityDescriptor = NewDescriptor;
    NewDescriptor = (char *)v4 + 20;
    v36 = 0;
  }
  if ( v5 && !v42 )
  {
    v27 = (struct _FAST_MUTEX *)(*((_QWORD *)a1 + 8) + 728LL);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v27);
    v6 = 1;
    AddCachedSharedSecurityForCreateUnsafe(
      (struct _VCB *)a2->Header.FileContextSupportPointer,
      (struct _SHARED_SECURITY *)((char *)v4 + 8),
      v5);
  }
  if ( v5 )
  {
    if ( !v6 )
    {
      v28 = (struct _FAST_MUTEX *)*((_QWORD *)a1 + 8);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(v28 + 13);
      v6 = 1;
    }
    if ( (*(_DWORD *)v5)-- == 1 )
      ExFreePoolWithTag(v5, 0);
  }
  if ( v6 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)a1 + 8) + 728LL));
    KeLeaveGuardedRegion();
  }
  v30 = NewDescriptor;
  v31 = *(_QWORD *)(v8 + 72);
  if ( (*(_DWORD *)(v8 + 12) & 0x4000000) == 0 )
  {
    v32 = *(void **)(v31 + 48);
    if ( v32 )
      ExFreePoolWithTag(v32, 0);
  }
  v33 = *(_DWORD *)(v8 + 12);
  if ( v36 )
    v34 = v33 & 0xFBFFFFFF;
  else
    v34 = v33 | 0x4000000;
  *(_DWORD *)(v8 + 12) = v34;
  *(_QWORD *)(v31 + 48) = v30;
  if ( SecurityDescriptor )
    SeDeassignSecurity(&SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x14032f1a0  mov     rax, rsp
0x14032f1a3  mov     [rax+8], rcx
0x14032f1a7  push    rbx
0x14032f1a8  push    rsi
0x14032f1a9  push    rdi
0x14032f1aa  push    r12
0x14032f1ac  push    r13
0x14032f1ae  push    r14
0x14032f1b0  push    r15
0x14032f1b2  sub     rsp, 80h
0x14032f1b9  mov     r13, rdx
0x14032f1bc  mov     rdi, rcx
0x14032f1bf  xor     ecx, ecx
0x14032f1c1  mov     [rax-60h], rcx
0x14032f1c5  mov     r14d, ecx
0x14032f1c8  mov     [rax+18h], rcx
0x14032f1cc  mov     esi, ecx
0x14032f1ce  mov     [rax-50h], rcx
0x14032f1d2  mov     [rax-67h], cl
0x14032f1d5  mov     r12b, cl
0x14032f1d8  mov     [rax-68h], cl
0x14032f1db  mov     [rax-58h], rcx
0x14032f1df  mov     byte ptr [rax-66h], 1
0x14032f1e3  mov     rax, [rdi+48h]
0x14032f1e7  mov     rbx, [rax+0B8h]
0x14032f1ee  mov     al, [rbx+10h]
0x14032f1f1  and     al, 1
0x14032f1f3  mov     [rsp+0B8h+arg_8], al
0x14032f1fa  mov     rax, [rbx+8]
0x14032f1fe  mov     r15, [rax+8]
0x14032f202  mov     [rsp+0B8h+var_48], r15
0x14032f207  cmp     [rdx+0C0h], rcx
0x14032f20e  jnz     short loc_14032F218
0x14032f210  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14032f213  call    ?RefsLoadSecurityDescriptor@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsLoadSecurityDescriptor(_IRP_CONTEXT *,_FCB *)
0x14032f218  mov     r8, [r13+0C0h]
0x14032f21f  add     r8, 14h; ParentSecurityDescriptor
0x14032f223  mov     rdx, [r15+40h]; SecurityDescriptor
0x14032f227  mov     rcx, cs:__imp_IoFileObjectType
0x14032f22e  mov     rcx, [rcx]; ObjectType
0x14032f231  call    cs:__imp_SeComputeAutoInheritByObjectType
0x14032f238  nop     dword ptr [rax+rax+00h]
0x14032f23d  mov     r8d, eax
0x14032f240  mov     [rsp+0B8h+arg_18], eax
0x14032f247  mov     rcx, [rdi+48h]
0x14032f24b  test    rcx, rcx
0x14032f24e  jnz     short loc_14032F266
0x14032f250  call    cs:__imp_ExGetPreviousMode
0x14032f257  nop     dword ptr [rax+rax+00h]
0x14032f25c  mov     r8d, [rsp+0B8h+arg_18]
0x14032f264  jmp     short loc_14032F2BA
0x14032f266  mov     al, [rbx]
0x14032f268  test    al, al
0x14032f26a  jnz     short loc_14032F276
0x14032f26c  test    byte ptr [rbx+2], 1
0x14032f270  jz      short loc_14032F2B7
0x14032f272  mov     al, 1
0x14032f274  jmp     short loc_14032F2BA
0x14032f276  cmp     al, 6
0x14032f278  jnz     short loc_14032F2A5
0x14032f27a  mov     edx, [rbx+10h]
0x14032f27d  lea     eax, [rdx-0Ah]
0x14032f280  cmp     eax, 3Eh ; '>'
0x14032f283  ja      short loc_14032F29E
0x14032f285  mov     r9, 4080000000000003h
0x14032f28f  bt      r9, rax
0x14032f293  jnb     short loc_14032F29E
0x14032f295  mov     al, [rbx+2]
0x14032f298  not     al
0x14032f29a  and     al, 1
0x14032f29c  jmp     short loc_14032F2BA
0x14032f29e  cmp     edx, 47h ; 'G'
0x14032f2a1  jnz     short loc_14032F2B7
0x14032f2a3  jmp     short loc_14032F26C
0x14032f2a5  cmp     al, 5
0x14032f2a7  jnz     short loc_14032F2B7
0x14032f2a9  cmp     dword ptr [rbx+10h], 47h ; 'G'
0x14032f2ad  jnz     short loc_14032F2B7
0x14032f2af  test    byte ptr [rbx+2], 1
0x14032f2b3  mov     al, 1
0x14032f2b5  jnz     short loc_14032F2BA
0x14032f2b7  mov     al, [rcx+40h]
0x14032f2ba  neg     al
0x14032f2bc  sbb     eax, eax
0x14032f2be  and     eax, 1FE8h
0x14032f2c3  add     eax, 4018h
0x14032f2c8  or      r8d, eax; unsigned int
0x14032f2cb  mov     [rsp+0B8h+arg_18], r8d
0x14032f2d3  cmp     qword ptr [r15+40h], 0
0x14032f2d8  jnz     short loc_14032F343
0x14032f2da  mov     rax, [r13+0C0h]
0x14032f2e1  lea     rdx, [rax+8]; struct _SECURITY_HASH_KEY *
0x14032f2e5  cmp     dword ptr [rdx+4], 0
0x14032f2e9  jz      short loc_14032F343
0x14032f2eb  mov     rcx, [r13+50h]; struct _VCB *
0x14032f2ef  cmp     qword ptr [rcx+0B0h], 0
0x14032f2f7  jz      short loc_14032F343
0x14032f2f9  lea     r9, [r15+20h]; struct _SECURITY_SUBJECT_CONTEXT *
0x14032f2fd  mov     al, [rsp+0B8h+arg_8]
0x14032f304  mov     [rsp+0B8h+IsDirectoryObject], al; unsigned __int8
0x14032f308  call    ?GetSharedSecurityForCreateUnsafe@@YAPEAU_SHARED_SECURITY_FOR_CREATE@@PEAU_VCB@@PEAU_SECURITY_HASH_KEY@@KPEAU_SECURITY_SUBJECT_CONTEXT@@E@Z; GetSharedSecurityForCreateUnsafe(_VCB *,_SECURITY_HASH_KEY *,ulong,_SECURITY_SUBJECT_CONTEXT *,uchar)
0x14032f30d  mov     rsi, rax
0x14032f310  mov     [rsp+0B8h+var_50], rax
0x14032f315  test    rax, rax
0x14032f318  jz      short loc_14032F343
0x14032f31a  cmp     dword ptr [rax+0Ch], 0
0x14032f31e  jz      short loc_14032F343
0x14032f320  lea     r9, [rsp+0B8h+arg_10]
0x14032f328  mov     r8, [rax+8]
0x14032f32c  mov     rdx, [r13+50h]
0x14032f330  mov     rcx, rdi
0x14032f333  call    ?RefsCacheSharedSecurityBySecurityId@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_VCB@@U_SECURITY_HASH_KEY@@PEAE@Z; RefsCacheSharedSecurityBySecurityId(_IRP_CONTEXT *,_VCB *,_SECURITY_HASH_KEY,uchar *)
0x14032f338  mov     r14, rax
0x14032f33b  mov     [rsp+0B8h+arg_10], rax
0x14032f343  test    r14, r14
0x14032f346  jnz     loc_14032F4B3
0x14032f34c  mov     ebx, cs:PoolType
0x14032f352  call    cs:__imp_IoGetFileObjectGenericMapping
0x14032f359  nop     dword ptr [rax+rax+00h]
0x14032f35e  lea     rdx, [r15+20h]
0x14032f362  mov     rcx, [r13+0C0h]
0x14032f369  add     rcx, 14h; ParentDescriptor
0x14032f36d  mov     [rsp+0B8h+PoolType], ebx; PoolType
0x14032f371  mov     [rsp+0B8h+GenericMapping], rax; GenericMapping
0x14032f376  mov     [rsp+0B8h+SubjectContext], rdx; SubjectContext
0x14032f37b  mov     eax, [rsp+0B8h+arg_18]
0x14032f382  mov     [rsp+0B8h+AutoInheritFlags], eax; AutoInheritFlags
0x14032f386  mov     al, [rsp+0B8h+arg_8]
0x14032f38d  mov     [rsp+0B8h+IsDirectoryObject], al; IsDirectoryObject
0x14032f391  xor     r9d, r9d; ObjectType
0x14032f394  lea     r8, [rsp+0B8h+NewDescriptor]; NewDescriptor
0x14032f399  mov     rdx, [r15+40h]; ExplicitDescriptor
0x14032f39d  call    cs:__imp_SeAssignSecurityEx
0x14032f3a4  nop     dword ptr [rax+rax+00h]
0x14032f3a9  mov     ebx, eax
0x14032f3ab  test    eax, eax
0x14032f3ad  jns     short loc_14032F413
0x14032f3af  lea     rdx, WPP_GLOBAL_Control
0x14032f3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14032f3bd  cmp     rcx, rdx
0x14032f3c0  jz      short loc_14032F3E8
0x14032f3c2  test    dword ptr [rcx+2Ch], 100h
0x14032f3c9  jz      short loc_14032F3E8
0x14032f3cb  cmp     byte ptr [rcx+29h], 4
0x14032f3cf  jb      short loc_14032F3E8
0x14032f3d1  lea     edx, [r14+27h]
0x14032f3d5  mov     r9d, eax
0x14032f3d8  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x14032f3df  mov     rcx, [rcx+18h]
0x14032f3e3  call    WPP_SF_d
0x14032f3e8  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14032f3ee  test    al, al
0x14032f3f0  jz      short loc_14032F409
0x14032f3f2  mov     r9d, 1257h; unsigned int
0x14032f3f8  lea     r8, aSecursupC; "SecurSup.c"
0x14032f3ff  mov     rdx, rdi; struct _IRP_CONTEXT *
0x14032f402  mov     ecx, ebx; Status
0x14032f404  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14032f409  mov     edx, ebx; int
0x14032f40b  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14032f40e  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14032f413  mov     [rsp+0B8h+var_67], 1
0x14032f418  mov     rcx, [rsp+0B8h+NewDescriptor]; SecurityDescriptor
0x14032f41d  call    cs:__imp_RtlLengthSecurityDescriptor
0x14032f424  nop     dword ptr [rax+rax+00h]
0x14032f429  test    eax, eax
0x14032f42b  jnz     short loc_14032F49B
0x14032f42d  lea     rdx, WPP_GLOBAL_Control
0x14032f434  mov     rcx, cs:WPP_GLOBAL_Control
0x14032f43b  cmp     rcx, rdx
0x14032f43e  jz      short loc_14032F46A
0x14032f440  mov     eax, [rcx+2Ch]
0x14032f443  bt      eax, 8
0x14032f447  jnb     short loc_14032F46A
0x14032f449  cmp     byte ptr [rcx+29h], 4
0x14032f44d  jb      short loc_14032F46A
0x14032f44f  mov     edx, 28h ; '('
0x14032f454  mov     r9d, 0C000000Dh
0x14032f45a  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x14032f461  mov     rcx, [rcx+18h]
0x14032f465  call    WPP_SF_d
0x14032f46a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14032f470  test    al, al
0x14032f472  jz      short loc_14032F48E
0x14032f474  mov     r9d, 127Eh; unsigned int
0x14032f47a  lea     r8, aSecursupC; "SecurSup.c"
0x14032f481  mov     rdx, rdi; struct _IRP_CONTEXT *
0x14032f484  mov     ecx, 0C000000Dh; Status
0x14032f489  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14032f48e  mov     edx, 0C000000Dh; int
0x14032f493  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14032f496  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14032f49b  mov     r9b, 1; unsigned __int8
0x14032f49e  mov     r8d, eax; Size
0x14032f4a1  mov     rdx, [rsp+0B8h+NewDescriptor]; SecurityDescriptor
0x14032f4a6  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14032f4a9  call    ?RefsCacheSharedSecurityByDescriptor@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAXKE@Z; RefsCacheSharedSecurityByDescriptor(_IRP_CONTEXT *,void *,ulong,uchar)
0x14032f4ae  mov     r14, rax
0x14032f4b1  jmp     short loc_14032F4B8
0x14032f4b3  mov     [rsp+0B8h+var_67], 1
0x14032f4b8  test    r14, r14
0x14032f4bb  jz      short loc_14032F4D5
0x14032f4bd  mov     rax, [rsp+0B8h+NewDescriptor]
0x14032f4c2  mov     [rsp+0B8h+SecurityDescriptor], rax
0x14032f4c7  lea     rax, [r14+14h]
0x14032f4cb  mov     [rsp+0B8h+NewDescriptor], rax
0x14032f4d0  mov     [rsp+0B8h+var_66], 0
0x14032f4d5  test    rsi, rsi
0x14032f4d8  jz      short loc_14032F524
0x14032f4da  cmp     [rsp+0B8h+arg_10], 0
0x14032f4e3  jnz     short loc_14032F524
0x14032f4e5  mov     rax, [rdi+40h]
0x14032f4e9  lea     rbx, [rax+2D8h]
0x14032f4f0  call    cs:__imp_KeEnterGuardedRegion
0x14032f4f7  nop     dword ptr [rax+rax+00h]
0x14032f4fc  mov     rcx, rbx; FastMutex
0x14032f4ff  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14032f506  nop     dword ptr [rax+rax+00h]
0x14032f50b  mov     r12b, 1
0x14032f50e  mov     [rsp+0B8h+var_68], r12b
0x14032f513  lea     rdx, [r14+8]; struct _SECURITY_HASH_KEY *
0x14032f517  mov     r8, rsi; struct _SHARED_SECURITY_FOR_CREATE *
0x14032f51a  mov     rcx, [r13+50h]; struct _VCB *
0x14032f51e  call    ?AddCachedSharedSecurityForCreateUnsafe@@YAXPEAU_VCB@@PEAU_SECURITY_HASH_KEY@@PEAU_SHARED_SECURITY_FOR_CREATE@@@Z; AddCachedSharedSecurityForCreateUnsafe(_VCB *,_SECURITY_HASH_KEY *,_SHARED_SECURITY_FOR_CREATE *)
0x14032f523  nop
0x14032f524  test    rsi, rsi
0x14032f527  jz      short loc_14032F56A
0x14032f529  test    r12b, r12b
0x14032f52c  jnz     short loc_14032F554
0x14032f52e  mov     rbx, [rdi+40h]
0x14032f532  call    cs:__imp_KeEnterGuardedRegion
0x14032f539  nop     dword ptr [rax+rax+00h]
0x14032f53e  lea     rcx, [rbx+2D8h]; FastMutex
0x14032f545  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14032f54c  nop     dword ptr [rax+rax+00h]
0x14032f551  mov     r12b, 1
0x14032f554  add     dword ptr [rsi], 0FFFFFFFFh
0x14032f557  jnz     short loc_14032F56A
0x14032f559  xor     edx, edx; Tag
0x14032f55b  mov     rcx, rsi; P
0x14032f55e  call    cs:__imp_ExFreePoolWithTag
0x14032f565  nop     dword ptr [rax+rax+00h]
0x14032f56a  test    r12b, r12b
0x14032f56d  jz      short loc_14032F592
0x14032f56f  mov     rcx, [rdi+40h]
0x14032f573  add     rcx, 2D8h; FastMutex
0x14032f57a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14032f581  nop     dword ptr [rax+rax+00h]
0x14032f586  call    cs:__imp_KeLeaveGuardedRegion
0x14032f58d  nop     dword ptr [rax+rax+00h]
0x14032f592  mov     rdi, [rsp+0B8h+NewDescriptor]
0x14032f597  mov     rbx, [r15+48h]
0x14032f59b  mov     esi, 4000000h
0x14032f5a0  test    [r15+0Ch], esi
0x14032f5a4  jnz     short loc_14032F5BD
0x14032f5a6  mov     rcx, [rbx+30h]; P
0x14032f5aa  test    rcx, rcx
0x14032f5ad  jz      short loc_14032F5BD
0x14032f5af  xor     edx, edx; Tag
0x14032f5b1  call    cs:__imp_ExFreePoolWithTag
0x14032f5b8  nop     dword ptr [rax+rax+00h]
0x14032f5bd  mov     eax, [r15+0Ch]
0x14032f5c1  cmp     [rsp+0B8h+var_66], 0
0x14032f5c6  jz      short loc_14032F5CE
0x14032f5c8  btr     eax, 1Ah
0x14032f5cc  jmp     short loc_14032F5D0
0x14032f5ce  or      eax, esi
0x14032f5d0  mov     [r15+0Ch], eax
0x14032f5d4  mov     [rbx+30h], rdi
0x14032f5d8  cmp     [rsp+0B8h+SecurityDescriptor], 0
0x14032f5de  jz      short loc_14032F5F1
0x14032f5e0  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x14032f5e5  call    cs:__imp_SeDeassignSecurity
0x14032f5ec  nop     dword ptr [rax+rax+00h]
0x14032f5f1  mov     rax, r14
0x14032f5f4  add     rsp, 80h
0x14032f5fb  pop     r15
0x14032f5fd  pop     r14
0x14032f5ff  pop     r13
0x14032f601  pop     r12
0x14032f603  pop     rdi
0x14032f604  pop     rsi
0x14032f605  pop     rbx
0x14032f606  retn
0x14034177d  push    rbx
0x14034177f  push    rbp
0x140341780  push    rsi
0x140341781  push    rdi
0x140341782  sub     rsp, 58h
0x140341786  mov     rbp, rdx
0x140341789  mov     rdi, [rbp+68h]
0x14034178d  test    rdi, rdi
0x140341790  jz      short loc_1403417E7
0x140341792  cmp     byte ptr [rbp+50h], 0
0x140341796  jnz     short loc_1403417C6
0x140341798  mov     rax, [rbp+0C0h]
0x14034179f  mov     rbx, [rax+40h]
0x1403417a3  call    cs:__imp_KeEnterGuardedRegion
0x1403417aa  nop     dword ptr [rax+rax+00h]
0x1403417af  lea     rcx, [rbx+2D8h]; FastMutex
  ... truncated ...
```
