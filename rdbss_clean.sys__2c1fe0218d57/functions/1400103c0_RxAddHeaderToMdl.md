# RxAddHeaderToMdl

- ea: `0x1400103c0`
- end: `0x14001048a`
- name: `RxAddHeaderToMdl`
- size: `202`
- prototype: `__int64 __fastcall(PMDL MemoryDescriptorList)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400103c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010412`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010451`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010412`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010451`

## pseudocode

```c
PVOID __fastcall RxAddHeaderToMdl(PMDL MemoryDescriptorList, ULONG a2)
{
  CSHORT MdlFlags; // ax
  __int64 v4; // rdi
  PVOID MappedSystemVa; // rcx

  MdlFlags = MemoryDescriptorList->MdlFlags;
  v4 = a2;
  if ( (MdlFlags & 0x16) == 0 )
    __int2c();
  if ( (MdlFlags & 0x1000) == 0 || MemoryDescriptorList->ByteOffset < a2 )
    return 0;
  if ( !((MdlFlags & 5) != 0
       ? MemoryDescriptorList->MappedSystemVa
       : MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u)) )
    return 0;
  MemoryDescriptorList->MappedSystemVa = (char *)MemoryDescriptorList->MappedSystemVa - v4;
  MemoryDescriptorList->ByteOffset -= v4;
  MemoryDescriptorList->ByteCount += v4;
  MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
  if ( (MemoryDescriptorList->MdlFlags & 5) == 0 )
    return MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
  return MappedSystemVa;
}

```

## disassembly

```asm
0x1400103c0  mov     [rsp+arg_10], rbx
0x1400103c5  push    rdi
0x1400103c6  sub     rsp, 30h
0x1400103ca  movzx   eax, word ptr [rcx+0Ah]
0x1400103ce  mov     rbx, rcx
0x1400103d1  mov     edi, edx
0x1400103d3  test    al, 16h
0x1400103d5  jz      loc_140010483
0x1400103db  bt      ax, 0Ch
0x1400103e0  mov     [rsp+38h+arg_0], rbp
0x1400103e5  mov     [rsp+38h+arg_8], rsi
0x1400103ea  jnb     short loc_140010465
0x1400103ec  cmp     [rcx+2Ch], edi
0x1400103ef  jb      short loc_140010465
0x1400103f1  xor     ebp, ebp
0x1400103f3  test    al, 5
0x1400103f5  jnz     loc_14001047D
0x1400103fb  mov     [rsp+38h+Priority], 40000010h; Priority
0x140010403  xor     r9d, r9d; RequestedAddress
0x140010406  xor     edx, edx; AccessMode
0x140010408  mov     [rsp+38h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x14001040c  mov     r8d, 1; CacheType
0x140010412  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140010419  nop     dword ptr [rax+rax+00h]
0x14001041e  test    rax, rax
0x140010421  jz      short loc_140010465
0x140010423  sub     [rbx+18h], rdi
0x140010427  sub     [rbx+2Ch], edi
0x14001042a  add     [rbx+28h], edi
0x14001042d  test    byte ptr [rbx+0Ah], 5
0x140010431  mov     rcx, [rbx+18h]
0x140010435  jnz     short loc_140010460
0x140010437  mov     [rsp+38h+Priority], 40000010h; Priority
0x14001043f  xor     r9d, r9d; RequestedAddress
0x140010442  xor     edx, edx; AccessMode
0x140010444  mov     [rsp+38h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x140010448  mov     r8d, 1; CacheType
0x14001044e  mov     rcx, rbx; MemoryDescriptorList
0x140010451  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140010458  nop     dword ptr [rax+rax+00h]
0x14001045d  mov     rcx, rax
0x140010460  mov     rax, rcx
0x140010463  jmp     short loc_140010467
0x140010465  xor     eax, eax
0x140010467  mov     rsi, [rsp+38h+arg_8]
0x14001046c  mov     rbp, [rsp+38h+arg_0]
0x140010471  mov     rbx, [rsp+38h+arg_10]
0x140010476  add     rsp, 30h
0x14001047a  pop     rdi
0x14001047b  retn
0x14001047d  mov     rax, [rcx+18h]
0x140010481  jmp     short loc_14001041E
0x140010483  int     2Ch; Windows NT - assertion failure
0x140010485  jmp     loc_1400103DB
```
