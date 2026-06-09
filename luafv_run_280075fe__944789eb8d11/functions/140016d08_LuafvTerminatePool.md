# LuafvTerminatePool

- ea: `0x140016d08`
- end: `0x140016d8d`
- name: `LuafvTerminatePool`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140016670`

## callees

- `0x140016d08`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d2a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d3d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d5c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d2a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d3d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d5c`
- `FLTMGR!FltReleasePushLockEx` at `0x140016d7a`
- `FLTMGR!FltReleasePushLockEx` at `0x140016d7a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140016d17`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140016d17`

## pseudocode

```c
__int64 LuafvTerminatePool()
{
  __int64 i; // rbx

  FltAcquirePushLockExclusiveEx(&PoolLock, 0);
  ExDeletePagedLookasideList(&StoreFileLookaside);
  ExDeletePagedLookasideList(&TableNodeLookaside);
  for ( i = 0; i != 5; ++i )
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)&StringLookaside[16 * i]);
  return FltReleasePushLockEx(&PoolLock, 0);
}

```

## disassembly

```asm
0x140016d08  push    rbx
0x140016d0a  sub     rsp, 20h
0x140016d0e  xor     edx, edx
0x140016d10  lea     rcx, PoolLock
0x140016d17  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140016d1e  nop     dword ptr [rax+rax+00h]
0x140016d23  lea     rcx, StoreFileLookaside; Lookaside
0x140016d2a  call    cs:__imp_ExDeletePagedLookasideList
0x140016d31  nop     dword ptr [rax+rax+00h]
0x140016d36  lea     rcx, TableNodeLookaside; Lookaside
0x140016d3d  call    cs:__imp_ExDeletePagedLookasideList
0x140016d44  nop     dword ptr [rax+rax+00h]
0x140016d49  xor     ebx, ebx
0x140016d4b  lea     rax, StringLookaside
0x140016d52  mov     rcx, rbx
0x140016d55  shl     rcx, 7
0x140016d59  add     rcx, rax; Lookaside
0x140016d5c  call    cs:__imp_ExDeletePagedLookasideList
0x140016d63  nop     dword ptr [rax+rax+00h]
0x140016d68  inc     rbx
0x140016d6b  cmp     rbx, 5
0x140016d6f  jnz     short loc_140016D4B
0x140016d71  xor     edx, edx
0x140016d73  lea     rcx, PoolLock
0x140016d7a  call    cs:__imp_FltReleasePushLockEx
0x140016d81  nop     dword ptr [rax+rax+00h]
0x140016d86  add     rsp, 20h
0x140016d8a  pop     rbx
0x140016d8b  retn
```
