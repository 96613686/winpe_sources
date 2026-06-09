# ExtSTAQueryBSSListOnSleep(EXTSTA_VELAN *)

- ea: `0x140063d84`
- end: `0x140063e58`
- name: `?ExtSTAQueryBSSListOnSleep@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `212`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14006319c`

## callees

- `0x140061204`
- `0x140063d84`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063e09`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140063e09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063e1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063e1a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140063ddf`
- `NDIS!NdisAcquireRWLockWrite` at `0x140063ddf`
- `NDIS!NdisReleaseRWLock` at `0x140063e40`
- `NDIS!NdisReleaseRWLock` at `0x140063e40`

## pseudocode

```c
void __fastcall ExtSTAQueryBSSListOnSleep(struct EXTSTA_VELAN *a1, unsigned int a2)
{
  EXTSTA_BSS_LIST *BSSList; // rdi
  EXTSTA_BSS_LIST *pPreSleepBSSList; // rcx
  ULONG *v5; // rcx
  _VELAN *pGenVElan; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( (*(_DWORD *)&a1->RoD & 1) != 0 && a1->RoD.CurrentBSSType == dot11_BSS_type_infrastructure )
  {
    BSSList = ExtSTAInternalQueryBSSList(a1, a2);
    if ( BSSList )
    {
      NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
      pPreSleepBSSList = a1->AssocMgr.pPreSleepBSSList;
      if ( pPreSleepBSSList )
      {
        v5 = (ULONG *)&pPreSleepBSSList[-1].BSSIDList[253][2];
        if ( *(_QWORD *)v5 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v5, v5);
        else
          ExFreePoolWithTag(v5, v5[2]);
      }
      pGenVElan = a1->pGenVElan;
      a1->AssocMgr.pPreSleepBSSList = BSSList;
      NdisReleaseRWLock(pGenVElan->pRWLock, &LockState);
    }
  }
}

```

## disassembly

```asm
0x140063d84  mov     [rsp+arg_8], rbx
0x140063d89  push    rdi
0x140063d8a  sub     rsp, 20h
0x140063d8e  xor     eax, eax
0x140063d90  mov     [rsp+28h+LockState.OldIrql], 0
0x140063d95  mov     word ptr [rsp+28h+LockState.LockState], ax
0x140063d9a  mov     rbx, rcx
0x140063d9d  mov     eax, [rcx+610h]
0x140063da3  test    al, 1
0x140063da5  jz      loc_140063E4C
0x140063dab  cmp     dword ptr [rcx+64Ch], 1
0x140063db2  jnz     loc_140063E4C
0x140063db8  call    ?ExtSTAInternalQueryBSSList@@YAPEAUEXTSTA_BSS_LIST@@PEAUEXTSTA_VELAN@@@Z; ExtSTAInternalQueryBSSList(EXTSTA_VELAN *)
0x140063dbd  mov     rdi, rax
0x140063dc0  test    rax, rax
0x140063dc3  jz      loc_140063E4C
0x140063dc9  mov     rcx, [rbx+0A38h]
0x140063dd0  lea     rdx, [rsp+28h+LockState]; LockState
0x140063dd5  xor     r8d, r8d; Flags
0x140063dd8  mov     rcx, [rcx+90h]; Lock
0x140063ddf  call    cs:__imp_NdisAcquireRWLockWrite
0x140063de6  nop     dword ptr [rax+rax+00h]
0x140063deb  mov     rcx, [rbx+2F0h]
0x140063df2  test    rcx, rcx
0x140063df5  jz      short loc_140063E26
0x140063df7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140063dfb  mov     rax, [rcx]
0x140063dfe  test    rax, rax
0x140063e01  jz      short loc_140063E17
0x140063e03  mov     rdx, rcx; Entry
0x140063e06  mov     rcx, rax; Lookaside
0x140063e09  call    cs:__imp_ExFreeToNPagedLookasideList
0x140063e10  nop     dword ptr [rax+rax+00h]
0x140063e15  jmp     short loc_140063E26
0x140063e17  mov     edx, [rcx+8]; Tag
0x140063e1a  call    cs:__imp_ExFreePoolWithTag
0x140063e21  nop     dword ptr [rax+rax+00h]
0x140063e26  mov     rcx, [rbx+0A38h]
0x140063e2d  lea     rdx, [rsp+28h+LockState]; LockState
0x140063e32  mov     [rbx+2F0h], rdi
0x140063e39  mov     rcx, [rcx+90h]; Lock
0x140063e40  call    cs:__imp_NdisReleaseRWLock
0x140063e47  nop     dword ptr [rax+rax+00h]
0x140063e4c  mov     rbx, [rsp+28h+arg_8]
0x140063e51  add     rsp, 20h
0x140063e55  pop     rdi
0x140063e56  retn
```
