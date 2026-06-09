# MupSurrogatePurgeNegativeCacheEntry

- ea: `0x140014340`
- end: `0x140014374`
- name: `MupSurrogatePurgeNegativeCacheEntry`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14001067c`
- `0x140014340`
- `0x14001dacc`

## pseudocode

```c
__int64 __fastcall MupSurrogatePurgeNegativeCacheEntry(__int64 a1)
{
  __int64 UncCachePrefixTable; // rax
  __int64 v3; // rdx

  if ( (*(_DWORD *)(*(_QWORD *)a1 + 16LL) & 0x80u) == 0 )
    return 3221225488LL;
  UncCachePrefixTable = MupGetUncCachePrefixTable(*(_QWORD *)(*(_QWORD *)(a1 - 16) + 48LL));
  MupFlushPrefixEntry(UncCachePrefixTable, v3);
  return 0;
}

```

## disassembly

```asm
0x140014340  sub     rsp, 28h
0x140014344  mov     rax, [rcx]
0x140014347  mov     r8d, [rax+10h]
0x14001434b  test    r8b, r8b
0x14001434e  js      short loc_140014357
0x140014350  mov     eax, 0C0000010h
0x140014355  jmp     short loc_14001436E
0x140014357  mov     rcx, [rcx-10h]
0x14001435b  mov     rcx, [rcx+30h]
0x14001435f  call    MupGetUncCachePrefixTable
0x140014364  mov     rcx, rax
0x140014367  call    MupFlushPrefixEntry
0x14001436c  xor     eax, eax
0x14001436e  add     rsp, 28h
0x140014372  retn
```
