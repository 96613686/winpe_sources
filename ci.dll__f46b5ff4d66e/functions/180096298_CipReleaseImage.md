# CipReleaseImage

- ea: `0x180096298`
- end: `0x18009633d`
- name: `CipReleaseImage`
- size: `165`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800758fc`
- `0x180099bd0`
- `0x1800a67cc`

## callees

- `0x18002bfd0`
- `0x180096298`
- `0x180096fa4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800962a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800962a1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800962b6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800962b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18009631e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18009631e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180096309`
- `ntoskrnl!ExFreePoolWithTag` at `0x180096309`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009632a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009632a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1800962da`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1800962da`

## pseudocode

```c
void __fastcall CipReleaseImage(char *P)
{
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&CipHvciTreeLock, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 16, 0xFFFFFFFF) == 1 )
  {
    RtlAvlRemoveNode(&CipHvciTree, P + 24);
    if ( *((_QWORD *)P + 2) )
      ((void (*)(void))xmmword_1800495D0)();
    MincryptFreePolicyInfo(P + 88);
    ExFreePoolWithTag(P, 0);
  }
  ExReleasePushLockExclusiveEx(&CipHvciTreeLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x180096298  push    rbx
0x18009629a  sub     rsp, 20h
0x18009629e  mov     rbx, rcx
0x1800962a1  call    cs:__imp_KeEnterCriticalRegion
0x1800962a8  nop     dword ptr [rax+rax+00h]
0x1800962ad  xor     edx, edx
0x1800962af  lea     rcx, CipHvciTreeLock
0x1800962b6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800962bd  nop     dword ptr [rax+rax+00h]
0x1800962c2  or      eax, 0FFFFFFFFh
0x1800962c5  lock xadd [rbx+40h], eax
0x1800962ca  cmp     eax, 1
0x1800962cd  jnz     short loc_180096315
0x1800962cf  lea     rdx, [rbx+18h]
0x1800962d3  lea     rcx, CipHvciTree
0x1800962da  call    cs:__imp_RtlAvlRemoveNode
0x1800962e1  nop     dword ptr [rax+rax+00h]
0x1800962e6  mov     rcx, [rbx+10h]
0x1800962ea  test    rcx, rcx
0x1800962ed  jz      short loc_1800962FB
0x1800962ef  mov     rax, qword ptr cs:xmmword_1800495D0
0x1800962f6  call    _guard_dispatch_icall
0x1800962fb  lea     rcx, [rbx+58h]
0x1800962ff  call    MincryptFreePolicyInfo
0x180096304  xor     edx, edx; Tag
0x180096306  mov     rcx, rbx; P
0x180096309  call    cs:__imp_ExFreePoolWithTag
0x180096310  nop     dword ptr [rax+rax+00h]
0x180096315  xor     edx, edx
0x180096317  lea     rcx, CipHvciTreeLock
0x18009631e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180096325  nop     dword ptr [rax+rax+00h]
0x18009632a  call    cs:__imp_KeLeaveCriticalRegion
0x180096331  nop     dword ptr [rax+rax+00h]
0x180096336  add     rsp, 20h
0x18009633a  pop     rbx
0x18009633b  retn
```
