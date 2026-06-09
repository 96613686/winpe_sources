# MupGetUncCachePrefixTable

- ea: `0x14001da7c`
- end: `0x14001da96`
- name: `MupGetUncCachePrefixTable`
- size: `26`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140003140`
- `0x1400033d0`
- `0x1400142f0`
- `0x140016490`
- `0x140016710`
- `0x140019944`
- `0x140019cc0`
- `0x14001ce20`
- `0x14001d6f4`

## callees

- `0x1400024ec`
- `0x14001da7c`

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
0x14001da7c  sub     rsp, 28h
0x14001da80  test    rcx, rcx
0x14001da83  jnz     short loc_14001DA8D
0x14001da85  call    MupGetUncCacheHostPrefixTable
0x14001da8a  mov     rcx, rax
0x14001da8d  mov     rax, rcx
0x14001da90  add     rsp, 28h
0x14001da94  retn
```
