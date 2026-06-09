# DiscpFreeTargetPortal

- ea: `0x1800068cc`
- end: `0x180006906`
- name: `DiscpFreeTargetPortal`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b20`
- `0x18000e040`
- `0x18000eeb0`
- `0x18000f310`

## callees

- `0x1800068cc`
- `0x180007a94`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x1800068e9`
- `ISCSIUM!DiscpFreeMemory` at `0x1800068e9`
- `ISCSIUM!DiscpFreeMemory` at `0x1800068ff`

## pseudocode

```c
__int64 __fastcall DiscpFreeTargetPortal(__int64 a1)
{
  __int64 v2; // rcx

  if ( (*(_BYTE *)(a1 + 20) & 1) != 0 )
    DiscpRemoveTargetPortalFromList();
  v2 = *(_QWORD *)(a1 + 72);
  if ( v2 )
  {
    DiscpFreeMemory(v2);
    *(_QWORD *)(a1 + 72) = 0;
  }
  return DiscpFreeMemory(a1);
}

```

## disassembly

```asm
0x1800068cc  push    rbx
0x1800068ce  sub     rsp, 20h
0x1800068d2  test    byte ptr [rcx+14h], 1
0x1800068d6  mov     rbx, rcx
0x1800068d9  jz      short loc_1800068E0
0x1800068db  call    DiscpRemoveTargetPortalFromList
0x1800068e0  mov     rcx, [rbx+48h]
0x1800068e4  test    rcx, rcx
0x1800068e7  jz      short loc_1800068F7
0x1800068e9  call    cs:__imp_DiscpFreeMemory
0x1800068ef  mov     qword ptr [rbx+48h], 0
0x1800068f7  mov     rcx, rbx
0x1800068fa  add     rsp, 20h
0x1800068fe  pop     rbx
0x1800068ff  jmp     cs:__imp_DiscpFreeMemory
```
