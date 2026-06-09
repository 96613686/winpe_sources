# DfscGetCurrentDcContext

- ea: `0x140022118`
- end: `0x1400221c6`
- name: `DfscGetCurrentDcContext`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140016c84`
- `0x1400219c0`
- `0x140021c60`
- `0x140021e28`
- `0x140022b60`
- `0x140022cd8`

## callees

- `0x1400130ec`
- `0x140022118`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002216a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002216a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002215e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002215e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002213f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400221a4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002213f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400221a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002212a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002218f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002212a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002218f`

## pseudocode

```c
PVOID __fastcall DfscGetCurrentDcContext(__int64 a1)
{
  PVOID DpcData; // rbx
  struct _ERESOURCE *p_AlignmentRequirement; // rcx
  struct _ERESOURCE *v5; // rdi

  if ( a1 )
  {
    KeEnterCriticalRegion();
    v5 = (struct _ERESOURCE *)(a1 + 16);
    ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 16), 1u);
    DpcData = *(PVOID *)(a1 + 120);
    if ( DpcData )
      DfscReferenceDcContext(DpcData);
    p_AlignmentRequirement = v5;
  }
  else
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement, 1u);
    DpcData = WPP_MAIN_CB.Dpc.DpcData;
    if ( WPP_MAIN_CB.Dpc.DpcData )
      DfscReferenceDcContext(WPP_MAIN_CB.Dpc.DpcData);
    p_AlignmentRequirement = (struct _ERESOURCE *)&WPP_MAIN_CB.AlignmentRequirement;
  }
  ExReleaseResourceLite(p_AlignmentRequirement);
  KeLeaveCriticalRegion();
  return DpcData;
}

```

## disassembly

```asm
0x140022118  mov     [rsp+arg_0], rbx
0x14002211d  push    rdi
0x14002211e  sub     rsp, 20h
0x140022122  mov     rbx, rcx
0x140022125  test    rcx, rcx
0x140022128  jnz     short loc_14002218F
0x14002212a  call    cs:__imp_KeEnterCriticalRegion
0x140022131  nop     dword ptr [rax+rax+00h]
0x140022136  mov     dl, 1; Wait
0x140022138  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14002213f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140022146  nop     dword ptr [rax+rax+00h]
0x14002214b  mov     rbx, cs:WPP_MAIN_CB.Dpc.DpcData
0x140022152  test    rbx, rbx
0x140022155  jnz     short loc_140022185
0x140022157  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14002215e  call    cs:__imp_ExReleaseResourceLite
0x140022165  nop     dword ptr [rax+rax+00h]
0x14002216a  call    cs:__imp_KeLeaveCriticalRegion
0x140022171  nop     dword ptr [rax+rax+00h]
0x140022176  mov     rax, rbx
0x140022179  mov     rbx, [rsp+28h+arg_0]
0x14002217e  add     rsp, 20h
0x140022182  pop     rdi
0x140022183  retn
0x140022185  mov     rcx, rbx
0x140022188  call    DfscReferenceDcContext
0x14002218d  jmp     short loc_140022157
0x14002218f  call    cs:__imp_KeEnterCriticalRegion
0x140022196  nop     dword ptr [rax+rax+00h]
0x14002219b  lea     rdi, [rbx+10h]
0x14002219f  mov     dl, 1; Wait
0x1400221a1  mov     rcx, rdi; Resource
0x1400221a4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400221ab  nop     dword ptr [rax+rax+00h]
0x1400221b0  mov     rbx, [rbx+78h]
0x1400221b4  test    rbx, rbx
0x1400221b7  jz      short loc_1400221C1
0x1400221b9  mov     rcx, rbx
0x1400221bc  call    DfscReferenceDcContext
0x1400221c1  mov     rcx, rdi
0x1400221c4  jmp     short loc_14002215E
```
