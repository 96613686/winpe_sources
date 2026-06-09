# PrjfInsertEntryBackingLayerNegativePathCache

- ea: `0x1400069a4`
- end: `0x140006a51`
- name: `PrjfInsertEntryBackingLayerNegativePathCache`
- size: `173`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024184`

## callees

- `0x1400069a4`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140006a2a`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140006a2a`
- `ntoskrnl!ExAllocatePool2` at `0x1400069d6`
- `ntoskrnl!ExAllocatePool2` at `0x1400069d6`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140006a0e`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140006a0e`
- `FLTMGR!FltReleaseResource` at `0x140006a39`
- `FLTMGR!FltReleaseResource` at `0x140006a39`

## pseudocode

```c
__int64 __fastcall PrjfInsertEntryBackingLayerNegativePathCache(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 Pool2; // rdi

  if ( a1 && (*(_DWORD *)(a1 + 56) & 1) != 0 )
  {
    Pool2 = ExAllocatePool2(256, 40, 1952991824);
    *(_WORD *)(Pool2 + 26) = *(_WORD *)(a2 + 2);
    *(_WORD *)(Pool2 + 24) = *(_WORD *)a2;
    *(_QWORD *)(Pool2 + 32) = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a2 + 8) = 0;
    FltAcquireResourceExclusive((PERESOURCE)(a1 + 544));
    RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a1 + 648), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Pool2, a3, 0);
    FltReleaseResource((PERESOURCE)(a1 + 544));
  }
  return 0;
}

```

## disassembly

```asm
0x1400069a4  push    rbx
0x1400069a6  push    rbp
0x1400069a7  push    rsi
0x1400069a8  push    rdi
0x1400069a9  sub     rsp, 28h
0x1400069ad  mov     ebp, r8d
0x1400069b0  mov     rbx, rdx
0x1400069b3  mov     rsi, rcx
0x1400069b6  test    rcx, rcx
0x1400069b9  jz      loc_140006A45
0x1400069bf  mov     eax, [rcx+38h]
0x1400069c2  test    al, 1
0x1400069c4  jz      short loc_140006A45
0x1400069c6  mov     edx, 28h ; '('
0x1400069cb  mov     ecx, 100h
0x1400069d0  mov     r8d, 74684A50h
0x1400069d6  call    cs:__imp_ExAllocatePool2
0x1400069dd  nop     dword ptr [rax+rax+00h]
0x1400069e2  movzx   ecx, word ptr [rbx+2]
0x1400069e6  mov     rdi, rax
0x1400069e9  mov     [rax+1Ah], cx
0x1400069ed  movzx   ecx, word ptr [rbx]
0x1400069f0  mov     [rax+18h], cx
0x1400069f4  mov     rcx, [rbx+8]
0x1400069f8  mov     [rax+20h], rcx
0x1400069fc  mov     qword ptr [rbx+8], 0
0x140006a04  lea     rbx, [rsi+220h]
0x140006a0b  mov     rcx, rbx; Resource
0x140006a0e  call    cs:__imp_FltAcquireResourceExclusive
0x140006a15  nop     dword ptr [rax+rax+00h]
0x140006a1a  mov     r8d, ebp; Signature
0x140006a1d  lea     rcx, [rsi+288h]; HashTable
0x140006a24  xor     r9d, r9d; Context
0x140006a27  mov     rdx, rdi; Entry
0x140006a2a  call    cs:__imp_RtlInsertEntryHashTable
0x140006a31  nop     dword ptr [rax+rax+00h]
0x140006a36  mov     rcx, rbx; Resource
0x140006a39  call    cs:__imp_FltReleaseResource
0x140006a40  nop     dword ptr [rax+rax+00h]
0x140006a45  xor     eax, eax
0x140006a47  add     rsp, 28h
0x140006a4b  pop     rdi
0x140006a4c  pop     rsi
0x140006a4d  pop     rbp
0x140006a4e  pop     rbx
0x140006a4f  retn
```
