# Smb2TeardownResilientHandleDatabase

- ea: `0x140035e9c`
- end: `0x140035ee2`
- name: `Smb2TeardownResilientHandleDatabase`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14002c110`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035ec4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035ec4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035eac`
- `ntoskrnl!ExDeleteResourceLite` at `0x140035eac`

## pseudocode

```c
void __fastcall Smb2TeardownResilientHandleDatabase(__int64 a1)
{
  ExDeleteResourceLite(*(PERESOURCE *)(a1 + 2336));
  ExFreePoolWithTag(*(PVOID *)(a1 + 2336), 0x6D536452u);
  *(_QWORD *)(a1 + 2336) = 0;
}

```

## disassembly

```asm
0x140035e9c  push    rbx
0x140035e9e  sub     rsp, 20h
0x140035ea2  mov     rbx, rcx
0x140035ea5  mov     rcx, [rcx+920h]; Resource
0x140035eac  call    cs:__imp_ExDeleteResourceLite
0x140035eb3  nop     dword ptr [rax+rax+00h]
0x140035eb8  mov     rcx, [rbx+920h]; P
0x140035ebf  mov     edx, 6D536452h; Tag
0x140035ec4  call    cs:__imp_ExFreePoolWithTag
0x140035ecb  nop     dword ptr [rax+rax+00h]
0x140035ed0  mov     qword ptr [rbx+920h], 0
0x140035edb  add     rsp, 20h
0x140035edf  pop     rbx
0x140035ee0  retn
```
