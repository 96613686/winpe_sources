# RefsDeleteCcb(_FCB &,_SCB &,_CCB *)

- ea: `0x1403146c0`
- end: `0x140314835`
- name: `?RefsDeleteCcb@@YAXAEAU_FCB@@AEAU_SCB@@PEAU_CCB@@@Z`
- size: `373`
- prototype: `void(struct _FCB *, struct _SCB *, struct _CCB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140332d24`

## callees

- `0x14002b110`
- `0x140052010`
- `0x1400c8644`
- `0x1403146c0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1403146f4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403146f4`
- `ntoskrnl!MmBadPointer` at `0x140314736`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1403147e7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140314806`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1403147e7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140314806`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140314704`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140314704`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140314758`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140314758`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140314764`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140314764`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403147b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140314824`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403147b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140314824`

## pseudocode

```c
void __fastcall RefsDeleteCcb(struct _FCB *a1, struct _SCB *a2, LONG *a3)
{
  PMRX_NET_ROOT pNetRoot; // rdi
  __int64 v6; // rax
  _QWORD *v7; // rcx
  void *v8; // rcx
  __int16 v9; // cx

  if ( *(_WORD *)a3 == 2056 )
  {
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(a3 + 96));
    v8 = (void *)*((_QWORD *)a3 + 59);
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      *((_QWORD *)a3 + 59) = 0;
    }
    RefsCleanupIndexCursor((struct _CCB *)a3);
  }
  if ( (a3[1] & 0x4000) != 0 )
    ExFreePoolWithTag(*((PVOID *)a3 + 3), 0);
  pNetRoot = a1->pNetRoot;
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)&pNetRoot->pSrvCall);
  v6 = *((_QWORD *)a3 + 9);
  *((_QWORD *)a3 + 9) = 0;
  if ( v6 )
  {
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(a3 + 14);
    v7[1] = 0;
    *v7 = 0;
  }
  ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(a3 + 10);
  *((_QWORD *)a3 + 6) = 0;
  *((_QWORD *)a3 + 5) = 0;
  *((_QWORD *)a3 + 6) = MmBadPointer;
  *((_QWORD *)a3 + 5) = MmBadPointer;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)&a1->pNetRoot->pSrvCall);
  KeLeaveGuardedRegion();
  if ( a3 == &a1[1].NumberOfBufferingStateChangeWaiters || a3 == (LONG *)((char *)&a1[1].1 + 144) )
  {
    *(_WORD *)a3 = 0;
  }
  else
  {
    v9 = *(_WORD *)a3;
    *(_WORD *)a3 = 0;
    if ( v9 == 2056 )
      ExFreeToLookasideListEx(&RefsCcbLookasideList, a3);
    else
      ExFreeToLookasideListEx(&RefsCcbDataLookasideList, a3);
  }
}

```

## disassembly

```asm
0x1403146c0  push    rbx
0x1403146c2  push    rbp
0x1403146c3  push    rsi
0x1403146c4  push    rdi
0x1403146c5  push    r14
0x1403146c7  sub     rsp, 20h
0x1403146cb  xor     ebp, ebp
0x1403146cd  mov     r14d, 808h
0x1403146d3  mov     rbx, r8
0x1403146d6  mov     rsi, rcx
0x1403146d9  cmp     [r8], r14w
0x1403146dd  jz      loc_140314797
0x1403146e3  test    dword ptr [rbx+4], 4000h
0x1403146ea  jnz     loc_14031481E
0x1403146f0  mov     rdi, [rsi+58h]
0x1403146f4  call    cs:__imp_KeEnterGuardedRegion
0x1403146fb  nop     dword ptr [rax+rax+00h]
0x140314700  lea     rcx, [rdi+8]; FastMutex
0x140314704  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14031470b  nop     dword ptr [rax+rax+00h]
0x140314710  mov     rax, [rbx+48h]
0x140314714  mov     [rbx+48h], rbp
0x140314718  test    rax, rax
0x14031471b  jz      short loc_14031472D
0x14031471d  lea     rcx, [rbx+38h]
0x140314721  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140314726  mov     [rcx+8], rbp
0x14031472a  mov     [rcx], rbp
0x14031472d  lea     rcx, [rbx+28h]
0x140314731  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140314736  mov     rax, cs:MmBadPointer
0x14031473d  mov     [rbx+30h], rbp
0x140314741  mov     [rbx+28h], rbp
0x140314745  mov     rcx, [rax]
0x140314748  mov     [rbx+30h], rcx
0x14031474c  mov     [rbx+28h], rcx
0x140314750  mov     rcx, [rsi+58h]
0x140314754  add     rcx, 8; FastMutex
0x140314758  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14031475f  nop     dword ptr [rax+rax+00h]
0x140314764  call    cs:__imp_KeLeaveGuardedRegion
0x14031476b  nop     dword ptr [rax+rax+00h]
0x140314770  lea     rax, [rsi+368h]
0x140314777  cmp     rbx, rax
0x14031477a  jz      short loc_140314788
0x14031477c  lea     rax, [rsi+320h]
0x140314783  cmp     rbx, rax
0x140314786  jnz     short loc_1403147D1
0x140314788  mov     [rbx], bp
0x14031478b  add     rsp, 20h
0x14031478f  pop     r14
0x140314791  pop     rdi
0x140314792  pop     rsi
0x140314793  pop     rbp
0x140314794  pop     rbx
0x140314795  retn
0x140314797  lea     rcx, [r8+180h]; this
0x14031479e  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x1403147a3  mov     rcx, [rbx+1D8h]; P
0x1403147aa  test    rcx, rcx
0x1403147ad  jz      short loc_1403147C4
0x1403147af  xor     edx, edx; Tag
0x1403147b1  call    cs:__imp_ExFreePoolWithTag
0x1403147b8  nop     dword ptr [rax+rax+00h]
0x1403147bd  mov     [rbx+1D8h], rbp
0x1403147c4  mov     rcx, rbx; struct _CCB *
0x1403147c7  call    ?RefsCleanupIndexCursor@@YAXAEAU_CCB@@@Z; RefsCleanupIndexCursor(_CCB &)
0x1403147cc  jmp     loc_1403146E3
0x1403147d1  movzx   ecx, word ptr [rbx]
0x1403147d4  mov     rdx, rbx; Entry
0x1403147d7  mov     [rbx], bp
0x1403147da  cmp     cx, r14w
0x1403147de  jz      short loc_1403147FF
0x1403147e0  lea     rcx, ?RefsCcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1403147e7  call    cs:__imp_ExFreeToLookasideListEx
0x1403147ee  nop     dword ptr [rax+rax+00h]
0x1403147f3  add     rsp, 20h
0x1403147f7  pop     r14
0x1403147f9  pop     rdi
0x1403147fa  pop     rsi
0x1403147fb  pop     rbp
0x1403147fc  pop     rbx
0x1403147fd  retn
0x1403147ff  lea     rcx, ?RefsCcbLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140314806  call    cs:__imp_ExFreeToLookasideListEx
0x14031480d  nop     dword ptr [rax+rax+00h]
0x140314812  add     rsp, 20h
0x140314816  pop     r14
0x140314818  pop     rdi
0x140314819  pop     rsi
0x14031481a  pop     rbp
0x14031481b  pop     rbx
0x14031481c  retn
0x14031481e  mov     rcx, [rbx+18h]; P
0x140314822  xor     edx, edx; Tag
0x140314824  call    cs:__imp_ExFreePoolWithTag
0x14031482b  nop     dword ptr [rax+rax+00h]
0x140314830  jmp     loc_1403146F0
```
