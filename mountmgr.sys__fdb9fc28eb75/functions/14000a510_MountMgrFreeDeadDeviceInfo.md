# MountMgrFreeDeadDeviceInfo

- ea: `0x14000a510`
- end: `0x14000a543`
- name: `MountMgrFreeDeadDeviceInfo`
- size: `51`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a050`
- `0x14000d7a0`
- `0x1400147a0`
- `0x140014fc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a51f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a530`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a51f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a530`

## pseudocode

```c
void __fastcall MountMgrFreeDeadDeviceInfo(PVOID *P)
{
  ExFreePoolWithTag(P[9], 0);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000a510  push    rbx
0x14000a512  sub     rsp, 20h
0x14000a516  mov     rbx, rcx
0x14000a519  xor     edx, edx; Tag
0x14000a51b  mov     rcx, [rcx+48h]; P
0x14000a51f  call    cs:__imp_ExFreePoolWithTag
0x14000a526  nop     dword ptr [rax+rax+00h]
0x14000a52b  xor     edx, edx; Tag
0x14000a52d  mov     rcx, rbx; P
0x14000a530  call    cs:__imp_ExFreePoolWithTag
0x14000a537  nop     dword ptr [rax+rax+00h]
0x14000a53c  add     rsp, 20h
0x14000a540  pop     rbx
0x14000a541  retn
```
