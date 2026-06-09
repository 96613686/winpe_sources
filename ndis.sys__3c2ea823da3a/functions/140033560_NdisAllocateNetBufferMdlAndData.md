# NdisAllocateNetBufferMdlAndData

- ea: `0x140033560`
- end: `0x1400338fc`
- name: `NdisAllocateNetBufferMdlAndData`
- size: `924`
- prototype: `PNET_BUFFER __stdcall(NDIS_HANDLE PoolHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140033510`
- `0x140033560`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140033712`
- `ntoskrnl!DbgPrint` at `0x140033712`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140033772`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140033772`
- `ntoskrnl!ExAllocatePool2` at `0x14003384b`
- `ntoskrnl!ExAllocatePool2` at `0x14003384b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003365b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400337d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400338b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003365b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400337d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400338b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400335e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400337a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033878`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400335e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400337a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033878`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003363d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003363d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033677`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400337ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033816`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033677`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400337ec`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140033816`
- `ntoskrnl!ExQueryDepthSList` at `0x1400338d6`
- `ntoskrnl!ExQueryDepthSList` at `0x1400338d6`

## pseudocode

```c
PNET_BUFFER __stdcall NdisAllocateNetBufferMdlAndData(NDIS_HANDLE PoolHandle)
{
  PSLIST_ENTRY v2; // rbx
  unsigned int Number; // r15d
  int v4; // r12d
  unsigned __int64 v5; // rbx
  char *v6; // rsi
  KIRQL v7; // r14
  _SLIST_ENTRY *v8; // rsi
  int v9; // ecx
  __int64 v11; // r9
  unsigned __int64 v12; // r8
  __int16 v13; // dx
  int v14; // edx
  KIRQL v15; // al
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  struct _SLIST_ENTRY *Pool2; // rax
  KIRQL v19; // al
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  KIRQL v22; // r8
  _QWORD *v23; // rax

  v2 = 0;
  if ( !PoolHandle )
    return (PNET_BUFFER)v2;
  if ( (*((_DWORD *)PoolHandle + 20) & 1) == 0 )
  {
    DbgPrint("NdisAllocateNetBufferMdlAndData: Pool %p wrong pool type.\n", PoolHandle);
    return (PNET_BUFFER)v2;
  }
  if ( (*((_DWORD *)PoolHandle + 1) & 1) != 0 )
  {
    v4 = 0;
    v2 = (PSLIST_ENTRY)ndisPplAllocateFromSpecialPool((const struct _NDIS_POOL_HEADER *)PoolHandle);
    goto LABEL_10;
  }
  Number = KeGetPcr()->Prcb.Number;
  v4 = 1;
  if ( ndisMaxNumberOfProcessors != 1 )
  {
    v5 = (unsigned __int64)Number << 8;
    v6 = (char *)PoolHandle + v5 + 384;
    if ( !v6[216] )
    {
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6 + 26);
      if ( !v6[216] )
      {
        ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)v6,
          ndisAllocateFromNPagedPool,
          *(PFREE_FUNCTION_EX *)&v6[-v5 - 200],
          NonPagedPoolNx,
          0,
          *(unsigned int *)&v6[-v5 - 212],
          *(_DWORD *)&v6[-v5 - 216],
          0x400u);
        v6[216] = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)v6 + 26, v7);
    }
    _InterlockedIncrement((volatile signed __int32 *)v6 + 5);
    v2 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v6 + 24));
    if ( v2 )
      goto LABEL_10;
    if ( ExQueryDepthSList(*((PSLIST_HEADER *)v6 + 25)) >= 0xAu )
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6 + 26);
      v16 = *((_QWORD *)v6 + 24);
      *((_QWORD *)v6 + 24) = *((_QWORD *)v6 + 25);
      *((_QWORD *)v6 + 25) = v16;
      KeReleaseSpinLock((PKSPIN_LOCK)v6 + 26, v15);
      v2 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v6 + 24));
      if ( v2 )
        goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)v6 + 6);
  }
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 37);
  v2 = ExpInterlockedPopEntrySList((PSLIST_HEADER)PoolHandle + 8);
  if ( v2 )
    goto LABEL_28;
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 38);
  v17 = *((unsigned int *)PoolHandle + 43);
  if ( v17 + 32 >= v17
    && (Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v17 + 32, *((unsigned int *)PoolHandle + 42))) != 0 )
  {
    v2 = Pool2 + 2;
    Pool2->Next = 0;
    if ( Pool2 != (struct _SLIST_ENTRY *)-32LL )
    {
      Pool2->Next = (_SLIST_ENTRY *)PoolHandle;
      v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 1);
      v20 = *((_QWORD *)PoolHandle + 2);
      v21 = (char *)PoolHandle + 16;
      v22 = v19;
      if ( *(NDIS_HANDLE *)(v20 + 8) != (char *)PoolHandle + 16 )
        __fastfail(3u);
      v23 = &v2[-2].Next + 1;
      *v23 = v20;
      v23[1] = v21;
      *(_QWORD *)(v20 + 8) = (char *)v2 - 24;
      *v21 = (char *)v2 - 24;
      KeReleaseSpinLock((PKSPIN_LOCK)PoolHandle + 1, v22);
      v4 = 0;
LABEL_28:
      *((_DWORD *)&v2[-1].Next + 2) = Number;
      goto LABEL_10;
    }
  }
  else
  {
    v2 = 0;
  }
  v4 = 0;
LABEL_10:
  if ( !v2 )
    return 0;
  v8 = v2 + 11;
  if ( v4 )
  {
    *((_DWORD *)&v2[13].Next + 2) = *((_DWORD *)PoolHandle + 21);
    v8->Next = 0;
  }
  else
  {
    v11 = *((unsigned int *)PoolHandle + 21);
    v12 = (unsigned __int64)v8 + *((unsigned int *)PoolHandle + 22);
    v13 = (_WORD)v8 + *((_DWORD *)PoolHandle + 22);
    v8->Next = 0;
    *((_WORD *)&v2[11].Next + 5) = 0;
    *((_DWORD *)&v2[13].Next + 2) = v11;
    v2[13].Next = (_SLIST_ENTRY *)(v12 & 0xFFFFFFFFFFFFF000uLL);
    v14 = v13 & 0xFFF;
    *((_DWORD *)&v2[13].Next + 3) = v14;
    *((_WORD *)&v2[11].Next + 4) = 8 * ((((unsigned __int64)(unsigned __int16)v14 + v11 + 4095) >> 12) + 6);
    MmBuildMdlForNonPagedPool((PMDL)&v2[11]);
  }
  v9 = *((_DWORD *)PoolHandle + 21);
  v2->Next = 0;
  *((_QWORD *)&v2[3].Next + 1) = PoolHandle;
  *((_QWORD *)&v2->Next + 1) = v8;
  LODWORD(v2[1].Next) = v9;
  v2[2].Next = v8;
  *((_DWORD *)&v2[2].Next + 2) = v9;
  *((_DWORD *)&v2[1].Next + 2) = 0;
  LODWORD(v2[3].Next) = 0;
  *((_QWORD *)&v2[4].Next + 1) = 0;
  v2[4].Next = 0;
  *((_QWORD *)&v2[8].Next + 1) = 0;
  v2[8].Next = 0;
  *((_QWORD *)&v2[10].Next + 1) = 0;
  return (PNET_BUFFER)v2;
}

```

## disassembly

```asm
0x140033560  mov     [rsp+arg_8], rbx
0x140033565  mov     [rsp+arg_10], rbp
0x14003356a  push    rsi
0x14003356b  push    rdi
0x14003356c  push    r12
0x14003356e  push    r13
0x140033570  push    r15
0x140033572  sub     rsp, 40h
0x140033576  xor     r13d, r13d
0x140033579  mov     rdi, rcx
0x14003357c  mov     ebx, r13d
0x14003357f  test    rcx, rcx
0x140033582  jz      loc_1400336EA
0x140033588  mov     eax, [rcx+50h]
0x14003358b  test    al, 1
0x14003358d  jz      loc_140033708
0x140033593  mov     eax, [rcx+4]
0x140033596  test    al, 1
0x140033598  jnz     loc_14003378B
0x14003359e  mov     r15d, gs:1A4h
0x1400335a7  mov     r12d, 1
0x1400335ad  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, r12d; ulong ndisMaxNumberOfProcessors
0x1400335b4  jz      loc_140033808
0x1400335ba  mov     ebx, r15d
0x1400335bd  lea     rsi, [rcx+180h]
0x1400335c4  shl     rbx, 8
0x1400335c8  add     rsi, rbx
0x1400335cb  cmp     [rsi+0D8h], r13b
0x1400335d2  jnz     loc_14003366C
0x1400335d8  lea     rcx, [rsi+0D0h]; SpinLock
0x1400335df  mov     [rsp+68h+arg_0], r14
0x1400335e4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400335eb  nop     dword ptr [rax+rax+00h]
0x1400335f0  movzx   r14d, al
0x1400335f4  cmp     [rsi+0D8h], r13b
0x1400335fb  jnz     short loc_140033650
0x1400335fd  mov     [rsp+68h+Depth], 400h; Depth
0x140033604  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x14003360b  mov     r8, rsi
0x14003360e  mov     r9d, 200h; PoolType
0x140033614  sub     r8, rbx
0x140033617  mov     ecx, [r8-0D4h]
0x14003361e  mov     eax, [r8-0D8h]
0x140033625  mov     r8, [r8-0C8h]; Free
0x14003362c  mov     [rsp+68h+Tag], eax; Tag
0x140033630  mov     [rsp+68h+Size], rcx; Size
0x140033635  mov     rcx, rsi; Lookaside
0x140033638  mov     [rsp+68h+Flags], r13d; Flags
0x14003363d  call    cs:__imp_ExInitializeLookasideListEx
0x140033644  nop     dword ptr [rax+rax+00h]
0x140033649  mov     [rsi+0D8h], r12b
0x140033650  movzx   edx, r14b; NewIrql
0x140033654  lea     rcx, [rsi+0D0h]; SpinLock
0x14003365b  call    cs:__imp_KeReleaseSpinLock
0x140033662  nop     dword ptr [rax+rax+00h]
0x140033667  mov     r14, [rsp+68h+arg_0]
0x14003366c  lock inc dword ptr [rsi+14h]
0x140033670  mov     rcx, [rsi+0C0h]; ListHead
0x140033677  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003367e  nop     dword ptr [rax+rax+00h]
0x140033683  mov     rbx, rax
0x140033686  test    rax, rax
0x140033689  jz      loc_1400338CF
0x14003368f  test    rbx, rbx
0x140033692  jz      loc_140033783
0x140033698  lea     rsi, [rbx+0B0h]
0x14003369f  test    r12d, r12d
0x1400336a2  jz      short loc_140033720
0x1400336a4  mov     eax, [rdi+54h]
0x1400336a7  mov     [rsi+28h], eax
0x1400336aa  mov     [rsi], r13
0x1400336ad  mov     ecx, [rdi+54h]
0x1400336b0  mov     [rbx], r13
0x1400336b3  mov     [rbx+38h], rdi
0x1400336b7  mov     [rbx+8], rsi
0x1400336bb  mov     [rbx+10h], ecx
0x1400336be  mov     [rbx+20h], rsi
0x1400336c2  mov     [rbx+28h], ecx
0x1400336c5  mov     [rbx+18h], r13d
0x1400336c9  mov     [rbx+30h], r13d
0x1400336cd  mov     [rbx+48h], r13
0x1400336d1  mov     [rbx+40h], r13
0x1400336d5  mov     [rbx+88h], r13
0x1400336dc  mov     [rbx+80h], r13
0x1400336e3  mov     [rbx+0A8h], r13
0x1400336ea  mov     rbp, [rsp+68h+arg_10]
0x1400336f2  mov     rax, rbx
0x1400336f5  mov     rbx, [rsp+68h+arg_8]
0x1400336fa  add     rsp, 40h
0x1400336fe  pop     r15
0x140033700  pop     r13
0x140033702  pop     r12
0x140033704  pop     rdi
0x140033705  pop     rsi
0x140033706  retn
0x140033708  mov     rdx, rdi
0x14003370b  lea     rcx, aNdisallocatene; "NdisAllocateNetBufferMdlAndData: Pool %"...
0x140033712  call    cs:__imp_DbgPrint
0x140033719  nop     dword ptr [rax+rax+00h]
0x14003371e  jmp     short loc_1400336EA
0x140033720  mov     r8d, [rdi+58h]
0x140033724  mov     r9d, [rdi+54h]
0x140033728  add     r8, rsi
0x14003372b  mov     edx, r8d
0x14003372e  mov     [rsi], r13
0x140033731  mov     eax, edx
0x140033733  mov     [rsi+0Ah], r13w
0x140033738  and     eax, 0FFFh
0x14003373d  mov     [rsi+28h], r9d
0x140033741  lea     rcx, [r9+0FFFh]
0x140033748  and     r8, 0FFFFFFFFFFFFF000h
0x14003374f  add     rcx, rax
0x140033752  mov     [rsi+20h], r8
0x140033756  shr     rcx, 0Ch
0x14003375a  and     edx, 0FFFh
0x140033760  add     cx, 6
0x140033764  mov     [rsi+2Ch], edx
0x140033767  shl     cx, 3
0x14003376b  mov     [rsi+8], cx
0x14003376f  mov     rcx, rsi; MemoryDescriptorList
0x140033772  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140033779  nop     dword ptr [rax+rax+00h]
0x14003377e  jmp     loc_1400336AD
0x140033783  mov     rbx, r13
0x140033786  jmp     loc_1400336EA
0x14003378b  mov     r12d, r13d
0x14003378e  call    ?ndisPplAllocateFromSpecialPool@@YAPEAXPEBU_NDIS_POOL_HEADER@@@Z; ndisPplAllocateFromSpecialPool(_NDIS_POOL_HEADER const *)
0x140033793  mov     rbx, rax
0x140033796  jmp     loc_14003368F
0x14003379b  lea     rcx, [rsi+0D0h]; SpinLock
0x1400337a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400337a9  nop     dword ptr [rax+rax+00h]
0x1400337ae  mov     rdx, [rsi+0C0h]
0x1400337b5  lea     rcx, [rsi+0D0h]; SpinLock
0x1400337bc  movzx   r8d, al
0x1400337c0  mov     rax, [rsi+0C8h]
0x1400337c7  mov     [rsi+0C0h], rax
0x1400337ce  mov     [rsi+0C8h], rdx
0x1400337d5  movzx   edx, r8b; NewIrql
0x1400337d9  call    cs:__imp_KeReleaseSpinLock
0x1400337e0  nop     dword ptr [rax+rax+00h]
0x1400337e5  mov     rcx, [rsi+0C0h]; ListHead
0x1400337ec  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400337f3  nop     dword ptr [rax+rax+00h]
0x1400337f8  mov     rbx, rax
0x1400337fb  test    rax, rax
0x1400337fe  jnz     loc_14003368F
0x140033804  lock inc dword ptr [rsi+18h]
0x140033808  lea     rsi, [rdi+80h]
0x14003380f  lock inc dword ptr [rsi+14h]
0x140033813  mov     rcx, rsi; ListHead
0x140033816  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003381d  nop     dword ptr [rax+rax+00h]
0x140033822  mov     rbx, rax
0x140033825  test    rax, rax
0x140033828  jnz     loc_1400338C6
0x14003382e  lock inc dword ptr [rsi+18h]
0x140033832  mov     eax, [rsi+2Ch]
0x140033835  lea     rdx, [rax+20h]
0x140033839  cmp     rdx, rax
0x14003383c  jb      loc_1400338F1
0x140033842  mov     r8d, [rsi+28h]
0x140033846  mov     ecx, 42h ; 'B'
0x14003384b  call    cs:__imp_ExAllocatePool2
0x140033852  nop     dword ptr [rax+rax+00h]
0x140033857  test    rax, rax
0x14003385a  jz      loc_1400338F1
0x140033860  lea     rbx, [rax+20h]
0x140033864  mov     [rax], r13
0x140033867  test    rbx, rbx
0x14003386a  jz      loc_1400338F4
0x140033870  lea     rcx, [rdi+8]; SpinLock
0x140033874  mov     [rbx-20h], rdi
0x140033878  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003387f  nop     dword ptr [rax+rax+00h]
0x140033884  mov     rdx, [rdi+10h]
0x140033888  lea     rcx, [rdi+10h]
0x14003388c  movzx   r8d, al
0x140033890  cmp     [rdx+8], rcx
0x140033894  jz      short loc_14003389D
0x140033896  mov     ecx, 3
0x14003389b  int     29h; Win8: RtlFailFast(ecx)
0x14003389d  lea     rax, [rbx-18h]
0x1400338a1  mov     [rax], rdx
0x1400338a4  mov     [rax+8], rcx
0x1400338a8  mov     [rdx+8], rax
0x1400338ac  movzx   edx, r8b; NewIrql
0x1400338b0  mov     [rcx], rax
0x1400338b3  lea     rcx, [rdi+8]; SpinLock
0x1400338b7  call    cs:__imp_KeReleaseSpinLock
0x1400338be  nop     dword ptr [rax+rax+00h]
0x1400338c3  mov     r12d, r13d
0x1400338c6  mov     [rbx-8], r15d
0x1400338ca  jmp     loc_14003368F
0x1400338cf  mov     rcx, [rsi+0C8h]; SListHead
0x1400338d6  call    cs:__imp_ExQueryDepthSList
0x1400338dd  nop     dword ptr [rax+rax+00h]
0x1400338e2  cmp     ax, 0Ah
0x1400338e6  jb      loc_140033804
0x1400338ec  jmp     loc_14003379B
0x1400338f1  mov     rbx, r13
0x1400338f4  mov     r12d, r13d
0x1400338f7  jmp     loc_14003368F
```
