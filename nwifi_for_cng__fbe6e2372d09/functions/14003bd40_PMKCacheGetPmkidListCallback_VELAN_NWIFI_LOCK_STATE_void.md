# PMKCacheGetPmkidListCallback(_VELAN *,_NWIFI_LOCK_STATE *,void *)

- ea: `0x14003bd40`
- end: `0x14003be42`
- name: `?PMKCacheGetPmkidListCallback@@YAXPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAX@Z`
- size: `258`
- prototype: `void __fastcall(struct _VELAN *, PLOCK_STATE_EX LockState, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14000ad28`
- `0x14003b918`
- `0x14003bb14`
- `0x14003bd40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bded`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bded`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bdfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bdfe`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003bdca`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003bdca`
- `NDIS!NdisReleaseRWLock` at `0x14003bd98`
- `NDIS!NdisReleaseRWLock` at `0x14003bd98`

## string_xrefs

- `0x14003be1e`: `PMKCacheGetPmkidListCallback [PmkId]`

## pseudocode

```c
void __fastcall PMKCacheGetPmkidListCallback(
        struct _VELAN *a1,
        struct _NWIFI_LOCK_STATE *LockState,
        struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *a3)
{
  ULONG uNumOfEntries; // ebp
  int PmkidList; // eax
  int v7; // edx
  int v8; // ecx
  struct DOT11_PMKID_LIST *v9; // rbx
  char v10; // si
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF
  struct DOT11_PMKID_LIST *v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  v11 = 0;
  LOBYTE(uNumOfEntries) = 0;
  PmkidList = Dot11GetPmkidList(a1, LockState, a3 + 3, &v12, &v11);
  v9 = v12;
  v10 = PmkidList;
  if ( !PmkidList )
  {
    uNumOfEntries = v12->uNumOfEntries;
    NdisReleaseRWLock(a1->pRWLock, &LockState->lockStateEx);
    v10 = Dot11SetPmkIdList(a1, a1->pDefaultMacState, v9, v11);
    NdisAcquireRWLockWrite(a1->pRWLock, &LockState->lockStateEx, 0);
  }
  if ( v9 )
  {
    if ( *(_QWORD *)&v9[-1].PMKIDs[0].PMKID[6] )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v9[-1].PMKIDs[0].PMKID[6], &v9[-1].PMKIDs[0].PMKID[6]);
    else
      ExFreePoolWithTag(&v9[-1].PMKIDs[0].PMKID[6], *(_DWORD *)&v9[-1].PMKIDs[0].PMKID[14]);
  }
  if ( (byte_1400B2804 & 0x10) != 0 )
    McTemplateK0zqq_EtwWriteTransfer(
      v8,
      v7,
      (_DWORD)a1 + 4920,
      (unsigned int)L"PMKCacheGetPmkidListCallback [PmkId]",
      v10,
      uNumOfEntries);
}

```

## disassembly

```asm
0x14003bd40  mov     r11, rsp
0x14003bd43  mov     [r11+8], rbx
0x14003bd47  mov     [r11+10h], rbp
0x14003bd4b  push    rsi
0x14003bd4c  push    rdi
0x14003bd4d  push    r14
0x14003bd4f  sub     rsp, 30h
0x14003bd53  lea     rax, [r11+18h]
0x14003bd57  mov     qword ptr [r11+20h], 0
0x14003bd5f  add     r8, 24h ; '$'; struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *
0x14003bd63  mov     [r11-28h], rax
0x14003bd67  lea     r9, [r11+20h]; struct DOT11_PMKID_LIST **
0x14003bd6b  mov     [rsp+48h+arg_10], 0
0x14003bd73  mov     r14, rdx
0x14003bd76  mov     rdi, rcx
0x14003bd79  xor     ebp, ebp
0x14003bd7b  call    ?Dot11GetPmkidList@@YAJPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAUDOT11_PMKID_CANDIDATE_LIST_PARAMETERS@@PEAPEAUDOT11_PMKID_LIST@@PEAK@Z; Dot11GetPmkidList(_VELAN *,_NWIFI_LOCK_STATE *,DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *,DOT11_PMKID_LIST * *,ulong *)
0x14003bd80  mov     rbx, [rsp+48h+arg_18]
0x14003bd85  mov     esi, eax
0x14003bd87  test    eax, eax
0x14003bd89  jnz     short loc_14003BDD6
0x14003bd8b  mov     rcx, [rdi+90h]; Lock
0x14003bd92  mov     rdx, r14; LockState
0x14003bd95  mov     ebp, [rbx+4]
0x14003bd98  call    cs:__imp_NdisReleaseRWLock
0x14003bd9f  nop     dword ptr [rax+rax+00h]
0x14003bda4  mov     r9d, [rsp+48h+arg_10]; unsigned int
0x14003bda9  mov     r8, rbx; struct DOT11_PMKID_LIST *
0x14003bdac  mov     rdx, [rdi+10D0h]; struct DOT11_MAC_STATE_ENTRY *
0x14003bdb3  mov     rcx, rdi; struct _VELAN *
0x14003bdb6  call    ?Dot11SetPmkIdList@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_PMKID_LIST@@K@Z; Dot11SetPmkIdList(_VELAN *,DOT11_MAC_STATE_ENTRY *,DOT11_PMKID_LIST *,ulong)
0x14003bdbb  mov     rcx, [rdi+90h]; Lock
0x14003bdc2  xor     r8d, r8d; Flags
0x14003bdc5  mov     rdx, r14; LockState
0x14003bdc8  mov     esi, eax
0x14003bdca  call    cs:__imp_NdisAcquireRWLockWrite
0x14003bdd1  nop     dword ptr [rax+rax+00h]
0x14003bdd6  test    rbx, rbx
0x14003bdd9  jz      short loc_14003BE0A
0x14003bddb  lea     rcx, [rbx-10h]; P
0x14003bddf  mov     rax, [rcx]
0x14003bde2  test    rax, rax
0x14003bde5  jz      short loc_14003BDFB
0x14003bde7  mov     rdx, rcx; Entry
0x14003bdea  mov     rcx, rax; Lookaside
0x14003bded  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003bdf4  nop     dword ptr [rax+rax+00h]
0x14003bdf9  jmp     short loc_14003BE0A
0x14003bdfb  mov     edx, [rcx+8]; Tag
0x14003bdfe  call    cs:__imp_ExFreePoolWithTag
0x14003be05  nop     dword ptr [rax+rax+00h]
0x14003be0a  test    cs:byte_1400B2804, 10h
0x14003be11  jz      short loc_14003BE2E
0x14003be13  lea     r8, [rdi+1338h]
0x14003be1a  mov     [rsp+48h+var_20], ebp
0x14003be1e  lea     r9, aPmkcachegetpmk; "PMKCacheGetPmkidListCallback [PmkId]"
0x14003be25  mov     [rsp+48h+var_28], esi
0x14003be29  call    McTemplateK0zqq_EtwWriteTransfer
0x14003be2e  mov     rbx, [rsp+48h+arg_0]
0x14003be33  mov     rbp, [rsp+48h+arg_8]
0x14003be38  add     rsp, 30h
0x14003be3c  pop     r14
0x14003be3e  pop     rdi
0x14003be3f  pop     rsi
0x14003be40  retn
```
