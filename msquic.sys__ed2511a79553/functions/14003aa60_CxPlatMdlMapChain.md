# CxPlatMdlMapChain

- ea: `0x14003aa60`
- end: `0x14003aaac`
- name: `CxPlatMdlMapChain`
- size: `76`
- prototype: `__int64 __fastcall(PMDL MemoryDescriptorList)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003a300`

## callees

- `0x14003aa60`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003aa88`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003aa88`

## pseudocode

```c
char __fastcall CxPlatMdlMapChain(PMDL MemoryDescriptorList)
{
  PVOID v2; // rax

  while ( 1 )
  {
    if ( (MemoryDescriptorList->MdlFlags & 5) == 0 )
    {
      v2 = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000000u);
      if ( !v2 )
        break;
    }
    MemoryDescriptorList = MemoryDescriptorList->Next;
    if ( !MemoryDescriptorList )
    {
      LOBYTE(v2) = 1;
      return (char)v2;
    }
  }
  return (char)v2;
}

```

## disassembly

```asm
0x14003aa60  push    rbx
0x14003aa62  sub     rsp, 30h
0x14003aa66  mov     rbx, rcx
0x14003aa69  test    byte ptr [rbx+0Ah], 5
0x14003aa6d  jnz     short loc_14003AA99
0x14003aa6f  xor     r9d, r9d; RequestedAddress
0x14003aa72  mov     [rsp+38h+Priority], 40000000h; Priority
0x14003aa7a  and     [rsp+38h+var_18], 0
0x14003aa7f  xor     edx, edx; AccessMode
0x14003aa81  mov     rcx, rbx; MemoryDescriptorList
0x14003aa84  lea     r8d, [r9+1]; CacheType
0x14003aa88  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003aa8f  nop     dword ptr [rax+rax+00h]
0x14003aa94  test    rax, rax
0x14003aa97  jz      short loc_14003AAAA
0x14003aa99  mov     rbx, [rbx]
0x14003aa9c  test    rbx, rbx
0x14003aa9f  jnz     short loc_14003AA69
0x14003aaa1  mov     al, 1
0x14003aaa3  add     rsp, 30h
0x14003aaa7  pop     rbx
0x14003aaa8  retn
0x14003aaaa  jmp     short loc_14003AAA3
```
