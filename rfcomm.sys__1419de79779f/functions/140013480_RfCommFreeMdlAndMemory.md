# RfCommFreeMdlAndMemory

- ea: `0x140013480`
- end: `0x1400134ed`
- name: `RfCommFreeMdlAndMemory`
- size: `109`
- prototype: `void __fastcall(PMDL Mdl)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400134f4`

## callees

- `0x140013480`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400134c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400134c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400134ae`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400134ae`
- `ntoskrnl!IoFreeMdl` at `0x1400134da`
- `ntoskrnl!IoFreeMdl` at `0x1400134da`

## pseudocode

```c
void __fastcall RfCommFreeMdlAndMemory(PMDL Mdl)
{
  void *MappedSystemVa; // rax

  if ( (Mdl->MdlFlags & 5) != 0 )
    MappedSystemVa = Mdl->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
    ExFreePoolWithTag(MappedSystemVa, 0);
  Mdl->Next = 0;
  IoFreeMdl(Mdl);
}

```

## disassembly

```asm
0x140013480  push    rbx
0x140013482  sub     rsp, 30h
0x140013486  test    byte ptr [rcx+0Ah], 5
0x14001348a  mov     rbx, rcx
0x14001348d  jz      short loc_140013495
0x14001348f  mov     rax, [rcx+18h]
0x140013493  jmp     short loc_1400134BA
0x140013495  xor     r9d, r9d; RequestedAddress
0x140013498  mov     [rsp+38h+Priority], 40000010h; Priority
0x1400134a0  xor     edx, edx; AccessMode
0x1400134a2  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400134aa  lea     r8d, [r9+1]; CacheType
0x1400134ae  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400134b5  nop     dword ptr [rax+rax+00h]
0x1400134ba  test    rax, rax
0x1400134bd  jz      short loc_1400134D0
0x1400134bf  xor     edx, edx; Tag
0x1400134c1  mov     rcx, rax; P
0x1400134c4  call    cs:__imp_ExFreePoolWithTag
0x1400134cb  nop     dword ptr [rax+rax+00h]
0x1400134d0  mov     rcx, rbx; Mdl
0x1400134d3  mov     qword ptr [rbx], 0
0x1400134da  call    cs:__imp_IoFreeMdl
0x1400134e1  nop     dword ptr [rax+rax+00h]
0x1400134e6  add     rsp, 30h
0x1400134ea  pop     rbx
0x1400134eb  retn
```
