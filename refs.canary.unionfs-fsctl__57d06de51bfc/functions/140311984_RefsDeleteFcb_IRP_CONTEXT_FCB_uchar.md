# RefsDeleteFcb(_IRP_CONTEXT *,_FCB *,uchar *)

- ea: `0x140311984`
- end: `0x140311cfa`
- name: `?RefsDeleteFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAE@Z`
- size: `886`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14003ec10`
- `0x1403040a0`
- `0x140304730`
- `0x140310460`
- `0x14033d970`

## callees

- `0x14000a370`
- `0x14007bdb0`
- `0x14008a460`
- `0x14008ed40`
- `0x140097680`
- `0x1400a3500`
- `0x1400a6a10`
- `0x1400fe568`
- `0x1401100c4`
- `0x1402e3bb4`
- `0x1402ff170`
- `0x140311984`
- `0x140311d00`
- `0x140311d70`
- `0x1403240d0`

## import_xrefs

- `ntoskrnl!ExIsFastResourceHeld` at `0x140311a3a`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140311a3a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140311bbc`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140311bbc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140311cd4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140311cd4`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140311b3c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140311b3c`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140311c95`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140311c95`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140311bcf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140311bcf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140311c0c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140311c0c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140311c18`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140311c18`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140311a1f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140311a1f`
- `ntoskrnl!ExReleaseFastResource` at `0x140311b74`
- `ntoskrnl!ExReleaseFastResource` at `0x140311b74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311cae`

## pseudocode

```c
void __fastcall RefsDeleteFcb(struct _IRP_CONTEXT *a1, struct _FCB *a2, unsigned __int8 *a3)
{
  char v5; // r15
  struct _IRP_CONTEXT *v6; // rbx
  struct _FCB **v7; // r14
  int v8; // ebp
  struct _FCB *v9; // rcx
  struct _IRP_CONTEXT *v10; // rax
  __int64 v11; // rax
  PVOID Context; // rcx
  struct _MS_FAST_RESOURCE_OWNER_ENTRY *IrpContextPagingIoOwnerEntryRelease; // rax
  __int64 v14; // r8
  PVOID v15; // rcx
  PVOID *FileContextSupportPointer; // rbx
  PVOID *v17; // rbx
  struct _LIST_ENTRY *Flink; // rcx
  struct _ROLLBACK_STRUCT *v19; // rax
  struct _IRP_CONTEXT *v20; // rcx
  struct _IRP_CONTEXT *v21; // rcx
  struct _ROLLBACK_STRUCT *v22; // rax
  struct _IRP_CONTEXT *v23; // rcx
  struct _LIST_ENTRY *v24; // rax
  PERESOURCE Resource; // rax
  struct _LOOKASIDE_LIST_EX *v26; // rcx

  if ( !_bittest64((const signed __int64 *)a1 + 1, 0x25u) || (v5 = 1, ((__int64)a2->spacer.Resource & 0x2000000) == 0) )
    v5 = 0;
  if ( ((_DWORD)a2->Header.FileContextSupportPointer[3] & 0x2000) != 0 && (*((_DWORD *)a1 + 1) & 0x40000000) == 0 )
    __int2c();
  RefsFreeSnapshotsForFcb(a1, a2);
  if ( !v5 && a2->Header.FilterContexts.Blink )
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveFromAnyList(a2);
  v6 = a1;
  do
  {
    v7 = (struct _FCB **)*((_QWORD *)v6 + 6);
    if ( v7 )
    {
      v8 = *((unsigned __int16 *)v6 + 21);
      if ( v8 == 1 )
        v7 = (struct _FCB **)((char *)v6 + 48);
      do
      {
        v9 = *v7;
        if ( *v7 && v9 == a2 )
        {
          if ( (unsigned __int8)ExIsFastResourceHeldExclusive(&v9->pNetRoot->InnerNamePrefix)
            && (unsigned __int8)ExIsFastResourceHeld(&(*v7)->pNetRoot->InnerNamePrefix) == 1 )
          {
            RefsFreeSnapshotsForFcb(v6, *v7);
          }
          RefsReleaseResource(v6, *v7);
          *v7 = 0;
          if ( *((_WORD *)v6 + 21) == 1 )
            *((_WORD *)v6 + 21) = 0;
        }
        ++v7;
        --v8;
      }
      while ( v8 );
    }
    v10 = (struct _IRP_CONTEXT *)*((_QWORD *)v6 + 13);
    if ( v6 == v10 )
      break;
    v6 = (struct _IRP_CONTEXT *)*((_QWORD *)v6 + 13);
  }
  while ( v10 );
  if ( !v5 )
  {
    if ( *((struct _FCB **)a1 + 7) == a2 )
    {
      *((_QWORD *)a1 + 7) = 0;
    }
    else
    {
      v11 = *((_QWORD *)a1 + 13);
      if ( *(struct _FCB **)(v11 + 56) == a2 )
        *(_QWORD *)(v11 + 56) = 0;
    }
    Context = a2->Context;
    if ( Context )
    {
      while ( (unsigned __int8)MsIsFastResourceHeld(Context) )
      {
        IrpContextPagingIoOwnerEntryRelease = RefsGetIrpContextPagingIoOwnerEntryRelease(
                                                a1,
                                                (struct _MS_FAST_RESOURCE *)a2->Context);
        if ( IrpContextPagingIoOwnerEntryRelease && *((_DWORD *)IrpContextPagingIoOwnerEntryRelease + 18) )
          MsReleaseFastResource(v14);
        else
          MsReleaseFastResourceLegacy(v14);
        Context = a2->Context;
      }
    }
    if ( a2->pNetRoot->NodeTypeCode == 2117 )
    {
      v15 = a2->Context;
      if ( v15 )
      {
        RefsFreeEresource(v15);
        a2->Context = 0;
      }
    }
    if ( ((__int64)a2->spacer.Resource & 0x40) != 0 )
    {
      FileContextSupportPointer = a2->Header.FileContextSupportPointer;
      RtlAvlRemoveNode(FileContextSupportPointer + 104, &a2->pNetRoot[2].Flags);
      --*((_DWORD *)FileContextSupportPointer + 210);
      a2->Header.Resource = (PERESOURCE)((unsigned __int64)a2->Header.Resource & ~0x40uLL);
    }
  }
  if ( *(_QWORD *)&a2->FcbTableEntry.Path.Length )
    RefsFreeFcbUsnRecord(a1, a2);
  ExReleaseFastResource(a2->Header.FileContextSupportPointer + 78, 0);
  *a3 = 0;
  RefsReleaseAllDataStreamSets(a2);
  if ( !v5 )
  {
    RefsDeleteNonpagedFcb((char *)a2->pNetRoot);
    a2->pNetRoot = 0;
  }
  if ( *(_QWORD *)&a2->FcbTableEntry.Lookups )
    RefsCloseFcbTable(a2);
  if ( a2->ScavengerFinalizationList.Flink )
  {
    v17 = a2->Header.FileContextSupportPointer;
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)v17 + 13);
    --LODWORD(a2->ScavengerFinalizationList.Flink->Flink);
    Flink = a2->ScavengerFinalizationList.Flink;
    if ( !LODWORD(Flink->Flink) )
      ExFreePoolWithTag(Flink, 0);
    a2->ScavengerFinalizationList.Flink = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)v17 + 13);
    KeLeaveGuardedRegion();
  }
  v19 = RefsAddStructToRollbackList(a1, 0x823u, a2, 0);
  if ( v19 )
    RefsProcessRollbackStruct(v20, v19, 0x10u);
  v21 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 13);
  if ( a1 != v21 )
  {
    v22 = RefsAddStructToRollbackList(v21, 0x823u, a2, 0);
    if ( v22 )
      RefsProcessRollbackStruct(v23, v22, 0x10u);
  }
  if ( v5 )
  {
    a2->Header.Resource = (PERESOURCE)((unsigned __int64)a2->Header.Resource | 0x4000000);
  }
  else
  {
    v24 = a2->FcbTableEntry.HashLinks.Flink;
    if ( v24 )
      LOBYTE(v24->Flink) = 1;
    if ( ((__int64)a2->spacer.Resource & 4) == 0 )
      FsRtlTeardownPerFileContexts((PVOID *)&a2->FcbTableEntry.HashLinks.Blink);
    Resource = a2->Header.Resource;
    if ( ((unsigned __int8)Resource & 2) != 0 )
    {
      ExFreePoolWithTag(a2, 0);
    }
    else
    {
      v26 = &RefsFcbIndexLookasideList;
      if ( ((unsigned __int16)Resource & 0x400) == 0 )
        v26 = &RefsFcbDataLookasideList;
      ExFreeToLookasideListEx(v26, a2);
    }
  }
}

```

## disassembly

```asm
0x140311984  mov     [rsp+arg_10], r8
0x140311989  push    rbx
0x14031198a  push    rbp
0x14031198b  push    rsi
0x14031198c  push    rdi
0x14031198d  push    r12
0x14031198f  push    r13
0x140311991  push    r14
0x140311993  push    r15
0x140311995  sub     rsp, 28h
0x140311999  xor     r13d, r13d
0x14031199c  mov     rdi, rdx
0x14031199f  bt      qword ptr [rcx+8], 25h ; '%'
0x1403119a5  mov     rsi, rcx
0x1403119a8  jnb     short loc_1403119B7
0x1403119aa  mov     eax, [rdx+8]
0x1403119ad  mov     r15b, 1
0x1403119b0  bt      rax, 19h
0x1403119b5  jb      short loc_1403119BA
0x1403119b7  mov     r15b, r13b
0x1403119ba  mov     rax, [rdx+50h]
0x1403119be  test    dword ptr [rax+18h], 2000h
0x1403119c5  jz      short loc_1403119D2
0x1403119c7  test    dword ptr [rcx+4], 40000000h
0x1403119ce  jnz     short loc_1403119D2
0x1403119d0  int     2Ch; Windows NT - assertion failure
0x1403119d2  call    ?RefsFreeSnapshotsForFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsFreeSnapshotsForFcb(_IRP_CONTEXT *,_FCB *)
0x1403119d7  test    r15b, r15b
0x1403119da  jnz     short loc_1403119EA
0x1403119dc  cmp     [rdi+40h], r13
0x1403119e0  jz      short loc_1403119EA
0x1403119e2  mov     rcx, rdi
0x1403119e5  call    ?RemoveFromAnyList@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAXAEAU_FCB@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveFromAnyList(_FCB &)
0x1403119ea  mov     rbx, rsi
0x1403119ed  mov     r12d, 1
0x1403119f3  lea     rax, [rbx+30h]
0x1403119f7  mov     r14, [rax]
0x1403119fa  test    r14, r14
0x1403119fd  jz      short loc_140311A79
0x1403119ff  movzx   ebp, word ptr [rbx+2Ah]
0x140311a03  cmp     ebp, r12d
0x140311a06  cmovz   r14, rax
0x140311a0a  mov     rcx, [r14]
0x140311a0d  test    rcx, rcx
0x140311a10  jz      short loc_140311A70
0x140311a12  cmp     rcx, rdi
0x140311a15  jnz     short loc_140311A70
0x140311a17  mov     rcx, [rcx+58h]
0x140311a1b  add     rcx, 40h ; '@'
0x140311a1f  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140311a26  nop     dword ptr [rax+rax+00h]
0x140311a2b  test    al, al
0x140311a2d  jz      short loc_140311A56
0x140311a2f  mov     rax, [r14]
0x140311a32  mov     rcx, [rax+58h]
0x140311a36  add     rcx, 40h ; '@'
0x140311a3a  call    cs:__imp_ExIsFastResourceHeld
0x140311a41  nop     dword ptr [rax+rax+00h]
0x140311a46  cmp     al, r12b
0x140311a49  jnz     short loc_140311A56
0x140311a4b  mov     rdx, [r14]; struct _FCB *
0x140311a4e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140311a51  call    ?RefsFreeSnapshotsForFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsFreeSnapshotsForFcb(_IRP_CONTEXT *,_FCB *)
0x140311a56  mov     rdx, [r14]
0x140311a59  mov     rcx, rbx
0x140311a5c  call    ?RefsReleaseResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleaseResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140311a61  mov     [r14], r13
0x140311a64  cmp     [rbx+2Ah], r12w
0x140311a69  jnz     short loc_140311A70
0x140311a6b  mov     [rbx+2Ah], r13w
0x140311a70  add     r14, 8
0x140311a74  add     ebp, 0FFFFFFFFh
0x140311a77  jnz     short loc_140311A0A
0x140311a79  mov     rax, [rbx+68h]
0x140311a7d  cmp     rbx, rax
0x140311a80  jz      short loc_140311A8E
0x140311a82  mov     rbx, rax
0x140311a85  test    rax, rax
0x140311a88  jnz     loc_1403119F3
0x140311a8e  mov     r12, [rsp+68h+arg_10]
0x140311a96  test    r15b, r15b
0x140311a99  jnz     loc_140311B53
0x140311a9f  cmp     [rsi+38h], rdi
0x140311aa3  jnz     short loc_140311AAB
0x140311aa5  mov     [rsi+38h], r13
0x140311aa9  jmp     short loc_140311AB9
0x140311aab  mov     rax, [rsi+68h]
0x140311aaf  cmp     [rax+38h], rdi
0x140311ab3  jnz     short loc_140311AB9
0x140311ab5  mov     [rax+38h], r13
0x140311ab9  mov     rcx, [rdi+60h]
0x140311abd  test    rcx, rcx
0x140311ac0  jnz     short loc_140311AF7
0x140311ac2  jmp     short loc_140311B00
0x140311ac4  mov     r8, [rdi+60h]
0x140311ac8  mov     rcx, rsi; struct _IRP_CONTEXT *
0x140311acb  mov     rdx, r8; struct _MS_FAST_RESOURCE *
0x140311ace  call    ?RefsGetIrpContextPagingIoOwnerEntryRelease@@YAPEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@PEAU_IRP_CONTEXT@@PEAU_MS_FAST_RESOURCE@@@Z; RefsGetIrpContextPagingIoOwnerEntryRelease(_IRP_CONTEXT *,_MS_FAST_RESOURCE *)
0x140311ad3  test    rax, rax
0x140311ad6  jz      short loc_140311AEB
0x140311ad8  cmp     [rax+48h], r13d
0x140311adc  jz      short loc_140311AEB
0x140311ade  mov     rdx, rax
0x140311ae1  mov     rcx, r8
0x140311ae4  call    MsReleaseFastResource
0x140311ae9  jmp     short loc_140311AF3
0x140311aeb  mov     rcx, r8
0x140311aee  call    MsReleaseFastResourceLegacy
0x140311af3  mov     rcx, [rdi+60h]
0x140311af7  call    MsIsFastResourceHeld
0x140311afc  test    al, al
0x140311afe  jnz     short loc_140311AC4
0x140311b00  mov     rax, [rdi+58h]
0x140311b04  mov     ecx, 845h
0x140311b09  cmp     [rax], cx
0x140311b0c  jnz     short loc_140311B20
0x140311b0e  mov     rcx, [rdi+60h]; P
0x140311b12  test    rcx, rcx
0x140311b15  jz      short loc_140311B20
0x140311b17  call    ?RefsFreeEresource@@YAXPEAU_MS_FAST_RESOURCE@@@Z; RefsFreeEresource(_MS_FAST_RESOURCE *)
0x140311b1c  mov     [rdi+60h], r13
0x140311b20  test    byte ptr [rdi+8], 40h
0x140311b24  jz      short loc_140311B53
0x140311b26  mov     rbx, [rdi+50h]
0x140311b2a  mov     rdx, [rdi+58h]
0x140311b2e  add     rdx, 110h
0x140311b35  lea     rcx, [rbx+340h]
0x140311b3c  call    cs:__imp_RtlAvlRemoveNode
0x140311b43  nop     dword ptr [rax+rax+00h]
0x140311b48  dec     dword ptr [rbx+348h]
0x140311b4e  and     qword ptr [rdi+8], 0FFFFFFFFFFFFFFBFh
0x140311b53  cmp     [rdi+0E8h], r13
0x140311b5a  jz      short loc_140311B67
0x140311b5c  mov     rdx, rdi; struct _FCB *
0x140311b5f  mov     rcx, rsi; struct _IRP_CONTEXT *
0x140311b62  call    ?RefsFreeFcbUsnRecord@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsFreeFcbUsnRecord(_IRP_CONTEXT *,_FCB *)
0x140311b67  mov     rcx, [rdi+50h]
0x140311b6b  xor     edx, edx
0x140311b6d  add     rcx, 270h
0x140311b74  call    cs:__imp_ExReleaseFastResource
0x140311b7b  nop     dword ptr [rax+rax+00h]
0x140311b80  mov     rcx, rdi; struct _FCB *
0x140311b83  mov     [r12], r13b
0x140311b87  call    ?RefsReleaseAllDataStreamSets@@YAXPEAU_FCB@@@Z; RefsReleaseAllDataStreamSets(_FCB *)
0x140311b8c  test    r15b, r15b
0x140311b8f  jnz     short loc_140311B9E
0x140311b91  mov     rcx, [rdi+58h]; Entry
0x140311b95  call    RefsDeleteNonpagedFcb
0x140311b9a  mov     [rdi+58h], r13
0x140311b9e  cmp     [rdi+108h], r13
0x140311ba5  jz      short loc_140311BAF
0x140311ba7  mov     rcx, rdi; struct _FCB *
0x140311baa  call    ?RefsCloseFcbTable@@YAXPEAU_FCB@@@Z; RefsCloseFcbTable(_FCB *)
0x140311baf  cmp     [rdi+0C0h], r13
0x140311bb6  jz      short loc_140311C24
0x140311bb8  mov     rbx, [rdi+50h]
0x140311bbc  call    cs:__imp_KeEnterGuardedRegion
0x140311bc3  nop     dword ptr [rax+rax+00h]
0x140311bc8  lea     rcx, [rbx+2D8h]; FastMutex
0x140311bcf  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140311bd6  nop     dword ptr [rax+rax+00h]
0x140311bdb  mov     rax, [rdi+0C0h]
0x140311be2  dec     dword ptr [rax]
0x140311be4  mov     rcx, [rdi+0C0h]; P
0x140311beb  cmp     [rcx], r13d
0x140311bee  jnz     short loc_140311BFE
0x140311bf0  xor     edx, edx; Tag
0x140311bf2  call    cs:__imp_ExFreePoolWithTag
0x140311bf9  nop     dword ptr [rax+rax+00h]
0x140311bfe  lea     rcx, [rbx+2D8h]; FastMutex
0x140311c05  mov     [rdi+0C0h], r13
0x140311c0c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140311c13  nop     dword ptr [rax+rax+00h]
0x140311c18  call    cs:__imp_KeLeaveGuardedRegion
0x140311c1f  nop     dword ptr [rax+rax+00h]
0x140311c24  mov     ebp, 823h
0x140311c29  xor     r9d, r9d; unsigned int
0x140311c2c  mov     edx, ebp; unsigned __int16
0x140311c2e  mov     r8, rdi; void *
0x140311c31  mov     rcx, rsi; struct _IRP_CONTEXT *
0x140311c34  call    ?RefsAddStructToRollbackList@@YAPEAU_ROLLBACK_STRUCT@@PEAU_IRP_CONTEXT@@GPEAXK@Z; RefsAddStructToRollbackList(_IRP_CONTEXT *,ushort,void *,ulong)
0x140311c39  mov     ebx, 10h
0x140311c3e  test    rax, rax
0x140311c41  jz      short loc_140311C4E
0x140311c43  mov     r8d, ebx; unsigned int
0x140311c46  mov     rdx, rax; struct _ROLLBACK_STRUCT *
0x140311c49  call    ?RefsProcessRollbackStruct@@YAXPEAU_IRP_CONTEXT@@PEAU_ROLLBACK_STRUCT@@K@Z; RefsProcessRollbackStruct(_IRP_CONTEXT *,_ROLLBACK_STRUCT *,ulong)
0x140311c4e  mov     rcx, [rsi+68h]; struct _IRP_CONTEXT *
0x140311c52  cmp     rsi, rcx
0x140311c55  jz      short loc_140311C74
0x140311c57  mov     edx, ebp; unsigned __int16
0x140311c59  xor     r9d, r9d; unsigned int
0x140311c5c  mov     r8, rdi; void *
0x140311c5f  call    ?RefsAddStructToRollbackList@@YAPEAU_ROLLBACK_STRUCT@@PEAU_IRP_CONTEXT@@GPEAXK@Z; RefsAddStructToRollbackList(_IRP_CONTEXT *,ushort,void *,ulong)
0x140311c64  test    rax, rax
0x140311c67  jz      short loc_140311C74
0x140311c69  mov     r8d, ebx; unsigned int
0x140311c6c  mov     rdx, rax; struct _ROLLBACK_STRUCT *
0x140311c6f  call    ?RefsProcessRollbackStruct@@YAXPEAU_IRP_CONTEXT@@PEAU_ROLLBACK_STRUCT@@K@Z; RefsProcessRollbackStruct(_IRP_CONTEXT *,_ROLLBACK_STRUCT *,ulong)
0x140311c74  test    r15b, r15b
0x140311c77  jnz     short loc_140311CE2
0x140311c79  mov     rax, [rdi+0F8h]
0x140311c80  test    rax, rax
0x140311c83  jz      short loc_140311C88
0x140311c85  mov     byte ptr [rax], 1
0x140311c88  test    byte ptr [rdi+8], 4
0x140311c8c  jnz     short loc_140311CA1
0x140311c8e  lea     rcx, [rdi+100h]; PerFileContextPointer
0x140311c95  call    cs:__imp_FsRtlTeardownPerFileContexts
0x140311c9c  nop     dword ptr [rax+rax+00h]
0x140311ca1  mov     rax, [rdi+8]
0x140311ca5  test    al, 2
0x140311ca7  jz      short loc_140311CBC
0x140311ca9  xor     edx, edx; Tag
0x140311cab  mov     rcx, rdi; P
0x140311cae  call    cs:__imp_ExFreePoolWithTag
0x140311cb5  nop     dword ptr [rax+rax+00h]
0x140311cba  jmp     short loc_140311CE8
0x140311cbc  lea     rcx, ?RefsFcbIndexLookasideList@@3U_LOOKASIDE_LIST_EX@@A; _LOOKASIDE_LIST_EX RefsFcbIndexLookasideList
0x140311cc3  mov     rdx, rdi; Entry
0x140311cc6  bt      rax, 0Ah
0x140311ccb  jb      short loc_140311CD4
0x140311ccd  lea     rcx, ?RefsFcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140311cd4  call    cs:__imp_ExFreeToLookasideListEx
0x140311cdb  nop     dword ptr [rax+rax+00h]
0x140311ce0  jmp     short loc_140311CE8
0x140311ce2  bts     qword ptr [rdi+8], 1Ah
0x140311ce8  add     rsp, 28h
0x140311cec  pop     r15
0x140311cee  pop     r14
0x140311cf0  pop     r13
0x140311cf2  pop     r12
0x140311cf4  pop     rdi
0x140311cf5  pop     rsi
0x140311cf6  pop     rbp
0x140311cf7  pop     rbx
0x140311cf8  retn
```
