# PMKCacheGetPmkidListCallback(_VELAN *,_NWIFI_LOCK_STATE *,void *)

- ea: `0x14003bb20`
- end: `0x14003bc22`
- name: `?PMKCacheGetPmkidListCallback@@YAXPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAX@Z`
- size: `258`
- prototype: `void __fastcall(struct _VELAN *, PLOCK_STATE_EX LockState, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14000ad38`
- `0x14003b6f8`
- `0x14003b8f4`
- `0x14003bb20`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bbcd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bbcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bbde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bbde`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003bbaa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003bbaa`
- `NDIS!NdisReleaseRWLock` at `0x14003bb78`
- `NDIS!NdisReleaseRWLock` at `0x14003bb78`

## string_xrefs

- `0x14003bbfe`: `PMKCacheGetPmkidListCallback [PmkId]`

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
  if ( (byte_1400AF804 & 0x10) != 0 )
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
0x14003bb20  mov     r11, rsp
0x14003bb23  mov     [r11+8], rbx
0x14003bb27  mov     [r11+10h], rbp
0x14003bb2b  push    rsi
0x14003bb2c  push    rdi
0x14003bb2d  push    r14
0x14003bb2f  sub     rsp, 30h
0x14003bb33  lea     rax, [r11+18h]
0x14003bb37  mov     qword ptr [r11+20h], 0
0x14003bb3f  add     r8, 24h ; '$'; struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *
0x14003bb43  mov     [r11-28h], rax
0x14003bb47  lea     r9, [r11+20h]; struct DOT11_PMKID_LIST **
0x14003bb4b  mov     [rsp+48h+arg_10], 0
0x14003bb53  mov     r14, rdx
0x14003bb56  mov     rdi, rcx
0x14003bb59  xor     ebp, ebp
0x14003bb5b  call    ?Dot11GetPmkidList@@YAJPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAUDOT11_PMKID_CANDIDATE_LIST_PARAMETERS@@PEAPEAUDOT11_PMKID_LIST@@PEAK@Z; Dot11GetPmkidList(_VELAN *,_NWIFI_LOCK_STATE *,DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *,DOT11_PMKID_LIST * *,ulong *)
0x14003bb60  mov     rbx, [rsp+48h+arg_18]
0x14003bb65  mov     esi, eax
0x14003bb67  test    eax, eax
0x14003bb69  jnz     short loc_14003BBB6
0x14003bb6b  mov     rcx, [rdi+90h]; Lock
0x14003bb72  mov     rdx, r14; LockState
0x14003bb75  mov     ebp, [rbx+4]
0x14003bb78  call    cs:__imp_NdisReleaseRWLock
0x14003bb7f  nop     dword ptr [rax+rax+00h]
0x14003bb84  mov     r9d, [rsp+48h+arg_10]; unsigned int
0x14003bb89  mov     r8, rbx; struct DOT11_PMKID_LIST *
0x14003bb8c  mov     rdx, [rdi+10D0h]; struct DOT11_MAC_STATE_ENTRY *
0x14003bb93  mov     rcx, rdi; struct _VELAN *
0x14003bb96  call    ?Dot11SetPmkIdList@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_PMKID_LIST@@K@Z; Dot11SetPmkIdList(_VELAN *,DOT11_MAC_STATE_ENTRY *,DOT11_PMKID_LIST *,ulong)
0x14003bb9b  mov     rcx, [rdi+90h]; Lock
0x14003bba2  xor     r8d, r8d; Flags
0x14003bba5  mov     rdx, r14; LockState
0x14003bba8  mov     esi, eax
0x14003bbaa  call    cs:__imp_NdisAcquireRWLockWrite
0x14003bbb1  nop     dword ptr [rax+rax+00h]
0x14003bbb6  test    rbx, rbx
0x14003bbb9  jz      short loc_14003BBEA
0x14003bbbb  lea     rcx, [rbx-10h]; P
0x14003bbbf  mov     rax, [rcx]
0x14003bbc2  test    rax, rax
0x14003bbc5  jz      short loc_14003BBDB
0x14003bbc7  mov     rdx, rcx; Entry
0x14003bbca  mov     rcx, rax; Lookaside
0x14003bbcd  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003bbd4  nop     dword ptr [rax+rax+00h]
0x14003bbd9  jmp     short loc_14003BBEA
0x14003bbdb  mov     edx, [rcx+8]; Tag
0x14003bbde  call    cs:__imp_ExFreePoolWithTag
0x14003bbe5  nop     dword ptr [rax+rax+00h]
0x14003bbea  test    cs:byte_1400AF804, 10h
0x14003bbf1  jz      short loc_14003BC0E
0x14003bbf3  lea     r8, [rdi+1338h]
0x14003bbfa  mov     [rsp+48h+var_20], ebp
0x14003bbfe  lea     r9, aPmkcachegetpmk; "PMKCacheGetPmkidListCallback [PmkId]"
0x14003bc05  mov     [rsp+48h+var_28], esi
0x14003bc09  call    McTemplateK0zqq_EtwWriteTransfer
0x14003bc0e  mov     rbx, [rsp+48h+arg_0]
0x14003bc13  mov     rbp, [rsp+48h+arg_8]
0x14003bc18  add     rsp, 30h
0x14003bc1c  pop     r14
0x14003bc1e  pop     rdi
0x14003bc1f  pop     rsi
0x14003bc20  retn
```
