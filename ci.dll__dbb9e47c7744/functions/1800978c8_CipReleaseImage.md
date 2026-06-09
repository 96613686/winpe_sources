# CipReleaseImage

- ea: `0x1800978c8`
- end: `0x18009796d`
- name: `CipReleaseImage`
- size: `165`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180076eac`
- `0x18009b200`
- `0x1800a7c4c`

## callees

- `0x18002c000`
- `0x1800978c8`
- `0x1800985d4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800978d1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800978d1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800978e6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800978e6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18009794e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18009794e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180097939`
- `ntoskrnl!ExFreePoolWithTag` at `0x180097939`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009795a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009795a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x18009790a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x18009790a`

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
      ((void (*)(void))xmmword_18004A630)();
    MincryptFreePolicyInfo(P + 88);
    ExFreePoolWithTag(P, 0);
  }
  ExReleasePushLockExclusiveEx(&CipHvciTreeLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1800978c8  push    rbx
0x1800978ca  sub     rsp, 20h
0x1800978ce  mov     rbx, rcx
0x1800978d1  call    cs:__imp_KeEnterCriticalRegion
0x1800978d8  nop     dword ptr [rax+rax+00h]
0x1800978dd  xor     edx, edx
0x1800978df  lea     rcx, CipHvciTreeLock
0x1800978e6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800978ed  nop     dword ptr [rax+rax+00h]
0x1800978f2  or      eax, 0FFFFFFFFh
0x1800978f5  lock xadd [rbx+40h], eax
0x1800978fa  cmp     eax, 1
0x1800978fd  jnz     short loc_180097945
0x1800978ff  lea     rdx, [rbx+18h]
0x180097903  lea     rcx, CipHvciTree
0x18009790a  call    cs:__imp_RtlAvlRemoveNode
0x180097911  nop     dword ptr [rax+rax+00h]
0x180097916  mov     rcx, [rbx+10h]
0x18009791a  test    rcx, rcx
0x18009791d  jz      short loc_18009792B
0x18009791f  mov     rax, qword ptr cs:xmmword_18004A630
0x180097926  call    _guard_dispatch_icall
0x18009792b  lea     rcx, [rbx+58h]
0x18009792f  call    MincryptFreePolicyInfo
0x180097934  xor     edx, edx; Tag
0x180097936  mov     rcx, rbx; P
0x180097939  call    cs:__imp_ExFreePoolWithTag
0x180097940  nop     dword ptr [rax+rax+00h]
0x180097945  xor     edx, edx
0x180097947  lea     rcx, CipHvciTreeLock
0x18009794e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180097955  nop     dword ptr [rax+rax+00h]
0x18009795a  call    cs:__imp_KeLeaveCriticalRegion
0x180097961  nop     dword ptr [rax+rax+00h]
0x180097966  add     rsp, 20h
0x18009796a  pop     rbx
0x18009796b  retn
```
