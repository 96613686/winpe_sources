# lldpCleanupBinding

- ea: `0x140012730`
- end: `0x140012786`
- name: `lldpCleanupBinding`
- size: `86`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400125f0`
- `0x140012710`
- `0x140012790`

## callees

- `0x1400046a4`
- `0x140012730`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012773`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012773`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x140012742`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x140012742`

## pseudocode

```c
void __fastcall lldpCleanupBinding(_QWORD *P)
{
  void *v2; // rcx

  v2 = (void *)P[2];
  if ( v2 )
  {
    NdisCompleteUnbindAdapterEx(v2);
    P[2] = 0;
  }
  if ( *((_BYTE *)P + 32) )
  {
    lldpRemoveBindingFromDriver(P);
    *((_BYTE *)P + 32) = 0;
  }
  *(_BYTE *)P = 0;
  ExFreePoolWithTag(P, 0x50444C4Cu);
}

```

## disassembly

```asm
0x140012730  push    rbx
0x140012732  sub     rsp, 20h
0x140012736  mov     rbx, rcx
0x140012739  mov     rcx, [rcx+10h]; UnbindContext
0x14001273d  test    rcx, rcx
0x140012740  jz      short loc_140012756
0x140012742  call    cs:__imp_NdisCompleteUnbindAdapterEx
0x140012749  nop     dword ptr [rax+rax+00h]
0x14001274e  mov     qword ptr [rbx+10h], 0
0x140012756  cmp     byte ptr [rbx+20h], 0
0x14001275a  jz      short loc_140012768
0x14001275c  mov     rcx, rbx
0x14001275f  call    lldpRemoveBindingFromDriver
0x140012764  mov     byte ptr [rbx+20h], 0
0x140012768  mov     edx, 50444C4Ch; Tag
0x14001276d  mov     byte ptr [rbx], 0
0x140012770  mov     rcx, rbx; P
0x140012773  call    cs:__imp_ExFreePoolWithTag
0x14001277a  nop     dword ptr [rax+rax+00h]
0x14001277f  add     rsp, 20h
0x140012783  pop     rbx
0x140012784  retn
```
