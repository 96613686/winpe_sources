# RefsDeleteCcb(_FCB &,_SCB &,_CCB *)

- ea: `0x1403188f0`
- end: `0x140318a65`
- name: `?RefsDeleteCcb@@YAXAEAU_FCB@@AEAU_SCB@@PEAU_CCB@@@Z`
- size: `373`
- prototype: `void(struct _FCB *, struct _SCB *, struct _CCB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1403349e4`

## callees

- `0x14002b620`
- `0x14003bf40`
- `0x1400cedec`
- `0x1403188f0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x140318924`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140318924`
- `ntoskrnl!MmBadPointer` at `0x140318966`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140318a17`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140318a36`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140318a17`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140318a36`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140318934`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140318934`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140318988`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140318988`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140318994`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140318994`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403189e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140318a54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403189e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140318a54`

## pseudocode

```c
void __fastcall RefsDeleteCcb(struct _FCB *a1, struct _SCB *a2, PKEVENT *a3)
{
  PMRX_NET_ROOT pNetRoot; // rdi
  PKEVENT v6; // rax
  _QWORD *v7; // rcx
  PKEVENT v8; // rcx
  __int16 v9; // cx

  if ( *(_WORD *)a3 == 2056 )
  {
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(a3 + 48));
    v8 = a3[59];
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      a3[59] = 0;
    }
    RefsCleanupIndexCursor((struct _CCB *)a3);
  }
  if ( (*((_DWORD *)a3 + 1) & 0x4000) != 0 )
    ExFreePoolWithTag(a3[3], 0);
  pNetRoot = a1->pNetRoot;
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)&pNetRoot->pSrvCall);
  v6 = a3[9];
  a3[9] = 0;
  if ( v6 )
  {
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(a3 + 7);
    v7[1] = 0;
    *v7 = 0;
  }
  ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(a3 + 5);
  a3[6] = 0;
  a3[5] = 0;
  a3[6] = (PKEVENT)MmBadPointer;
  a3[5] = (PKEVENT)MmBadPointer;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)&a1->pNetRoot->pSrvCall);
  KeLeaveGuardedRegion();
  if ( a3 == &a1[1].pBufferingStateChangeCompletedEvent || a3 == (PKEVENT *)((char *)&a1[1].1 + 144) )
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
0x1403188f0  push    rbx
0x1403188f2  push    rbp
0x1403188f3  push    rsi
0x1403188f4  push    rdi
0x1403188f5  push    r14
0x1403188f7  sub     rsp, 20h
0x1403188fb  xor     ebp, ebp
0x1403188fd  mov     r14d, 808h
0x140318903  mov     rbx, r8
0x140318906  mov     rsi, rcx
0x140318909  cmp     [r8], r14w
0x14031890d  jz      loc_1403189C7
0x140318913  test    dword ptr [rbx+4], 4000h
0x14031891a  jnz     loc_140318A4E
0x140318920  mov     rdi, [rsi+58h]
0x140318924  call    cs:__imp_KeEnterGuardedRegion
0x14031892b  nop     dword ptr [rax+rax+00h]
0x140318930  lea     rcx, [rdi+8]; FastMutex
0x140318934  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14031893b  nop     dword ptr [rax+rax+00h]
0x140318940  mov     rax, [rbx+48h]
0x140318944  mov     [rbx+48h], rbp
0x140318948  test    rax, rax
0x14031894b  jz      short loc_14031895D
0x14031894d  lea     rcx, [rbx+38h]
0x140318951  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140318956  mov     [rcx+8], rbp
0x14031895a  mov     [rcx], rbp
0x14031895d  lea     rcx, [rbx+28h]
0x140318961  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140318966  mov     rax, cs:MmBadPointer
0x14031896d  mov     [rbx+30h], rbp
0x140318971  mov     [rbx+28h], rbp
0x140318975  mov     rcx, [rax]
0x140318978  mov     [rbx+30h], rcx
0x14031897c  mov     [rbx+28h], rcx
0x140318980  mov     rcx, [rsi+58h]
0x140318984  add     rcx, 8; FastMutex
0x140318988  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14031898f  nop     dword ptr [rax+rax+00h]
0x140318994  call    cs:__imp_KeLeaveGuardedRegion
0x14031899b  nop     dword ptr [rax+rax+00h]
0x1403189a0  lea     rax, [rsi+360h]
0x1403189a7  cmp     rbx, rax
0x1403189aa  jz      short loc_1403189B8
0x1403189ac  lea     rax, [rsi+320h]
0x1403189b3  cmp     rbx, rax
0x1403189b6  jnz     short loc_140318A01
0x1403189b8  mov     [rbx], bp
0x1403189bb  add     rsp, 20h
0x1403189bf  pop     r14
0x1403189c1  pop     rdi
0x1403189c2  pop     rsi
0x1403189c3  pop     rbp
0x1403189c4  pop     rbx
0x1403189c5  retn
0x1403189c7  lea     rcx, [r8+180h]; this
0x1403189ce  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x1403189d3  mov     rcx, [rbx+1D8h]; P
0x1403189da  test    rcx, rcx
0x1403189dd  jz      short loc_1403189F4
0x1403189df  xor     edx, edx; Tag
0x1403189e1  call    cs:__imp_ExFreePoolWithTag
0x1403189e8  nop     dword ptr [rax+rax+00h]
0x1403189ed  mov     [rbx+1D8h], rbp
0x1403189f4  mov     rcx, rbx; struct _CCB *
0x1403189f7  call    ?RefsCleanupIndexCursor@@YAXAEAU_CCB@@@Z; RefsCleanupIndexCursor(_CCB &)
0x1403189fc  jmp     loc_140318913
0x140318a01  movzx   ecx, word ptr [rbx]
0x140318a04  mov     rdx, rbx; Entry
0x140318a07  mov     [rbx], bp
0x140318a0a  cmp     cx, r14w
0x140318a0e  jz      short loc_140318A2F
0x140318a10  lea     rcx, ?RefsCcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140318a17  call    cs:__imp_ExFreeToLookasideListEx
0x140318a1e  nop     dword ptr [rax+rax+00h]
0x140318a23  add     rsp, 20h
0x140318a27  pop     r14
0x140318a29  pop     rdi
0x140318a2a  pop     rsi
0x140318a2b  pop     rbp
0x140318a2c  pop     rbx
0x140318a2d  retn
0x140318a2f  lea     rcx, ?RefsCcbLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140318a36  call    cs:__imp_ExFreeToLookasideListEx
0x140318a3d  nop     dword ptr [rax+rax+00h]
0x140318a42  add     rsp, 20h
0x140318a46  pop     r14
0x140318a48  pop     rdi
0x140318a49  pop     rsi
0x140318a4a  pop     rbp
0x140318a4b  pop     rbx
0x140318a4c  retn
0x140318a4e  mov     rcx, [rbx+18h]; P
0x140318a52  xor     edx, edx; Tag
0x140318a54  call    cs:__imp_ExFreePoolWithTag
0x140318a5b  nop     dword ptr [rax+rax+00h]
0x140318a60  jmp     loc_140318920
```
