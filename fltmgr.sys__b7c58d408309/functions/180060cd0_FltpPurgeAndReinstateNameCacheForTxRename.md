# FltpPurgeAndReinstateNameCacheForTxRename

- ea: `0x180060cd0`
- end: `0x180060dfb`
- name: `FltpPurgeAndReinstateNameCacheForTxRename`
- size: `299`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18004e990`

## callees

- `0x18000f5b0`
- `0x180012d80`
- `0x18001ad40`
- `0x18001e390`
- `0x180060cd0`
- `0x1800614b0`
- `0x180061760`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x180060ce2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180060ce2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180060d42`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180060ded`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180060d42`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180060ded`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180060d94`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180060d94`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180060cfa`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x180060cfa`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180060d36`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180060de1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180060d36`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180060de1`

## pseudocode

```c
void __fastcall FltpPurgeAndReinstateNameCacheForTxRename(__int64 a1)
{
  __int64 v2; // r9
  __int64 *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rbx
  int v7; // r9d
  _QWORD *v8; // rdi

  KeEnterGuardedRegion();
  ExAcquireAutoExpandPushLockExclusive(a1 + 160, 0);
  v3 = (__int64 *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 148) & 0x20) == 0
    || (FltpPurgeVolumeNameCache(*v3, 0, 0), FltpEnableNameCachingForVolume(*v3), (*(_DWORD *)(a1 + 148) & 0x10) != 0) )
  {
    v4 = TreeUnlinkMulti((_QWORD *)(a1 + 176), 0xFFFFFFFFFFFFFFFFuLL, -1, v2);
    v5 = a1 + 160;
    v6 = (_QWORD *)v4;
    ExReleaseAutoExpandPushLockExclusive(v5, 0);
    KeLeaveGuardedRegion();
    if ( v6 )
    {
      do
      {
        v8 = (_QWORD *)v6[2];
        PurgeStreamNameCache(*v3, v6[7], 0, v7, 0);
        FltpEnableNameCachingForStream(v6[7]);
        FltpReleaseStreamListCtrl((char *)v6[7]);
        ExFreeToPagedLookasideList(&stru_18003F140, v6);
        v6 = v8;
      }
      while ( v8 );
    }
  }
  else
  {
    ExReleaseAutoExpandPushLockExclusive(a1 + 160, 0);
    KeLeaveGuardedRegion();
  }
}

```

## disassembly

```asm
0x180060cd0  mov     [rsp+arg_0], rbx
0x180060cd5  mov     [rsp+arg_8], rsi
0x180060cda  push    rdi
0x180060cdb  sub     rsp, 30h
0x180060cdf  mov     rbx, rcx
0x180060ce2  call    cs:__imp_KeEnterGuardedRegion
0x180060ce9  nop     dword ptr [rax+rax+00h]
0x180060cee  lea     rdi, [rbx+0A0h]
0x180060cf5  xor     edx, edx
0x180060cf7  mov     rcx, rdi
0x180060cfa  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x180060d01  nop     dword ptr [rax+rax+00h]
0x180060d06  mov     eax, [rbx+94h]
0x180060d0c  lea     rsi, [rbx+8]
0x180060d10  test    al, 20h
0x180060d12  jnz     loc_180060DB9
0x180060d18  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180060d1f  lea     rcx, [rbx+0B0h]
0x180060d26  mov     r8, rdx
0x180060d29  call    TreeUnlinkMulti
0x180060d2e  xor     edx, edx
0x180060d30  mov     rcx, rdi
0x180060d33  mov     rbx, rax
0x180060d36  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180060d3d  nop     dword ptr [rax+rax+00h]
0x180060d42  call    cs:__imp_KeLeaveGuardedRegion
0x180060d49  nop     dword ptr [rax+rax+00h]
0x180060d4e  test    rbx, rbx
0x180060d51  jz      short loc_180060DA8
0x180060d53  nop     dword ptr [rax+00h]
0x180060d57  nop     word ptr [rax+rax+00000000h]
0x180060d60  mov     rdx, [rbx+38h]
0x180060d64  xor     r8d, r8d
0x180060d67  mov     rcx, [rsi]
0x180060d6a  mov     rdi, [rbx+10h]
0x180060d6e  mov     [rsp+38h+var_18], 0
0x180060d73  call    PurgeStreamNameCache
0x180060d78  mov     rcx, [rbx+38h]
0x180060d7c  call    FltpEnableNameCachingForStream
0x180060d81  mov     rcx, [rbx+38h]; Entry
0x180060d85  call    FltpReleaseStreamListCtrl
0x180060d8a  mov     rdx, rbx; Entry
0x180060d8d  lea     rcx, stru_18003F140; Lookaside
0x180060d94  call    cs:__imp_ExFreeToPagedLookasideList
0x180060d9b  nop     dword ptr [rax+rax+00h]
0x180060da0  mov     rbx, rdi
0x180060da3  test    rdi, rdi
0x180060da6  jnz     short loc_180060D60
0x180060da8  mov     rbx, [rsp+38h+arg_0]
0x180060dad  mov     rsi, [rsp+38h+arg_8]
0x180060db2  add     rsp, 30h
0x180060db6  pop     rdi
0x180060db7  retn
0x180060db9  mov     rcx, [rsi]
0x180060dbc  xor     r8d, r8d
0x180060dbf  xor     edx, edx
0x180060dc1  call    FltpPurgeVolumeNameCache
0x180060dc6  mov     rcx, [rsi]
0x180060dc9  call    FltpEnableNameCachingForVolume
0x180060dce  mov     eax, [rbx+94h]
0x180060dd4  test    al, 10h
0x180060dd6  jnz     loc_180060D18
0x180060ddc  xor     edx, edx
0x180060dde  mov     rcx, rdi
0x180060de1  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x180060de8  nop     dword ptr [rax+rax+00h]
0x180060ded  call    cs:__imp_KeLeaveGuardedRegion
0x180060df4  nop     dword ptr [rax+rax+00h]
0x180060df9  jmp     short loc_180060DA8
```
