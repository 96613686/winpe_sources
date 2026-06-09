# LuafvTerminatePool

- ea: `0x140016cb8`
- end: `0x140016d3d`
- name: `LuafvTerminatePool`
- size: `133`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140016670`

## callees

- `0x140016cb8`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016cda`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016ced`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d0c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016cda`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016ced`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140016d0c`
- `FLTMGR!FltReleasePushLockEx` at `0x140016d2a`
- `FLTMGR!FltReleasePushLockEx` at `0x140016d2a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140016cc7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140016cc7`

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
0x140016cb8  push    rbx
0x140016cba  sub     rsp, 20h
0x140016cbe  xor     edx, edx
0x140016cc0  lea     rcx, PoolLock
0x140016cc7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140016cce  nop     dword ptr [rax+rax+00h]
0x140016cd3  lea     rcx, StoreFileLookaside; Lookaside
0x140016cda  call    cs:__imp_ExDeletePagedLookasideList
0x140016ce1  nop     dword ptr [rax+rax+00h]
0x140016ce6  lea     rcx, TableNodeLookaside; Lookaside
0x140016ced  call    cs:__imp_ExDeletePagedLookasideList
0x140016cf4  nop     dword ptr [rax+rax+00h]
0x140016cf9  xor     ebx, ebx
0x140016cfb  lea     rax, StringLookaside
0x140016d02  mov     rcx, rbx
0x140016d05  shl     rcx, 7
0x140016d09  add     rcx, rax; Lookaside
0x140016d0c  call    cs:__imp_ExDeletePagedLookasideList
0x140016d13  nop     dword ptr [rax+rax+00h]
0x140016d18  inc     rbx
0x140016d1b  cmp     rbx, 5
0x140016d1f  jnz     short loc_140016CFB
0x140016d21  xor     edx, edx
0x140016d23  lea     rcx, PoolLock
0x140016d2a  call    cs:__imp_FltReleasePushLockEx
0x140016d31  nop     dword ptr [rax+rax+00h]
0x140016d36  add     rsp, 20h
0x140016d3a  pop     rbx
0x140016d3b  retn
```
