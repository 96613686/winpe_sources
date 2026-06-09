# MupSurrogatePurgeNegativeCacheEntry

- ea: `0x1400142f0`
- end: `0x140014324`
- name: `MupSurrogatePurgeNegativeCacheEntry`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14001067c`
- `0x1400142f0`
- `0x14001da7c`

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
0x1400142f0  sub     rsp, 28h
0x1400142f4  mov     rax, [rcx]
0x1400142f7  mov     r8d, [rax+10h]
0x1400142fb  test    r8b, r8b
0x1400142fe  js      short loc_140014307
0x140014300  mov     eax, 0C0000010h
0x140014305  jmp     short loc_14001431E
0x140014307  mov     rcx, [rcx-10h]
0x14001430b  mov     rcx, [rcx+30h]
0x14001430f  call    MupGetUncCachePrefixTable
0x140014314  mov     rcx, rax
0x140014317  call    MupFlushPrefixEntry
0x14001431c  xor     eax, eax
0x14001431e  add     rsp, 28h
0x140014322  retn
```
