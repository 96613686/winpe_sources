# FltpDisableNameCachePurgeForTxRename

- ea: `0x1800612f0`
- end: `0x18006149f`
- name: `FltpDisableNameCachePurgeForTxRename`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180061190`

## callees

- `0x18000d270`
- `0x18000f5b0`
- `0x1800139a0`
- `0x180060e10`
- `0x1800612f0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x180061308`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180061378`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180061308`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180061378`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18006136c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800613b8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800613ee`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180061465`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18006136c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800613b8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1800613ee`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180061465`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180061483`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180061483`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18006138d`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18006138d`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800613ac`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180061459`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1800613ac`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180061459`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x18006131d`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x18006131d`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180061360`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1800613e2`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x180061360`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1800613e2`

## pseudocode

```c
void __fastcall FltpDisableNameCachePurgeForTxRename(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r9
  _DWORD *v9; // rbx
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // rax
  void *v13; // rdi
  unsigned int v14; // edx
  unsigned int v15; // edx

  KeEnterGuardedRegion();
  v6 = ExAcquireAutoExpandPushLockShared(a2 + 2040, 0);
  v7 = TreeLookup(a2 + 2056, a1, -1, v6);
  if ( v7 )
  {
    v9 = (_DWORD *)(v7 - 88);
    _InterlockedIncrement((volatile signed __int32 *)(v7 - 88 + 144));
    ExReleaseAutoExpandPushLockShared(v8, 0);
    KeLeaveGuardedRegion();
    KeEnterGuardedRegion();
    ExAcquireAutoExpandPushLockExclusive(v9 + 40, 0);
    if ( (v9[37] & 0x30) == 0 )
    {
      v11 = *(_DWORD *)(a3 + 64);
      if ( (v11 & 0x20) != 0 )
      {
        --v9[38];
      }
      else if ( (v11 & 0x10) != 0 )
      {
        v12 = TreeLookup(v9 + 44, a3, -1, v10);
        v13 = (void *)v12;
        if ( v12 )
        {
          v14 = *(_DWORD *)(v12 + 64);
          if ( v14 < 0x7FFFFFFF )
          {
            v15 = v14 - 1;
            *(_DWORD *)(v12 + 64) = v15;
            if ( !v15 )
            {
              TreeUnlink(v12);
              ExReleaseAutoExpandPushLockExclusive(v9 + 40, 0);
              KeLeaveGuardedRegion();
              FltpReleaseStreamListCtrl((char *)a3);
              ExFreeToPagedLookasideList(&stru_18003F140, v13);
              goto LABEL_4;
            }
          }
        }
      }
    }
    ExReleaseAutoExpandPushLockExclusive(v9 + 40, 0);
    KeLeaveGuardedRegion();
LABEL_4:
    FltpReleaseTxVolContext(v9);
    return;
  }
  ExReleaseAutoExpandPushLockShared(v8, 0);
  KeLeaveGuardedRegion();
}

```

## disassembly

```asm
0x1800612f0  mov     [rsp+arg_8], rbx
0x1800612f5  mov     [rsp+arg_10], rsi
0x1800612fa  push    rdi
0x1800612fb  sub     rsp, 20h
0x1800612ff  mov     rsi, r8
0x180061302  mov     rbx, rdx
0x180061305  mov     rdi, rcx
0x180061308  call    cs:__imp_KeEnterGuardedRegion
0x18006130f  nop     dword ptr [rax+rax+00h]
0x180061314  lea     rcx, [rbx+7F8h]
0x18006131b  xor     edx, edx
0x18006131d  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x180061324  nop     dword ptr [rax+rax+00h]
0x180061329  lea     rcx, [rbx+808h]
0x180061330  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180061337  mov     rdx, rdi
0x18006133a  mov     r9, rax
0x18006133d  call    TreeLookup
0x180061342  xor     edx, edx
0x180061344  mov     rcx, r9
0x180061347  test    rax, rax
0x18006134a  jz      loc_1800613E2
0x180061350  mov     [rsp+28h+arg_0], rbp
0x180061355  lea     rbx, [rax-58h]
0x180061359  lock inc dword ptr [rbx+90h]
0x180061360  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x180061367  nop     dword ptr [rax+rax+00h]
0x18006136c  call    cs:__imp_KeLeaveGuardedRegion
0x180061373  nop     dword ptr [rax+rax+00h]
0x180061378  call    cs:__imp_KeEnterGuardedRegion
0x18006137f  nop     dword ptr [rax+rax+00h]
0x180061384  xor     edx, edx
0x180061386  lea     rcx, [rbx+0A0h]
0x18006138d  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x180061394  nop     dword ptr [rax+rax+00h]
0x180061399  mov     eax, [rbx+94h]
0x18006139f  test    al, 30h
0x1800613a1  jz      short loc_1800613FC
0x1800613a3  xor     edx, edx
0x1800613a5  lea     rcx, [rbx+0A0h]
0x1800613ac  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1800613b3  nop     dword ptr [rax+rax+00h]
0x1800613b8  call    cs:__imp_KeLeaveGuardedRegion
0x1800613bf  nop     dword ptr [rax+rax+00h]
0x1800613c4  mov     rcx, rbx; Entry
0x1800613c7  call    FltpReleaseTxVolContext
0x1800613cc  mov     rbp, [rsp+28h+arg_0]
0x1800613d1  mov     rbx, [rsp+28h+arg_8]
0x1800613d6  mov     rsi, [rsp+28h+arg_10]
0x1800613db  add     rsp, 20h
0x1800613df  pop     rdi
0x1800613e0  retn
0x1800613e2  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1800613e9  nop     dword ptr [rax+rax+00h]
0x1800613ee  call    cs:__imp_KeLeaveGuardedRegion
0x1800613f5  nop     dword ptr [rax+rax+00h]
0x1800613fa  jmp     short loc_1800613D1
0x1800613fc  mov     eax, [rsi+40h]
0x1800613ff  test    al, 20h
0x180061401  jnz     loc_180061494
0x180061407  test    al, 10h
0x180061409  jz      short loc_1800613A3
0x18006140b  lea     rcx, [rbx+0B0h]
0x180061412  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180061419  mov     rdx, rsi
0x18006141c  call    TreeLookup
0x180061421  mov     rdi, rax
0x180061424  test    rax, rax
0x180061427  jz      loc_1800613A3
0x18006142d  mov     edx, [rax+40h]
0x180061430  cmp     edx, 7FFFFFFFh
0x180061436  jnb     loc_1800613A3
0x18006143c  sub     edx, 1
0x18006143f  mov     [rax+40h], edx
0x180061442  jnz     loc_1800613A3
0x180061448  mov     rcx, rax
0x18006144b  call    TreeUnlink
0x180061450  xor     edx, edx
0x180061452  lea     rcx, [rbx+0A0h]
0x180061459  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180061460  nop     dword ptr [rax+rax+00h]
0x180061465  call    cs:__imp_KeLeaveGuardedRegion
0x18006146c  nop     dword ptr [rax+rax+00h]
0x180061471  mov     rcx, rsi; Entry
0x180061474  call    FltpReleaseStreamListCtrl
0x180061479  mov     rdx, rdi; Entry
0x18006147c  lea     rcx, stru_18003F140; Lookaside
0x180061483  call    cs:__imp_ExFreeToPagedLookasideList
0x18006148a  nop     dword ptr [rax+rax+00h]
0x18006148f  jmp     loc_1800613C4
0x180061494  dec     dword ptr [rbx+98h]
0x18006149a  jmp     loc_1800613A3
```
