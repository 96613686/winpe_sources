# CipReleaseImage

- ea: `0x18008e098`
- end: `0x18008e13d`
- name: `CipReleaseImage`
- size: `165`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007718c`
- `0x1800a0540`
- `0x1800a3148`

## callees

- `0x18002c1b0`
- `0x18008e098`
- `0x18008eda4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18008e0a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008e0a1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18008e0b6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18008e0b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18008e11e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18008e11e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008e109`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008e109`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008e12a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008e12a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x18008e0da`
- `ntoskrnl!RtlAvlRemoveNode` at `0x18008e0da`

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
      ((void (*)(void))xmmword_18004A5D0)();
    MincryptFreePolicyInfo(P + 88);
    ExFreePoolWithTag(P, 0);
  }
  ExReleasePushLockExclusiveEx(&CipHvciTreeLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x18008e098  push    rbx
0x18008e09a  sub     rsp, 20h
0x18008e09e  mov     rbx, rcx
0x18008e0a1  call    cs:__imp_KeEnterCriticalRegion
0x18008e0a8  nop     dword ptr [rax+rax+00h]
0x18008e0ad  xor     edx, edx
0x18008e0af  lea     rcx, CipHvciTreeLock
0x18008e0b6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18008e0bd  nop     dword ptr [rax+rax+00h]
0x18008e0c2  or      eax, 0FFFFFFFFh
0x18008e0c5  lock xadd [rbx+40h], eax
0x18008e0ca  cmp     eax, 1
0x18008e0cd  jnz     short loc_18008E115
0x18008e0cf  lea     rdx, [rbx+18h]
0x18008e0d3  lea     rcx, CipHvciTree
0x18008e0da  call    cs:__imp_RtlAvlRemoveNode
0x18008e0e1  nop     dword ptr [rax+rax+00h]
0x18008e0e6  mov     rcx, [rbx+10h]
0x18008e0ea  test    rcx, rcx
0x18008e0ed  jz      short loc_18008E0FB
0x18008e0ef  mov     rax, qword ptr cs:xmmword_18004A5D0
0x18008e0f6  call    _guard_dispatch_icall
0x18008e0fb  lea     rcx, [rbx+58h]
0x18008e0ff  call    MincryptFreePolicyInfo
0x18008e104  xor     edx, edx; Tag
0x18008e106  mov     rcx, rbx; P
0x18008e109  call    cs:__imp_ExFreePoolWithTag
0x18008e110  nop     dword ptr [rax+rax+00h]
0x18008e115  xor     edx, edx
0x18008e117  lea     rcx, CipHvciTreeLock
0x18008e11e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18008e125  nop     dword ptr [rax+rax+00h]
0x18008e12a  call    cs:__imp_KeLeaveCriticalRegion
0x18008e131  nop     dword ptr [rax+rax+00h]
0x18008e136  add     rsp, 20h
0x18008e13a  pop     rbx
0x18008e13b  retn
```
