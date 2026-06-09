# DfscCredTableFree

- ea: `0x140012534`
- end: `0x14001256e`
- name: `DfscCredTableFree`
- size: `58`
- prototype: `void __fastcall(struct _ERESOURCE *P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140012930`
- `0x140019ec0`

## callees

- `0x140012534`
- `0x140012668`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001255b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001255b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001254a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001254a`

## pseudocode

```c
void __fastcall DfscCredTableFree(struct _ERESOURCE *P)
{
  if ( P )
  {
    DfscCredTablePurge((ULONG_PTR)P);
    ExDeleteResourceLite(P + 1);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140012534  test    rcx, rcx
0x140012537  jz      short locret_14001256C
0x140012539  push    rbx
0x14001253a  sub     rsp, 20h
0x14001253e  mov     rbx, rcx
0x140012541  call    DfscCredTablePurge
0x140012546  lea     rcx, [rbx+68h]; Resource
0x14001254a  call    cs:__imp_ExDeleteResourceLite
0x140012551  nop     dword ptr [rax+rax+00h]
0x140012556  xor     edx, edx; Tag
0x140012558  mov     rcx, rbx; P
0x14001255b  call    cs:__imp_ExFreePoolWithTag
0x140012562  nop     dword ptr [rax+rax+00h]
0x140012567  add     rsp, 20h
0x14001256b  pop     rbx
0x14001256c  retn
```
