# CldSyncRemoveInFlightRanges

- ea: `0x14003e08c`
- end: `0x14003e156`
- name: `CldSyncRemoveInFlightRanges`
- size: `202`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003e15c`

## callees

- `0x14001e600`
- `0x14003e08c`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e0e3`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e0e3`
- `FLTMGR!FltReleasePushLockEx` at `0x14003e139`
- `FLTMGR!FltReleasePushLockEx` at `0x14003e139`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e0b6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e0b6`

## pseudocode

```c
__int64 __fastcall CldSyncRemoveInFlightRanges(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax

  v3 = (unsigned __int64)(~(unsigned __int8)*(_DWORD *)(**(_QWORD **)a1 + 28LL) & 2) << 11;
  FltAcquirePushLockExclusiveEx(a2 + 24, 0);
  FsRtlRemoveBaseMcbEntry((PBASE_MCB)(a2 + 32), 0, (-(__int64)v3 & 0x7FFFFFFFFFFFFFFFuLL) / v3);
  v4 = *(int *)(a2 + 56);
  if ( (_DWORD)v4 )
  {
    memset(*(void **)(a2 + 64), 0, 24 * v4);
    *(_DWORD *)(a2 + 60) = 0;
  }
  v5 = *(int *)(a2 + 72);
  if ( (_DWORD)v5 )
  {
    memset(*(void **)(a2 + 80), 0, 24 * v5);
    *(_DWORD *)(a2 + 76) = 0;
  }
  return FltReleasePushLockEx(a2 + 24, 0);
}

```

## disassembly

```asm
0x14003e08c  mov     [rsp+arg_0], rbx
0x14003e091  mov     [rsp+arg_8], rsi
0x14003e096  push    rdi
0x14003e097  sub     rsp, 20h
0x14003e09b  mov     rax, [rcx]
0x14003e09e  mov     rdi, rdx
0x14003e0a1  xor     edx, edx
0x14003e0a3  mov     rcx, [rax]
0x14003e0a6  mov     ebx, [rcx+1Ch]
0x14003e0a9  lea     rcx, [rdi+18h]
0x14003e0ad  not     ebx
0x14003e0af  and     ebx, 2
0x14003e0b2  shl     rbx, 0Bh
0x14003e0b6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14003e0bd  nop     dword ptr [rax+rax+00h]
0x14003e0c2  xor     edx, edx
0x14003e0c4  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14003e0ce  mov     rax, rbx
0x14003e0d1  neg     rax
0x14003e0d4  and     rax, rcx
0x14003e0d7  lea     rcx, [rdi+20h]; Mcb
0x14003e0db  div     rbx
0x14003e0de  xor     edx, edx; Vbn
0x14003e0e0  mov     r8, rax; SectorCount
0x14003e0e3  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x14003e0ea  nop     dword ptr [rax+rax+00h]
0x14003e0ef  movsxd  rax, dword ptr [rdi+38h]
0x14003e0f3  test    eax, eax
0x14003e0f5  jz      short loc_14003E111
0x14003e0f7  mov     rcx, [rdi+40h]; void *
0x14003e0fb  lea     r8, [rax+rax*2]
0x14003e0ff  shl     r8, 3; Size
0x14003e103  xor     edx, edx; Val
0x14003e105  call    memset
0x14003e10a  mov     dword ptr [rdi+3Ch], 0
0x14003e111  movsxd  rax, dword ptr [rdi+48h]
0x14003e115  test    eax, eax
0x14003e117  jz      short loc_14003E133
0x14003e119  mov     rcx, [rdi+50h]; void *
0x14003e11d  lea     r8, [rax+rax*2]
0x14003e121  shl     r8, 3; Size
0x14003e125  xor     edx, edx; Val
0x14003e127  call    memset
0x14003e12c  mov     dword ptr [rdi+4Ch], 0
0x14003e133  xor     edx, edx
0x14003e135  lea     rcx, [rdi+18h]
0x14003e139  call    cs:__imp_FltReleasePushLockEx
0x14003e140  nop     dword ptr [rax+rax+00h]
0x14003e145  mov     rbx, [rsp+28h+arg_0]
0x14003e14a  mov     rsi, [rsp+28h+arg_8]
0x14003e14f  add     rsp, 20h
0x14003e153  pop     rdi
0x14003e154  retn
```
