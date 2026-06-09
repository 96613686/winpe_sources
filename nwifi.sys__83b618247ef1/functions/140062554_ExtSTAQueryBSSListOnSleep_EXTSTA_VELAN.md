# ExtSTAQueryBSSListOnSleep(EXTSTA_VELAN *)

- ea: `0x140062554`
- end: `0x140062628`
- name: `?ExtSTAQueryBSSListOnSleep@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `212`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14006196c`

## callees

- `0x14005f9d4`
- `0x140062554`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400625d9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400625d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400625ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400625ea`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400625af`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400625af`
- `NDIS!NdisReleaseRWLock` at `0x140062610`
- `NDIS!NdisReleaseRWLock` at `0x140062610`

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
0x140062554  mov     [rsp+arg_8], rbx
0x140062559  push    rdi
0x14006255a  sub     rsp, 20h
0x14006255e  xor     eax, eax
0x140062560  mov     [rsp+28h+LockState.OldIrql], 0
0x140062565  mov     word ptr [rsp+28h+LockState.LockState], ax
0x14006256a  mov     rbx, rcx
0x14006256d  mov     eax, [rcx+610h]
0x140062573  test    al, 1
0x140062575  jz      loc_14006261C
0x14006257b  cmp     dword ptr [rcx+64Ch], 1
0x140062582  jnz     loc_14006261C
0x140062588  call    ?ExtSTAInternalQueryBSSList@@YAPEAUEXTSTA_BSS_LIST@@PEAUEXTSTA_VELAN@@@Z; ExtSTAInternalQueryBSSList(EXTSTA_VELAN *)
0x14006258d  mov     rdi, rax
0x140062590  test    rax, rax
0x140062593  jz      loc_14006261C
0x140062599  mov     rcx, [rbx+0A38h]
0x1400625a0  lea     rdx, [rsp+28h+LockState]; LockState
0x1400625a5  xor     r8d, r8d; Flags
0x1400625a8  mov     rcx, [rcx+90h]; Lock
0x1400625af  call    cs:__imp_NdisAcquireRWLockWrite
0x1400625b6  nop     dword ptr [rax+rax+00h]
0x1400625bb  mov     rcx, [rbx+2F0h]
0x1400625c2  test    rcx, rcx
0x1400625c5  jz      short loc_1400625F6
0x1400625c7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400625cb  mov     rax, [rcx]
0x1400625ce  test    rax, rax
0x1400625d1  jz      short loc_1400625E7
0x1400625d3  mov     rdx, rcx; Entry
0x1400625d6  mov     rcx, rax; Lookaside
0x1400625d9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400625e0  nop     dword ptr [rax+rax+00h]
0x1400625e5  jmp     short loc_1400625F6
0x1400625e7  mov     edx, [rcx+8]; Tag
0x1400625ea  call    cs:__imp_ExFreePoolWithTag
0x1400625f1  nop     dword ptr [rax+rax+00h]
0x1400625f6  mov     rcx, [rbx+0A38h]
0x1400625fd  lea     rdx, [rsp+28h+LockState]; LockState
0x140062602  mov     [rbx+2F0h], rdi
0x140062609  mov     rcx, [rcx+90h]; Lock
0x140062610  call    cs:__imp_NdisReleaseRWLock
0x140062617  nop     dword ptr [rax+rax+00h]
0x14006261c  mov     rbx, [rsp+28h+arg_8]
0x140062621  add     rsp, 20h
0x140062625  pop     rdi
0x140062626  retn
```
