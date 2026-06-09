# MupGetUncCachePrefixTable

- ea: `0x14001dacc`
- end: `0x14001dae6`
- name: `MupGetUncCachePrefixTable`
- size: `26`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140003140`
- `0x1400033d0`
- `0x140014340`
- `0x1400164e0`
- `0x140016760`
- `0x140019994`
- `0x140019d10`
- `0x14001ce70`
- `0x14001d744`

## callees

- `0x1400024ec`
- `0x14001dacc`

## pseudocode

```c
__int64 __fastcall MupGetUncCachePrefixTable(__int64 a1)
{
  if ( !a1 )
    return MupGetUncCacheHostPrefixTable();
  return a1;
}

```

## disassembly

```asm
0x14001dacc  sub     rsp, 28h
0x14001dad0  test    rcx, rcx
0x14001dad3  jnz     short loc_14001DADD
0x14001dad5  call    MupGetUncCacheHostPrefixTable
0x14001dada  mov     rcx, rax
0x14001dadd  mov     rax, rcx
0x14001dae0  add     rsp, 28h
0x14001dae4  retn
```
