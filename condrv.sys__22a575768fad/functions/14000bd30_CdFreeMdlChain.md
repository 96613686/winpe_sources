# CdFreeMdlChain

- ea: `0x14000bd30`
- end: `0x14000bd7d`
- name: `CdFreeMdlChain`
- size: `77`
- prototype: `__int64 __fastcall(PMDL Mdl)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140009760`
- `0x140009af0`
- `0x14000a260`
- `0x14000b4d0`
- `0x14000b820`

## callees

- `0x14000bd30`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14000bd51`
- `ntoskrnl!MmUnlockPages` at `0x14000bd51`
- `ntoskrnl!IoFreeMdl` at `0x14000bd60`
- `ntoskrnl!IoFreeMdl` at `0x14000bd60`

## pseudocode

```c
void __fastcall CdFreeMdlChain(PMDL Mdl)
{
  PMDL v1; // rbx
  PMDL v2; // rdi

  if ( Mdl )
  {
    v1 = Mdl;
    do
    {
      v2 = v1;
      v1 = v1->Next;
      if ( (v2->MdlFlags & 2) != 0 )
        MmUnlockPages(v2);
      IoFreeMdl(v2);
    }
    while ( v1 );
  }
}

```

## disassembly

```asm
0x14000bd30  test    rcx, rcx
0x14000bd33  jz      short locret_14000BD7B
0x14000bd35  push    rbx
0x14000bd36  sub     rsp, 20h
0x14000bd3a  mov     rbx, rcx
0x14000bd3d  mov     [rsp+28h+arg_0], rdi
0x14000bd42  mov     rdi, rbx
0x14000bd45  mov     rbx, [rbx]
0x14000bd48  test    byte ptr [rdi+0Ah], 2
0x14000bd4c  jz      short loc_14000BD5D
0x14000bd4e  mov     rcx, rdi; MemoryDescriptorList
0x14000bd51  call    cs:__imp_MmUnlockPages
0x14000bd58  nop     dword ptr [rax+rax+00h]
0x14000bd5d  mov     rcx, rdi; Mdl
0x14000bd60  call    cs:__imp_IoFreeMdl
0x14000bd67  nop     dword ptr [rax+rax+00h]
0x14000bd6c  test    rbx, rbx
0x14000bd6f  jnz     short loc_14000BD42
0x14000bd71  mov     rdi, [rsp+28h+arg_0]
0x14000bd76  add     rsp, 20h
0x14000bd7a  pop     rbx
0x14000bd7b  retn
```
