# CldSyncRemoveInFlightRanges

- ea: `0x14003e06c`
- end: `0x14003e136`
- name: `CldSyncRemoveInFlightRanges`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003e13c`

## callees

- `0x14001e580`
- `0x14003e06c`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e0c3`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e0c3`
- `FLTMGR!FltReleasePushLockEx` at `0x14003e119`
- `FLTMGR!FltReleasePushLockEx` at `0x14003e119`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e096`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e096`

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
0x14003e06c  mov     [rsp+arg_0], rbx
0x14003e071  mov     [rsp+arg_8], rsi
0x14003e076  push    rdi
0x14003e077  sub     rsp, 20h
0x14003e07b  mov     rax, [rcx]
0x14003e07e  mov     rdi, rdx
0x14003e081  xor     edx, edx
0x14003e083  mov     rcx, [rax]
0x14003e086  mov     ebx, [rcx+1Ch]
0x14003e089  lea     rcx, [rdi+18h]
0x14003e08d  not     ebx
0x14003e08f  and     ebx, 2
0x14003e092  shl     rbx, 0Bh
0x14003e096  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14003e09d  nop     dword ptr [rax+rax+00h]
0x14003e0a2  xor     edx, edx
0x14003e0a4  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14003e0ae  mov     rax, rbx
0x14003e0b1  neg     rax
0x14003e0b4  and     rax, rcx
0x14003e0b7  lea     rcx, [rdi+20h]; Mcb
0x14003e0bb  div     rbx
0x14003e0be  xor     edx, edx; Vbn
0x14003e0c0  mov     r8, rax; SectorCount
0x14003e0c3  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x14003e0ca  nop     dword ptr [rax+rax+00h]
0x14003e0cf  movsxd  rax, dword ptr [rdi+38h]
0x14003e0d3  test    eax, eax
0x14003e0d5  jz      short loc_14003E0F1
0x14003e0d7  mov     rcx, [rdi+40h]; void *
0x14003e0db  lea     r8, [rax+rax*2]
0x14003e0df  shl     r8, 3; Size
0x14003e0e3  xor     edx, edx; Val
0x14003e0e5  call    memset
0x14003e0ea  mov     dword ptr [rdi+3Ch], 0
0x14003e0f1  movsxd  rax, dword ptr [rdi+48h]
0x14003e0f5  test    eax, eax
0x14003e0f7  jz      short loc_14003E113
0x14003e0f9  mov     rcx, [rdi+50h]; void *
0x14003e0fd  lea     r8, [rax+rax*2]
0x14003e101  shl     r8, 3; Size
0x14003e105  xor     edx, edx; Val
0x14003e107  call    memset
0x14003e10c  mov     dword ptr [rdi+4Ch], 0
0x14003e113  xor     edx, edx
0x14003e115  lea     rcx, [rdi+18h]
0x14003e119  call    cs:__imp_FltReleasePushLockEx
0x14003e120  nop     dword ptr [rax+rax+00h]
0x14003e125  mov     rbx, [rsp+28h+arg_0]
0x14003e12a  mov     rsi, [rsp+28h+arg_8]
0x14003e12f  add     rsp, 20h
0x14003e133  pop     rdi
0x14003e134  retn
```
